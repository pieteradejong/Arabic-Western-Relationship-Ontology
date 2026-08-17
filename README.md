# Arabic–Western Relationship Ontology

## Purpose

This project explores how Arabic and modern English divide the conceptual space of human relationships.

The central question is not simply whether Arabic has "more words for friend." Many Arabic terms commonly translated as friend actually emphasize different relational properties: companionship, intimacy, sincerity, affection, loyalty, protection, alliance, kinship, or obligation.

The broader research question is:

> Do Arabic and modern English carve up the underlying space of human relationships differently?

The goal is to build independent Arabic and English relationship ontologies, map them into a common semantic space, and eventually visualize the differences.

## Core Principle

Do not model relationships as a single categorical variable:

```
relationship_type = "friend"
```

Instead, treat a relationship as a multidimensional object.

A preliminary model:

$$R = (I, A, K, O, P, D, C, F)$$

| Dimension | Meaning |
|---|---|
| Intimacy | Emotional closeness and disclosure |
| Affection | Fondness, attachment, or love |
| Kinship | Blood, marriage, or family connection |
| Obligation | Expected duties toward the other person |
| Protection | Responsibility or willingness to defend/support |
| Duration | Stability or expected permanence |
| Companionship | Shared presence, activities, circumstances, or journey |

Possible later dimensions include trust, reciprocity, loyalty, hierarchy, dependence, exclusivity, shared identity, shared purpose, hospitality, and patronage.

## Preliminary Arabic Ontology

This is an exploratory starting point rather than a definitive linguistic taxonomy.

### Stranger / Outsider

**غريب — gharīb**

Approximate meanings:
- stranger
- outsider
- foreigner
- unfamiliar person

Represents the low-familiarity boundary of the relationship space.

### Social Association and Companionship

**جليس — jalīs**

Approximate meanings:
- someone one sits with
- social companion
- conversational companion

Emphasizes shared presence and social interaction.

**صاحب — ṣāḥib**

Approximate meanings:
- companion
- associate
- one who accompanies another

Broader than ordinary English friend. Companionship and association are central.

**رفيق — rafīq**

Approximate meanings:
- companion
- fellow
- traveling companion

Can emphasize accompanying someone through a journey, circumstance, or shared experience.

### Friendship and Intimacy

**صديق — ṣadīq**

The ordinary general Arabic word commonly translated as friend.

It is etymologically connected with the root ṣ-d-q (ص د ق), associated with truthfulness and sincerity.

Etymology should not automatically be equated with contemporary meaning, but sincerity is an important historical semantic dimension to investigate.

**أنيس — anīs**

Approximate meanings:
- congenial companion
- comforting companion
- person whose presence dispels loneliness

Interesting because it describes something about the emotional experience produced by companionship.

**حميم — ḥamīm**

Approximate meanings:
- intimate
- close friend
- very close companion

Occupies a high-intimacy portion of the relationship space.

**خليل — khalīl**

Approximate meanings:
- intimate friend
- deeply beloved friend
- exceptionally close companion

A particularly strong friendship concept in classical and religious usage.

### Affection and Love

**حبيب — ḥabīb**

Approximate meanings:
- beloved
- dear one
- loved person

Depending on context, this may describe romantic, familial, friendly, or general affection.

It therefore belongs primarily on an affection/love dimension rather than simply representing "stronger friendship."

**ودود — wadūd**

Associated with:
- loving
- affectionate
- warmly disposed

Potentially useful for representing affection, although its grammatical role should be distinguished from nouns naming relationship categories.

### Alliance, Loyalty, and Protection

**ولي — walī**

Highly context-dependent. Its semantic field can include:
- ally
- protector
- patron
- guardian
- supporter
- person possessing closeness or authority

This is a good example of why a one-dimensional friendship scale is inadequate.

A walī relationship can involve protection, loyalty, obligation, authority, patronage, and closeness without being equivalent to ordinary friendship.

**حليف — ḥalīf**

Approximate meaning:
- ally

Primarily organized around alliance, commitment, or shared interest rather than necessarily affection or intimacy.

### Kinship

**قريب — qarīb**

Depending on context:
- near
- close
- relative

The semantic relationship between nearness and kinship may itself be interesting.

**رحم — raḥim**

Associated with:
- womb
- blood relationship
- kinship ties

Kinship should be modeled as a major relational dimension rather than as a subtype of friendship.

### Antagonistic Relationships

**خصم — khaṣm**

Approximate meanings:
- opponent
- adversary
- disputant

**عدو — ʿaduww**

Approximate meaning:
- enemy

The ontology should include negative relationships so friendship exists within the broader interpersonal space.

Potential negative dimensions include rivalry, competition, hostility, distrust, conflict, and enmity.

## First-Pass Taxonomy

```
HUMAN RELATIONSHIP
│
├── STRANGER / OUTSIDER
│   └── gharīb
│
├── SOCIAL ASSOCIATION
│   ├── jalīs
│   ├── ṣāḥib
│   └── rafīq
│
├── FRIENDSHIP / INTIMACY
│   ├── ṣadīq
│   ├── anīs
│   ├── ḥamīm
│   └── khalīl
│
├── AFFECTION / LOVE
│   ├── ḥabīb
│   └── wadūd
│
├── ALLIANCE / LOYALTY / PROTECTION
│   ├── walī
│   └── ḥalīf
│
├── KINSHIP
│   ├── qarīb
│   └── raḥim
│
└── ANTAGONISM
    ├── khaṣm
    └── ʿaduww
```

This hierarchy is useful for orientation but should not become the final data model.

Human relationships overlap too much for a strict tree.

## Graph Ontology

The final ontology should preferably be represented as a graph.

Nodes can represent:
- relationship concepts
- lexical terms
- semantic properties
- people
- cultural concepts
- social institutions

Edges could represent:
- IS_A
- RELATED_TO
- MAY_INCLUDE
- IMPLIES
- INVOLVES_COMPANIONSHIP
- INVOLVES_KINSHIP
- INVOLVES_PROTECTION
- INVOLVES_AFFECTION
- STRONGER_INTIMACY_THAN
- HISTORICALLY_ASSOCIATED_WITH
- TRANSLATED_AS
- CONTRASTS_WITH

Example:

```
ṣāḥib ── companionship ──> rafīq
   │
   └── may overlap with ──> ṣadīq
                              │
                              ├── greater intimacy ──> ḥamīm
                              │
                              └── exceptional intimacy ──> khalīl

walī ── loyalty/protection ──> PERSON
ḥalīf ── alliance ───────────> PERSON
qarīb ── kinship ────────────> PERSON
ḥabīb ── affection ──────────> PERSON
```

A real relationship may instantiate several concepts simultaneously.

```
Ahmed → Omar

ṣadīq    friend
rafīq    companion
ḥabīb    dear/beloved
qarīb    relative
```

## Independent Western / English Ontology

The English ontology should not be constructed by translating the Arabic ontology.

That would bias the comparison.

Instead, construct it independently from English vocabulary and usage.

Initial candidates:
- stranger
- acquaintance
- neighbor
- associate
- colleague
- coworker
- peer
- companion
- friend
- casual friend
- close friend
- best friend
- buddy
- pal
- confidant
- mentor
- mentee
- patron
- client
- ally
- partner
- lover
- spouse
- relative
- rival
- competitor
- opponent
- adversary
- enemy

Modern categories may also be revealing:
- roommate
- classmate
- teammate
- follower
- mutual
- online friend
- work friend
- situationship
- ex
- contact
- connection

These may expose dimensions that contemporary Western society lexicalizes particularly strongly, such as professional context, institutional affiliation, romantic ambiguity, and digitally mediated relationships.

## Universal Relationship Space

After constructing the Arabic and English ontologies independently, map both into the same semantic space.

```
                 UNIVERSAL RELATIONSHIP SPACE
                           │
              ┌────────────┴────────────┐
              │                         │
         Arabic lexicon           English lexicon
              │                         │
       ṣadīq   ●                    ● friend
       rafīq   ●                    ● companion
       khalīl  ●                    ● confidant
       walī    ●                    ● ally
```

We should not expect these points to align exactly.

Important questions:
- Which concepts map closely?
- Which only partially overlap?
- Which concepts have no clean lexical equivalent?
- Where does one language use several common terms where the other uses one broad category?
- Which semantic dimensions receive especially fine lexical resolution?
- How have these mappings changed historically?

## Why a Friendship Ladder Is Insufficient

A simple model such as:

```
stranger
   ↓
acquaintance
   ↓
companion
   ↓
friend
   ↓
close friend
   ↓
intimate friend
```

is useful as one projection but misleading as an ontology.

For example:
- an ally can have high obligation but low intimacy;
- a relative can have high kinship but low affection;
- a traveling companion can have high companionship but modest intimacy;
- a patron can have high protection but low reciprocity;
- a confidant can have high trust and intimacy without frequent companionship;
- a beloved person can have high affection without fitting ordinary friendship.

Relationships therefore require multiple axes.

## Candidate Data Model

Each lexical concept could eventually be represented as structured data.

```yaml
id: ar_sadiq
language: Arabic
script: صديق
transliteration: ṣadīq
lemma: صديق
root: ص-د-ق

glosses:
  - friend
  - sincere friend

domains:
  - friendship

dimensions:
  intimacy: null
  affection: null
  kinship: null
  obligation: null
  protection: null
  duration: null
  companionship: null
  formality: null

register:
  - Modern Standard Arabic
  - Classical Arabic

notes:
  - General friendship term.
  - Root is associated historically with truthfulness and sincerity.

evidence: []
```

Initially, dimensions should remain qualitative or unscored until the ontology and evidence base are sufficiently mature.

Additional useful fields:
- language
- dialect
- historical_period
- script
- transliteration
- root
- part_of_speech
- literal_gloss
- common_gloss
- semantic_domain
- register
- frequency
- example_usage
- source
- corpus_frequency
- translation_candidates
- translation_confidence
- cultural_notes
- religious_usage
- historical_usage
- modern_usage

## Historical Layers

"Arabic" should not be treated as one timeless linguistic system.

Potential layers:

```
Arabic
├── Classical Arabic
├── Qur'anic Arabic
├── Modern Standard Arabic
├── Egyptian Arabic
├── Levantine Arabic
├── Gulf Arabic
├── Iraqi Arabic
└── Maghrebi varieties
```

Likewise, "Western" should eventually be decomposed:

```
Western comparison
├── contemporary American English
├── British English
├── historical English
├── French
├── German
├── Dutch
└── other European languages
```

The initial serious comparison should probably focus on Classical/Modern Standard Arabic and contemporary English.

## Research Methodology

Semantic distinctions should ultimately be evidence-based.

### Dictionaries and Lexicons

Use authoritative Arabic dictionaries, historical lexicons, bilingual dictionaries, and English dictionaries.

### Corpora

Measure actual usage:
- frequency
- collocations
- neighboring words
- contexts
- sentiment
- historical change

### Literature and Historical Texts

Poetry, prose, letters, religious texts, and popular writing may reveal distinctions that dictionaries flatten.

### Native-Speaker Judgments

Speakers could rate terms along semantic dimensions.

For example:

```
How much intimacy does ṣadīq imply?

0 ───────────────────── 10
```

With enough speakers, semantic scores become distributions rather than researcher guesses.

### Computational Semantics

Generate embeddings from Arabic and English corpora and analyze:
- semantic neighborhoods
- cosine similarity
- clustering
- cross-lingual alignment
- historical semantic movement

## Visualization Ideas

### 1. Semantic Map

Plot terms on selectable dimensions.

Example:

```
                    HIGH INTIMACY
                         ↑
                         │     khalīl
                         │       ●
                  ḥamīm ●       ● confidant
                         │
             ṣadīq ●    │    ● close friend
                         │
       rafīq ●           │ ● friend
                         │
  ṣāḥib ●                │       ● colleague
─────────────────────────┼──────────────────────→
                         │
                    LOW INTIMACY
```

Possible axes:
- intimacy
- affection
- obligation
- loyalty
- protection
- companionship
- kinship
- reciprocity
- formality

### 2. Radar Charts

Give each term a semantic fingerprint and overlay apparent translations such as:
- ṣadīq vs friend
- rafīq vs companion
- khalīl vs confidant

### 3. Network Graph

Nodes represent lexical concepts.

Edges represent:
- semantic similarity
- translations
- shared roots
- historical relationships
- semantic overlap

### 4. Semantic Density Map

Ask:

> Where does each language devote lexical resolution?

Instead of simply counting vocabulary, measure how densely terms occupy particular regions of relationship space.

### 5. Translation-Loss Map

Measure how well the nearest translation covers the original semantic region.

Conceptually:

```
Arabic                    English

ṣadīq ────────────────── friend
       ███████████████░░

rafīq ────────────────── companion
       ████████████░░░░░

walī ─────────────────── ???
       ███████░░░░░░░░░░
```

The metric would need to be defined empirically.

### 6. Interactive Explorer

Possible controls:

```
Language:       Arabic ↔ English
Period:         Classical ↔ Modern
Dialect:        MSA / Egyptian / Levantine / ...
Dimension X:    Intimacy
Dimension Y:    Obligation
Color:          Semantic domain
Size:           Corpus frequency
```

Clicking a concept could show:
- script
- transliteration
- pronunciation
- root
- definitions
- example usages
- historical usage
- semantic vector
- nearest concepts
- nearest translations
- translation gaps

## Research Questions

### Lexical Granularity

Does Arabic distinguish certain kinds of companionship or intimacy more finely than contemporary English?

### Translation Asymmetry

Are particular Arabic relationship concepts systematically lossy when translated into English?

Does the reverse also occur?

### Cultural Emphasis

Which relational dimensions receive particularly high lexical resolution in each linguistic community?

### Historical Change

Has English collapsed distinctions that existed historically?

Has modern Arabic retained, weakened, or repurposed classical distinctions?

### Social Structure

Do lexical categories correlate with institutions such as:
- tribe
- extended family
- patronage
- hospitality
- religious community
- professional institutions
- nuclear family
- urban anonymity
- online networks

Lexical distinctions alone cannot prove cultural behavior, so these questions require external historical and sociological evidence.

### Digital Relationships

Has contemporary English developed unusually rich vocabulary for digitally mediated weak ties?

Examples:
- follower
- mutual
- connection
- online friend
- contact

This could provide an interesting modern counterpoint to older relationship vocabularies.

## Methodological Warnings

**Avoid "Arabic Has N Words for Friend"**

Many supposedly synonymous terms emphasize different relationship dimensions.

**Avoid the Etymological Fallacy**

Historical roots illuminate semantic history but do not determine contemporary meaning.

**Translation Is Not Identity**

ṣadīq ≈ friend

does not mean:

ṣadīq = friend

**Arabic Is Not Identical to Arab Culture**

Linguistic evidence cannot automatically establish how Arabic-speaking societies structure actual relationships.

**Western Is Not Identical to English**

English is merely the first comparison language.

**Classical Is Not Modern**

Meanings change over centuries.

**More Vocabulary Does Not Mean Greater Sophistication**

Lexical density does not imply that one culture experiences relationships more deeply.

The interesting question is where and how languages lexicalize distinctions.

## Proposed Repository Structure

```
relationship-ontology/
│
├── README.md
│
├── data/
│   ├── arabic/
│   │   ├── classical.yaml
│   │   ├── msa.yaml
│   │   └── dialects/
│   │
│   ├── english/
│   │   ├── contemporary.yaml
│   │   └── historical.yaml
│   │
│   └── universal/
│       └── dimensions.yaml
│
├── sources/
│   ├── dictionaries.md
│   ├── corpora.md
│   └── bibliography.md
│
├── analysis/
│   ├── embeddings/
│   ├── clustering/
│   └── translation-loss/
│
├── visualizations/
│   ├── semantic-map/
│   ├── network/
│   ├── radar/
│   └── interactive/
│
└── docs/
    ├── methodology.md
    └── findings.md
```

## Project Sequence

### Phase 1 — Define the Ontology

Precisely define the universal semantic dimensions.

### Phase 2 — Arabic Dataset

Build a canonical dataset of approximately 30–50 Arabic relational concepts.

For each concept collect:
- Arabic spelling
- transliteration
- root and morphology
- core meanings
- semantic domain
- Classical usage
- modern usage
- dialectal variation where relevant
- example contexts
- likely relationship dimensions
- authoritative sources

### Phase 3 — Independent English Dataset

Construct approximately 30–50 English concepts independently.

Do not simply find translations for the Arabic terms.

### Phase 4 — Validation

Use:
- dictionaries
- corpora
- historical texts
- native-speaker judgments
- linguistic scholarship

### Phase 5 — Quantification

Represent each term as a semantic vector or probability distribution.

$$x_t = [I, A, K, O, P, D, C, F, \ldots]$$

### Phase 6 — Computational Analysis

Potential techniques:
- distance metrics
- hierarchical clustering
- PCA
- multidimensional scaling
- UMAP
- graph community detection
- cross-lingual embeddings

### Phase 7 — Visualization

Produce:
- semantic scatter plots
- radar charts
- network graphs
- lexical-density maps
- translation-loss diagrams
- interactive Arabic–English explorer

## Long-Term Vision

The project can eventually expand beyond Arabic and English.

```
                       HUMAN RELATIONSHIP SPACE
                                 │
        ┌──────────┬─────────────┼─────────────┬──────────┐
        │          │             │             │          │
      Arabic     English       Japanese      Greek      ...
```

Possible comparisons:
- Arabic vs English
- Classical Arabic vs modern dialects
- contemporary English vs historical English
- Japanese vs English
- ancient Greek vs modern European languages

The broader question becomes:

> How do human languages partition the universal conceptual space of interpersonal relationships?

The project sits at the intersection of:
- linguistics
- anthropology
- graph theory
- computational semantics
- NLP
- cultural history
- information visualization

## Next Step

Create `arabic_relationships.yaml` with approximately 30–50 Arabic relationship concepts.

Do not assign arbitrary numerical scores yet.

For each term first establish:
- spelling
- transliteration
- root
- morphology
- meaning
- semantic domain
- Classical vs modern usage
- likely relationship dimensions
- example usage
- authoritative sources

Then construct the English dataset independently.

Only after both datasets exist should the comparative visualization begin.

This separation is essential: it allows the visualization to reveal differences rather than merely illustrating assumptions built into the ontology.
</content>

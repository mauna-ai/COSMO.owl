# COSMO.owl

## Introduction and Status as of March 2019

For a listing of the files in this Status Summary folder see below at **FILES**.
Additional related materials are in the folder: http://micra.com/COSMO

The COSMO.owl ontology is a project of:

> Patrick Cassidy
> cassidy@micra.com
> 908-561-3416
> Plainfield, NJ

## Goal

To investigate the potential of a foundation ontology to enable broad semantic interoperability by providing a "logical defining vocabulary" that can provide logical specifications for any entity of interest, with minimal need to create and add new semantic primitives. The first phase will be to create an outline of such a foundation ontology in OWL format, to obtain an overall view of the basic concepts. If this effort suggests the feasibility of this approach, then an FOL version will be prepared to allow more detailed reasoning for further testing.

## Method

Create an OWL-format ontology that has representation for the most common words of English, and determine how many new primitives need to be added in order to represent additional concepts from other fields or less common words. Determine how many new primitives need to be added for each group of new concepts represented. Determine if the curve suggests an approach to an asymptote where only new few primitives are needed for representing the concepts of new domains and new practical applications.

## Status

As of March 5,2019, representations of the most common 5000 words (in a Brigham Young University (BYU) corpus) is completed.

## Observations to date

### Recognizing primitives

'primitives' should be those concepts that _cannot_ be represented using only combinations of concepts already in the ontology. No attempt was made to clearly identify primitives at this stage, as that will likely require an FOL version. But generally, the number of ObjectProperties plus the number of '' QualitativeAttributeValues'' (usually represented by adjectives), plus the highest-level (most general) classes, number over two thousand, and this is probably a lower limit on the actual number of primitives represented.

1. New semantic relations (in OWL, 'ObjectProperty's) are likely candidates unless they are only subproperties of existing relations with a narrower domain or range.
2. Qualitative attribute values (represented by adjectives and adverbs) tend to be vague and unless they can be represented as subattributes of existing attributes, their proper representation may require an FOL logic. Thus this type of primitive will be hard to recognize.
3. In the phase of going from the 4000th least frequent to the 5000th least frequent, the number of new ObjectProperties added per 100 new types (owl:Classes) is decreasing only slowly (about 5 new properties per 100 new classes added). Additional data will be required by addition of representations of more of the less common words in order to obtain a more precise estimates of the rate of decrease for new concept representations.

In this group of 1044 unrecognized words added, 51 new semantic relations (owl:ObjectProperty's) were added, about 1 for every 20 unrecognized words. In this segment of supplementation, there were a total of 1710 new classes added, 666 of which were not in the list of frequent words but were added to add more detail to the meaning of those common words, and for other reasons that arose in the course of the supplementation.

## owl:Class entries

| Wordnet Tags                                       | No. of words                                          |
| -------------------------------------------------- | ----------------------------------------------------- |
| WordNet base tags                                  | 9585 individual words (without WN word combinations). |
| WordNet sense tags                                 | 18,919                                                |
| WordNet senses no duplicates                       | 16,417                                                |
| Wordnet sense tags w/o sense number, no duplicates | 11,160                                                |

> [ compare WordNet no senses no spaces (single words) WN1497NoSp.txt 9585 lines]
> implies multi-word WN tags: 1575

## Lists still to do (common words not present):

| File             | Words          | Notes                                                                                                             |
| ---------------- | -------------- | ----------------------------------------------------------------------------------------------------------------- |
| CYCnotInWNEN.txt | 1669 words     | Additional Common words in Open CYC not among <wordnet. or <en> tags in rev1497                                   |
| BNCnotIn1497.txt | 1007 words     | from British National Corpus list of most frequent 6300 words) (not in WNENCYC)                                   |
| ASLnotInWEBC.txt | 2463 words     | from American Sign Language on-line dictionary not among _wordnet_, or _en_ tags nor in the OpenCYC or BNC lists. |
| **To be added**  | **5139 words** |                                                                                                                   |

## Motivation:

Semantic Interoperability is the ability of computers to correctly and automatically interpret the intended meaning of data and the symbols used to represent the data without human intervention, and use them properly in their local applications. In locally controlled contexts (as in one organization), a group of databases can be merged to form a "Data Warehouse" that permits use of information from multiple databases to be used by applications without interpretation error. This requires that one authority mandate and enforce the integration technique. But in contexts where users of one application or database want to use information from another application or database without knowing the exact meanings of the data elements, or even who created them or the reason for their creation (as with information on the Internet), some form of translation from the terminology of one database to the terminology of the other is needed. If two separately developed databases want to integrate and the developers are in contact, they can form an ad hoc translation for those two databases. But for multiple separately developed databases that is a practical impossibility. For accurate interoperability, widespread databases need to rely on automatic translation which in practice can only come from use of some common language for translation. The tactic of translation by correlations (e.g. "Deep Learning") is inapplicable because of the absence or sparsity of cross "'language" translations to train the translator.

A common ontology can function as such an interlingua. If local database managers or application developers want to use data outside their control, they can create a representation of their local data using the common ontology, which can then function as an interlingua for multiple databases, provided that they also have some representation in the terminology of the common ontology . The most efficient strategy of this type would be to use a common ontology focusing on the most fundamental concepts that are used to create representations of more specialized concepts. This is called a "'Foundation Ontology", which is one type of "Upper Ontology".

The COSMO ontology is intended to be a "Foundation Ontology" ("FO") of this kind. By focusing on discovery and representation of "semantic primitives" it is expected that the most efficient type of FO can be developed using the smallest number of concept representations to enable representation of a much larger number of specialized concepts. A "semantic primitive" is a concept that cannot be represented by a combination of concepts already in the ontology. The COSMO effort is intended to identify as many as feasible of the semantic primitives needed to represent common concepts, such as those in the Longman dictionary defining vocabulary and others in lists of the most frequently used words from two different text corpora, plus the words in an Ameslan (American Sign Language) on-line dictionary. When completed, this will form a starting point for investigation of use of this principle in practical applications, and an "outline" for expanding and elaborating the ontology to make it more logically expressive, more widely useful, and easier to use.

#### Two points are worth noting about this tactic.

1. An FO of this type can use alternative ways to represent the same intended meanings, because such alternative representations can be converted using "Bridging Axioms" (in the words of Pat Hayes). Thus far the only impediment to such translation would appear to be inclusion of an axiom asserting that some entity 'cannot exist' . This sometimes occurs in debates over 3D versus 4D (space and time) representations. Without such an axiom, bridging axioms can be developed that allow the same meanings to be represented differently and converted with logical consistency. Truly logically contradictory representations would have to be represented as different theories, but that can be done using a common set of semantic primitives. Contradictory theories need to be used and computed separately, as with the CYC "microtheories". Such multiple representations can coexist in the FO without incurring excessive computational complexity costs, because any given local application will need to use only a small fraction of the concept representations to support the local application, which can be extracted with modest or little effort.

2. The need to represent a local database using the common FO would initially be a labor-intensive effort, and is likely to be undertaken only for sets of legacy databases or applications that have a strong incentive to interoperate. But as the FO becomes more widely used, newly developed databases can be created using the FO as a foundation and will thus be interoperable without additional effort. An FO suitable as an interlingua for general interoperability will have almost the expressivity of a human language, and learning how to use it efficiently will require an effort similar to that of learning a human language. But for any given organization, it should be necessary for only one member of the database development team to be "bilingual" in the terminology of the local database and the terminology of the FO.

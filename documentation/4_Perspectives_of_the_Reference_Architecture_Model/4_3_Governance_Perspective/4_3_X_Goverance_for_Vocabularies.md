### Governance for Vocabularies ###

(original notes by Sebastian Steinbuss:
- shared vocabularies need a governance
- Problem description: reliability of vocabularies, quality assurance
- BOMOS Model as good practice?
- Mapping of Standards (written paper) to machine readable models leaves some  degrees of freedom
)

Data spaces are expected to be built in a decentralized manner and with distributed efforts, hence necessary shared vocabularies will also be created by different parties. This gives rise to the need of certain governance to ensure the interoperability of the domains involved in the respective use cases and solutions. For this, two main perspectives need to be considered, which should be supported by the Vocabulary Hub. 

1. Technical perspective, aiming at the design of vocabularies as artifacts
2. Governance perspective, aiming at the application and lifecycle of the vocabularies.

The technical perspective comprises the following aspects:
* Choice of identifiers: Vocabularies can be developed using either expressive/meaningful identifiers, i.e., names, or abstract/language-neutral identifiers for their elements. While in the first case the vocabularies are directly usable by humans at least in the language of the identifiers, the second approach requires labels in the different languages to generate human-usable display names. The IDS Information Model is designed using the first approach. With view to overall semantic interoperability within and across data spaces, such design decisions impose like modeling paradigms on vocabularies built upon, yet there may be other vocabularies used in a solution that follow the second approach. In order to achieve interoperability, mappings are necessary for linking at least entities with the same meanings but being identified differently. 
* Choice of naming conventions: They need to be agreed upon at least within one vocabulary or even better within an entire domain. This applies to any of the above-mentioned approaches to defining identifiers.
* Choice of model documentation: Vocabularies can exhibit different qualities of documentation, from carrying no documentation elements, i.e., only the bare syntactical structure, to detailed labels and comments in multiple languages. With view to use in computer linguistics scenarios it is advisable to include lemma forms.
* Choice of modeling paradigms: Technically, same aspects can be modeled differently in different domains. Further, given the possible expressivity of the languages used for the vocabularies, it is advised to establish guidelines for modeling. Semantic interoperability in general requires making any domains properly connectable, hence mapping ontologies are required in cases of heterogeneity of modeling paradigms.

The governance perspective comprises the following aspects:
* Lifecycle of vocabularies: Vocabularies can pass through phases from exploration to retirement, which needs to be followed in order to aid users in selecting suitable vocabularies for their solutions.
* Maturity of vocabularies: Given the development as a continuous process, a vocabulary can pass through different stages of maturity, including such as completeness of documentation or stability of concepts over a certain period. This involves metrics for the maturity and selection of a suitable versioning scheme.
* Approval of vocabularies: Release of a vocabulary should be controlled by either a decision board and supported by automated model checking where possible.

(TO BE ELABORATED AND CONTINUED)





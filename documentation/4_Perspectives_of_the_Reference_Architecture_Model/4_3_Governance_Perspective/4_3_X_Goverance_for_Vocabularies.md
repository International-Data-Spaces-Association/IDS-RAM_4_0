### Governance for Vocabularies ###

(original notes by Sebastian Steinbuss:
- shared vocabularies need a governance
- Problem description: reliability of vocabularies, quality assurance
- BOMOS Model as good practice?
- Mapping of Standards (written paper) to machine readable models leaves some  degrees of freedom
)

With regard to both 
- the large number and variety of domains covered by different vocabularies that can be used to achieve the necessary interoperability of the domains involved in use cases, and
- the nature of such vocabularies being developed, applied and managed in a shared manner,
two main perspectives need to be considered. 

These are
1. Technical level, aiming at the design of vocabularies
2. Governance level, aiming at the proper application and lifecycle of the vocabularies.

On the technical level, the following aspects need to be considered:
* Choice of identifiers: Vocabularies can be created using either expressive/meaningful identifiers, i.e., names, or abstract/language-neutral identifiers for their elements. While in the first case the vocabularies are directly usable at least in the language of the identifiers, the second approach requires labels in the different languages to generate human-usable artifacts. The IDS Information Model is created using the first approach. With view to overall semantic interoperability within and across data spaces, such design decisions impose like modeling paradigms on vocabularies built upon, yet there can be existing standards following the second approach. In order to achieve overall interoperability, mapping vocabularies are necessary not only for connecting different modeling paradigms but also for connecting vocabularies following different naming schemes. The Vocabulary Hub serves the task of integrating such vocabularies.
* Choice of naming conventions: They need to be agreed upon at least within one vocabulary or even better within an entire domain. This applies to any of the above-mentioned approaches to defining identifiers.
* Choice of modeling paradigms: Technically, same aspects can be modeled differently in different domains. Semantic interoperability requires making such domains properly connectable, hence mapping ontologies are required in such cases.
* Choice of model documentation: Vocabularies can exhibit different qualities of documentation, from carrying no documentation elements, i.e., only the bare syntactical structure, to detailed labels in multiple languages.

On the governance level, aspects to be considered include:
* Maturity of individual vocabularies
* Lifecycle of individual vocabularies as well as of interlinked ones

(TO BE ELABORATED AND CONTINUED)





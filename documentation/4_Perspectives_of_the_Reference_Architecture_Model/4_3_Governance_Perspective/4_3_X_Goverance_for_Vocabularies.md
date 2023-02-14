### Governance for Vocabularies

Data spaces are expected to be built in a decentralized manner and with distributed efforts,
hence necessary shared vocabularies will also be created by different parties.
This gives rise to the need of certain governance to ensure the interoperability of the domains involved
in the respective use cases and solutions.
For this, two main perspectives need to be considered, which should be supported by the Vocabulary Hub. 

1. Technical perspective, aiming at the design of vocabularies as artifacts
2. Governance perspective, aiming at the application and lifecycle of the vocabularies.


The need for shared vocabularies, or 'semantic standards', in data sharing networks cannot be overstated.
They provide a common language for describing data, allowing different systems and organizations to share
and understand the data  effectively. Without semantic standards, data is likely to be inconsistent and
difficult to understand, and the added value of sharing that data decreases.


Good standards are living documents in that they change over time. Semantic standards are no different.
They pass through life cycle phases from exploration to retirement. Given the development as a continuous process,
a semantic standard can pass through different stages of maturity, including such as completeness of documentation
or stability of concepts over a certain period. This involves the use of metrics for the maturity and selection
of a suitable versioning scheme.

Setting up governance of semantic standards is essential to ensure they are technically sound and reliable,
but also to keep them in line with the changing needs of its users. Governance means setting guidelines for
creating and maintaining the standards, as well as processes for resolving conflicts or inconsistencies that may arise. 

The governance perspective comprises the following aspects:
* Lifecycle of vocabularies: Vocabularies can pass through phases from exploration to retirement, which needs to be followed in order to aid users in selecting suitable vocabularies for their solutions.
* Maturity of vocabularies: Given the development as a continuous process, a vocabulary can pass through different stages of maturity, including such as completeness of documentation or stability of concepts over a certain period. This involves metrics for the maturity and selection of a suitable versioning scheme.
* Approval of vocabularies: Release of a vocabulary should be controlled by either a decision board and supported by automated model checking where possible.

#### Open vs. centralized governance
Governance can be set up in varying gradations of openness and centralization. The former promotes a more democratic and participatory process, where decision about the standards are made by a broad range of stakeholders. Governance in this sense is about ensuring that the standards are inclusive and reflective of the needs of all stakeholders.

In centralized governance, the authority and responsibility often rest with a single organization, such as a government agency or an industry association. This organization has the power to create and maintain the standards, and often also to enforce them through regulations or other means. 

A governance model leaning towards centralization can be more efficient, as it allows for quicker decision-making and can be more effective in ensuring compliance. However, because less effort is spent on fostering inclusiveness and participation, it runs a greater risk of overrepresenting some stakeholders while underrepresting the interests of others in the decision about the standards.

#### Governance goals
Whatever the approach, the goals of governance remain the same and can be summarized as: 
- to ensure reliability of the vocabulary
- to ensure quality of the vocabulary
- to boost adoption of the vocabulary

Decisions about the semantic standard are made through the governance organization, e.g., decision to work start development work, approval of changes in the new version, and release of said version through publication on the web. In open standardization, the work is carried out by its members as much as possible, while the goverannce organization acts as coordinator and oversees progress.


##### Reliability
Ensuring the reliability of the vocabulary, i.e. its accuracy and consistency, is crucial. This means ensuring that the terms and definitions used in the vocabulary are unambiguous and used consistently throughout the model. Without reliable vocabularies, there is a risk of misunderstandings and misinterpretations of data even among compliant systems, which can lead to incorrect conclusions and poor decision making.

##### Quality assurance
Additionally, governance ensures quality of the vocabulary, i.e. that it's complete, up-to-date, and relevant to the needs of stakeholders. Without quality assurance, vocabularies may be missing important terms, or may not be reflective of current needs or industry standards. To address this problem, governance organizations establish a process for quality assurance, which includes regular reviews and updates of the vocabularies, and input from stakeholders.

##### Adoption
Standards make an impact only when they are adopted by users. Good governance is constantly identifying barriers that hamper adoption or opportunties that could boost it. This involves promoting the use of the vocabulary among different systems and organizations and encouraging compliance with the standards. Because of the network effect on the added value of standards, the benefits of the semantic standards will be limited without widespread adoption, and data sharing will continue to be inconsistent and costly.

To achieve this aim, vocabulary governance organizations often employ strategies for communication and education, such as providing training and resources to help stakeholders understand and use the vocabulary. Additionally, they often design incentives or rewards for organizations that adopt the vocabulary and comply with the standards, such as recognition or access to exclusive resources. Ideally, governance organizations also monitor and track the adoption of the vocabulary to identify any areas where additional support is needed, to make sure that the vocabulary is being used as intended. 


#### Best modelling practices
The technical perspective comprises the following aspects:
* **Choice of identifiers**: Vocabularies can be developed using either expressive/meaningful identifiers, i.e., names, or abstract/language-neutral identifiers for their elements. While in the first case the vocabularies are directly usable by humans at least in the language of the identifiers, the second approach requires labels in the different languages to generate human-usable display names. The IDS Information Model is designed using the first approach. With view to overall semantic interoperability within and across data spaces, such design decisions impose like modeling paradigms on vocabularies built upon, yet there may be other vocabularies used in a solution that follow the second approach. In order to achieve interoperability, mappings are necessary for linking at least entities with the same meanings but being identified differently. 
* **Choice of naming conventions**: They need to be agreed upon at least within one vocabulary or even better within an entire domain. This applies to any of the above-mentioned approaches to defining identifiers.
* **Choice of model documentation**: Vocabularies can exhibit different qualities of documentation, from carrying no documentation elements, i.e., only the bare syntactical structure, to detailed labels and comments in multiple languages. With view to use in computer linguistics scenarios it is advisable to include lemma forms.
* **Choice of modeling paradigms**: Technically, same aspects can be modeled differently in different domains. Further, given the possible expressivity of the languages used for the vocabularies, it is advised to establish guidelines for modeling. Semantic interoperability in general requires making any domains properly connectable, hence mapping ontologies are required in cases of heterogeneity of modeling paradigms.

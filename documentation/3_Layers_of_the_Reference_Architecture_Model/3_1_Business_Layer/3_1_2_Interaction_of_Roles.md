### Interaction of Roles ###

#### Basic interactions for data exchange and data sharing in the International Data Spaces ####

The figure below gives an overview of the roles and the interactions taking place between
them. As some of the roles (Certification Body and Evaluation
Facilities) are not actively involved in the everyday operations of the
International Data Spaces, they are omitted from the illustration. Also,
the figure does not include Software Providers and Identity Providers,
because of the necessary connection of those roles with all other roles.
The Software Provider would be connected to all other roles with the
relation _provides software_. Likewise, the Identity Provider
would be connected to all other roles with the relation _provides
identity_.

![ Roles and interactions in the International Data
Spaces](./media/image18.png)
##### Figure 3.1.2: Roles and interactions in the International Data Spaces

This shows only the basic interactions taking place between the different
roles in the International Data Spaces. For data exchange, additional,
more specific interactions are necessary. These interactions are
described in the [Process Layer](../3_4_Process_Layer/3_4_Process_Layer.md) section of the Reference Architecture
Model.

The table below gives an overview of possible (mandatory are marked with X
or optional marked with (X)) interactions taking place in the IDS.

|                          | Data Owner  | Data Provider  | Data Consumer  | Data User  | Broker  | Clearing House  | Identity Provider  | Service Provider  | App Provider  | App Store  | Vocabulary Provider | Certification Body  | Evaluation Facility  |
|------------------------- |:----------: |:-------------: |:-------------: |:---------: |:------: |:--------------: |:-----------------: |:----------------: |:------------: |:---------: |:------------------: |:------------------: |:--------------------: |
| **Data Owner**           |      -      |       X        |       -        |     -      |    -    |       (X)       |         -          |        (X)        |      (X)      |    (X)     |         (X)         |          -          |          (X)          |
| **Data Provider**        |      X      |       -        |       X        |     -      |    X    |       (X)       |         X          |        (X)        |      (X)      |    (X)     |         (X)         |          -          |           X           |
| **Data Consumer**        |      -      |       X        |       -        |     X      |   (X)   |       (X)       |         X          |        (X)        |      (X)      |    (X)     |         (X)         |          -          |           X           |
| **Data User**            |      -      |       -        |       X        |     -      |    -    |       (X)       |         -          |        (X)        |      (X)      |    (X)     |         (X)         |          -          |          (X)          |
| **Broker**               |      -      |      (X)       |      (X)       |     -      |    -    |        -        |         X          |        (X)        |       -       |     -      |          ?          |          -          |           X           |
| **Clearing House**       |     (X)     |      (X)       |      (X)       |    (X)     |    -    |        -        |         X          |        (X)        |      (X)      |    (X)     |         (X)         |          -          |           X           |
| **Identity Provider**    |      -      |       X        |       X        |     -      |    X    |        X        |     Federation     |         -         |     (X)?      |    (X)?    |          -          |          -          |           X           |
| **Service Provider**     |     (X)     |      (X)       |      (X)       |    (X)     |   (X)   |       (X)       |         -          |         -         |      (X)      |    (X)     |         (X)         |          -          |           X           |
| **App Provider**         |     (X)     |      (X)       |      (X)       |    (X)     |    -    |       (X)       |        (X)         |        (X)        |       -       |    (X)     |          -          |          -          |          (X)          |
| **App Store**            |     (X)     |      (X)       |      (X)       |    (X)     |    -    |       (X)       |        (X)         |        (X)        |      (X)      |     -      |         (X)         |          -          |          (X)          |
| **Vocabulary Provider**  |     (X)     |      (X)       |      (X)       |    (X)     |    ?    |       (X)       |        (X)         |        (X)        |      (X)      |    (X)     |          -          |          -          |           X           |
| **Certification Body**   |      -      |       -        |       -        |     -      |    -    |        -        |         -          |         -         |       -       |     -      |          -          |          -          |           X           |
| **Evaluation Facility**  |     (X)     |       X        |       X        |     X      |    X    |        X        |         X          |         X         |      (X)      |     X      |          X          |          X          |           -           |

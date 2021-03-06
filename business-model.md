
# Business Object Model

In this section you will learn

1. What is a Business Object Model.
2. How to create a Business Object Model inside the RHPAM Business Central Workbench.
3. How to import a project into your space.

The Credit Card Dispute process is not straightforward. It involves different actors inside, and outside of, the company. These actors need to have visibility and control at all times into what is happening during the processing of each dispute.

We have identified the actors involved in the overall CC Dispute process. These actors are outside of the corporation and we can think of them as external entities. Entities that we will connect with to get information, but that do not participate in the dispute resolution process. We will see more of that in the Case Management Scenario.

---
**NOTE**

To get an overview of the actors, look into the Use Case overview of step 1 of this module.

---

One of the requirements to successfully process a dispute is that all of the parties involved are aware of the dispute status at all times, since they can all influence the final resolution of the dispute. Because different parties will have visibility into, and sometimes control over, the process, we need a domain model that clearly depicts the objects that describe the data and the actors that do interact in the resolution of the Credit Card Dispute process.

So far we can identify 3 major entities:

- Card Holder
- Fraud Data
- Additional Information

_The difference between these entities and the Actors is that these entities are the ones that contain data that is relevant to the processing of the dispute. This data will come from/is provide by the different actors and will be stored in the dispute process instance as process variables._

## The Business Domain Context

You, as business domain expert, need to define what the domain model is for the business capability you're trying to automate. Eric Evans coined the term [_Domain Driven Design_](https://en.wikipedia.org/wiki/Domain-driven_design) that holds 3 main guiding principles:

- Focus on the core domain.
- Explore models in a creative collaboration of domain practitioners and software practitioners.
- Speak a ubiquitous language within an explicitly bounded context.

You can learn more about this design approach in his book.

So, the first and very important task when automating a core business capability is to create a definition of the business entities within the context of the Credit Card Dispute domain. In our case, our first entity is the `Credit Card Holder`. The definition in the context of our use case maybe totally different from the definition inside other organizations. But within our use case, it will be common definition among the team of business and technology experts. I.e. it will be part of our _ubiquitous language_.

## Creating the Card Holder entity

1. From your Lab Information page, click the link for the **Business Central Console**.
1. Login to Business Central with the credentials u:`pamAdmin`, p:`redhatpam1!`

    ![Business Central Console]({% image_path business-central-console.png %}){:width="600px"}

1. Select _Design_ from the main menu. You will be redirected to your working space. This is the sandbox in which you'll define your projects, and within those projects, your projects assets.

1. Click on the _Add Project_ button to create a new project in your space. When the _Add Project_ wizard opens up, type in `ccd-project` as the name of the project, and `Assets to Automate credit card dispute process` as the description of your project. This project is your business boundary that encapsulates your business capability.

    Once the creation of your project is complete you should see the following page with the project content, which, at the moment, is empty.

    ![Business Central Asset Empty Project]({% image_path business-central-asset-empty-project.png %}){:width="600px"}

1. You will see a blue button called `Add Asset`. An asset is any Rule, Process, Decision Table, Data Object, Data Form, etc. Click on the `Add Asset` button and you will be presented with a catalog of the wizards to create assets.

    ![Business Central Asset Catalog]({% image_path business-central-asset-catalog.png %}){:width="600px"}

1. Select the wizard for _Data Object_ from the catalog to create your business object model for the _Credit Card Holder_, type `CreditCardHolder` {{copy}} as the name of the object and select `com.myspace.ccd_project` as the Package. Click OK

    ![Business Central CCD Object]({% image_path business-central-CCD-object-new.png %}){:width="600px"}

1. You will see the new created object with no properties, lets click on the `+add field` button to start adding the properties to our CreditCardHolder.

    ![Business Central CCD Object New Empty]({% image_path business-central-CCD-object-new-empty.png %}){:width="600px"}

1. In the _New Field_ window, enter the following values and click on _Create_:

    - Id: `age`
    - Label: `Age`
    - Type: `Integer`

    ![Business Central CCD Object New Properties]({% image_path business-central-CCD-object-new-properties.png %}){:width="600px"}

The first step to automate a process or decision is to define and specify the Business Object Model. In this exercise you've created the Entity `CreditCardHolder` and defined it's `age` field. These entities will be used to store the information that you need to make decisions and drive process execution.

## Import Remainder of Project

You will now import the rest of the Business Object Model from a predefined repository. Once you have successfully imported it, examine the other entities in your project.

1. Delete the current project

    1. At the top of the screen under the main heading, click the _ccd-project_ to bring you back to the homepage for the project

    ![Business Central Breadcrumb bar ccd project]({% image_path business-central-breadcrumb-bar-ccd-project.png %}){:width="600px"}

    2. Delete the project by clicking the hamburger menu & selecting _Delete Project_

    ![Business Central Delete CCD Project]({% image_path business-central-delete-ccd-project.png %}){:width="600px"}

    3. Type in _ccd-project_ and click `Delete Project`
    4. If asked you can `Discard unsaved changed and proceed`

2. Import the finished Domain Model
    1. Click the `Import Project` button
    2. Enter [https://github.com/RedHat-Middleware-Workshops/rhpam-rhdm-workshop-v1m2-labs-step-2.git](https://github.com/RedHat-Middleware-Workshops/rhpam-rhdm-workshop-v1m2-labs-step-2.git) as the _Repository URL_ and click `Import`
    3. On the _Import Projects_ screen, select the _ccd-project_ and click `Ok`

    ![Business Central Delete CCD Project]({% image_path business-central-import-ccd-project.png %}){:width="600px"}

3. Examine the other newly-imported entities

# About
[HomeSpace](https://homespace.is) is a decentralized social network representing an aggregate of photorealistic virtual worlds with a separate world for each user, adapted for mobile devices, PC, and VR. All complex digital objects in Homespace are NFT tokens created by professional designers using the built-in NFT converter. The direction of the project development is the creation of each user's own dream home (his own Homespace), development of virtual areas for user interaction: Defi Wall-street, game rooms, educational worlds, etc., implementation of AI worlds based on machine learning, creation of creative workshops.

# Technical Overview
## Overview
In developing HomeSpace, we want to focus on achieving the highest possible rendering quality on all devices. To do this, we decided to go in several ways: by developing a standard client on the one hand, as well as a stream service for browsers on the other, which would allow us to get a high-quality AAA picture, which does not depend in any way on the characteristics of the computer or phone on which it is launched.

For mobile devices, it will also be a client with a texture simplification and polygon reduction system.

Based on our past development experience, we chose the following technologies for project implementation:

## Architecture
Homespace's core services will be written in the Kotlin language. It will help us to develop quickly, produce maintainable code and reduce the number of possible problems. We will also use a number of NodeJS lambda functions for infrastructure maintaining tasks.

Using Kotlin multiplatform, we can share core business logic between various platforms (iOS, Android, Web, Desktop) and get native applications as an output. That saves us development time, helps to build consistent logic for all platforms, and gives us the benefit of native application performance. And, also, an easy way to integrate with native third-party libraries and the unreal engine. 

Remote procedure call (RPC) generator will be used to create a consistent way to communicate between client and server.

Client applications will be able to work offline having limited functionality and will be immediately synchronized when getting back online.

For the backend services, written in Kotlin, we will use Ktor. It's Kotlin native, asynchronous, lightweight framework. Ktor has all the necessary functionality and is able to start very quickly, which is especially important when scaling up.

Communication between client and server will happen via secure WebSockets to provide the client with live updates and reduce the number of unnecessary network calls. We will also provide a REST API for integration with third parties. 

## Social Network
Amazon Cognito is used to manage user authentication and some authorization. It's a rich solution to allow our users to use multiple authentication methods with 2FA and store their data securely.

For voice communication and chat, we will use a third-party solution based on WebRTC technology (Agora, ConnectyCube). Users will be able to connect directly and communicate within an end-to-end encrypted channel.

Live updates from the server and push notifications will be used for real-time users state updates.

## Cloud System
The application will be deployed to the AWS cloud. It provides mature out-of-the-box solutions for our needs. The infrastructure will be managed by Terraform.

The main part of the application will be located in a virtual private network (VPC). VPC is divided into private and public subnets into different availability zones for higher availability. Communication between services is carried out inside the VPC via an internal load balancer or event bus to reduce the number of possible security problems. The entry point for clients is an external load balancer that will handle base security rules and routes.

Each service is located in its own auto-scaling group that will automatically increase or reduce the number of instances based on current needs. Services will use relational or NoSQL databases based on their purposes. We will also use S3 to store the files and models. We will use ElasticCache with Redis for caching data.

We will collect various application metrics and logs using CloudWatch, ElasticSearch, and Graphite. And then monitor them in Grafana and Kibana.

## Unreal Engine
After a long analysis, the HomeSpace team has decided that Unreal Engine is the most suitable game developing engine for this specific project. It has lots of lightning and effects settings, which are perfect for projects with architectural elements and photorealistic graphics. Unreal Engine is a robust tool with lots of official and community created features, which will help us to speed up the development process while simultaneously maintaining the highest quality possible.

## Open development tracking Principles 
As part of the work of our company Vergil Development Studio, we use the Agile methodology, which we also apply in the development of the HomeSpace project.  The main concept of this approach is that we will initially have two main documents - a backlog, which will describe all the components that must be implemented within our system, as well as user stories, which will describe the UX of each user action.  All development will be divided into two-week sprints, not counting the tasks that will be performed by the community developers.

In an effort to speed up the development process as much as possible, we will create a microservice architecture for individual external parts of our system to enable third-party developers to perform our tasks through the Bounty Builder program as a reward in the form of tokens. Tokens for external developers will be distributed in the first 2 years of the project's existence, according to successfully voted rewarding proposals on our governance forum.

We will also post monthly reports on our development in all our groups on social networks.

## Blockchain
Homespace’s core infrastructure relies on the Ethereum blockchain, which allows it to securely and transparently store and protect user’s ownership of their assets in a trustless environment. 

On-chain infrastructure will consist of three main components: HomeSpace Protocol,  Homespace DAO and Homespace Governance Token (HOMES / HSP)

## Functionality
- Create NFT
- What: Anything (Architecture, Furniture & Sculpture, Art & Images, Skyboxes, Music)
- Who: Anyone
- How: Provides metadata, mint, appears in unassigned collection
- Import NFT
- What: Limited at the beginning (Art, Music)
- Who: Anyone
- How: Specifies data, transfers, appears in unassigned collection
- Sell / Buy / Auction
- Public marketplace
- Wrap (Assign)
- How: TBD, Depends on UniverseXYZ, more likely NFT ownership by  NFT

## Homespace DAO (SafeSnap)
- Off-chain voting
- On-chain execution
- Controls Homespace Protocol
- Controls Ecosystem fund
- Controls Emergency mechanisms
- Signalling votes for community-driven development of the ecosystem
- Already audited

## Homespace Protocol
- Wrapper around UniverseXYZ
- Controlled by Homespace DAO
- Upgradability
- Parameters
- Uses Primary NFTs
- Created by Homespace
- Uses Secondary NFTs
- Imported (external) NFTs
- Emergency mechanisms
- Closed-source initially
- Open Source after audit
- Bounty program
- ENS domains for entities
- Interoperability

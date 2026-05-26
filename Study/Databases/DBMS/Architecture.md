### What is abstraction?
- System hides certain details that are not usefull for user.
- i.e Car driving: User don't care about when he/she press acceralator or break how the actual thing works so engineer hides it.
- Abstraction provides different views for different deoartments according to their needs and permisions.
- It's like logistic department can only access logtic information, they should not care about other departments.
- In summary user don't care about algorithm and engineer hides the algorithm that how thing works?

### What is schema?
Schema is a design that describes how table will be displays.

# Three schema architecture

- **Purpose of DBMS:** A Database Management System (DBMS) serves to provide users with a simplified and abstract view of data, hiding the complexities of data storage and maintenance.
<br>

- **Abstraction through Levels:** Abstraction is applied through different levels to simplify user interactions with the system.
<br>

- **Three-Level Architecture Objective:** The main aim of the Three-Level Architecture is to allow multiple users to access the same data while customizing their views, all while storing the actual data only once.

## Physical Level (Internal Level):

- The lowest level of abstraction that deals with how data is physically stored.

- Involves low-level data structures, like how data is arranged and organized.

- Describes the physical schema, which defines the physical storage structure of the database.

- Covers topics such as storage allocation (e.g., N-ary tree), data compression, encryption, and more.

- It also known as Database schema.

- Goal: Define algorithms that enable efficient access to data.

## Logical Level (Conceptual Level):


- Describes the design of the database at a conceptual level.

- Specifies what data is stored in the database and how different data elements are related to each other.

- Users at the logical level do not need to concern themselves with the physical-level structures.

- It also known as Database schema.

- Database administrators (DBAs) use the logical level to make decisions about what information should be stored in the database.

- Goal: Simplify data usage and make it user-friendly.

## View Level (External Level):

- This is the level where regular users interact with the database system.

- Each user can have a customized view of the data, tailored to their specific needs.

- The view level is like the interface users see when interacting with a software application or a website.

- It allows users to access the data they need in a way that's relevant to their tasks.

- Goal: Provide a user-friendly and personalized experience for accessing data.

![[Pasted image 20231023164640.png]]

**Important:** conversion of data from lower level layer to higher level layer is called mapping.
### Difference between Physical and Logical level architecture

**Physical Level:**
- The physical level of a database deals with the nitty-gritty technical details of how data is stored on a computer's hardware.
- It's like understanding how files are saved on your computer's hard drive or how data is stored on a disk.
- In this level, you think about data structures, storage allocation, compression, encryption, and similar technical aspects.
- The main goal here is to ensure data is stored efficiently and effectively on the physical hardware.

**Logical Level:**
- The logical level is all about how you organize and view the data in a way that makes sense for users.
- It focuses on what data is in the database and how it's related to other data, without diving into the technical details.
- It's like designing the blueprint of a house without getting into the specifics of construction materials.
- People working at the logical level, like database administrators, decide what information should be stored in the database and how it should be organized to make it user-friendly.
- The main goal here is to make data easy to use and understand for users without worrying about the underlying technical complexities.

In essence, the physical level deals with the technical aspects of data storage, while the logical level is concerned with how data is structured and presented to users in a way that's meaningful and user-friendly.

### Instances of schemas?
1. The collection of information stored in the DB at a particular moment is called an instance of DB.
2. The overall design of the DB is called the DB schema.
3. Schema is structural description of data. Schema doesn’t change frequently. Data may change frequently.
4. DB schema corresponds to the variable declarations (along with type) in a program.
5. We have 3 types of Schemas: Physical, Logical, several view schemas called subschemas.
6. Logical schema is most important in terms of its effect on application programs, as programmers construct apps by using logical schema.
7. Physical data independence, physical schema change should not affect logical schema/application programs

# Tier based Architecture in Networking

## T1 Architecture:

- **Definition:** T1, short for "T-Carrier 1," is a widely used digital transmission technology in telecommunications.
- **Data Rate:** It operates at a data rate of 1.544 Mbps (megabits per second).
- **Usage:** T1 lines are commonly used for high-speed internet connections and for voice and data transmission in business settings.
- **Channels:** T1 can be divided into 24 channels, each operating at 64 Kbps (kilobits per second).
- **Reliability:** T1 lines are known for their reliability and are often used for critical business applications.
- **Applications:** T1 is suitable for businesses that require stable and consistent high-speed data and voice transmission.

## T2 Architecture:

- **Definition:** T2, or "T-Carrier 2," is a digital transmission technology with higher data rates compared to T1.
- **Data Rate:** T2 operates at a data rate of 6.312 Mbps.
- **Usage:** T2 lines are used for larger organizations, institutions, and internet service providers (ISPs) requiring higher bandwidth.
- **Channels:** T2 lines consist of four T1 lines, providing a total of 96 channels, each running at 64 Kbps.
- **Reliability:** Similar to T1, T2 lines are known for their reliability and are suitable for mission-critical applications.
- **Applications:** T2 is ideal for organizations with substantial data and voice communication needs and a demand for higher bandwidth.

## T3 Architecture:

- **Definition:** T3, also known as "T-Carrier 3" or "DS3," is a high-capacity digital transmission technology.
- **Data Rate:** T3 operates at a data rate of 44.736 Mbps.
- **Usage:** T3 lines are typically employed by large corporations, data centers, and service providers that require substantial bandwidth.
- **Channels:** T3 lines consist of 28 T1 lines or 672 individual channels, each operating at 64 Kbps.
- **Reliability:** T3 connections provide a high level of reliability and are suitable for demanding applications.
- **Applications:** T3 is used for data-intensive applications, high-quality video streaming, and large-scale data transfer, making it a crucial part of the internet backbone.


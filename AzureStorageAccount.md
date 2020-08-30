# Azure Storage Account

Microsoft Azure Cloud offers several types of scalable, high-availability storage: for tables, queues, files, blobs, and Azure virtual machine disks

![N|Solid](Image.png)

# Types
- Blob Storage  
- Table Storage
- Queue Storage
- Disk Storage

##### Blob Storage
‘Blob’ stands for Binary Large Object and includes text files, images, audios, and videos. Azure Blob is a service that stores massive unstructured data that can be accessed from any place via protocols like HTTP or HTTPS.
>This is the most basic and the cheapest way to store your files in Azure.

##### Queue Storage

Queue Storage is a type of storage designed to connect components of your application. It allows you to build flexible applications with decoupled and independent components that rely on asynchronous message queuing.

##### Table Storage
Table storage can store, you guessed it, tables. Microsoft Azure Table Storage was designed to store structured NoSQL data. The storage is hugely scalable and, at the same time, cheap to keep data in. 
It is schemaless, i.e., the data does not have a fixed structure. You can easily store datasets that do not require any joins or foreign keys. You can denormalize them to make quicker access. You can scale up the tables based on your requirements.

##### Disk Storage
Microsoft Azure Disk Storage works on the basis of Page Blobs. It is a service that allows you to create disks for your virtual machines. The disk, created in Disk Storage, can be accessed from only one virtual machine. In other words - it is your local drive.
They are accessible via SMB.

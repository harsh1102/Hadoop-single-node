# Hadoop Single-Node Cluster
## About Apache Hadoop

Apache Hadoop is a set of algorithms (an open-source software framework written in Java) for distributed storage and distributed processing of very large data sets (Big Data) on computer clusters built from commodity hardware. All the modules in Hadoop are designed with a fundamental assumption that hardware failures (of individual machines, or racks of machines) are commonplace and thus should be automatically handled in software by the framework.

In this tutorial I will describe the required steps for setting up a pseudo-distributed, single-node Hadoop cluster backed by the Hadoop Distributed File System.

## Benefits of using Hadoop

The architecture of Hadoop allows you to scale your hardware as and when you need to. New nodes can be added incrementally without having to worry about the change in data formats or the handling of applications that sit on the file system.

One of the most important features of Hadoop is that it allows you to save enormous amounts of money by substituting cheap commodity servers for expensive ones. This is possible because Hadoop transfers the responsibility of fault tolerance from the hardware layer to the application layer.

## Environment Versions
```bash
Ubuntu 19.04 LTS Xenial Xerus 64-bit Server Edition
Hadoop 3.2.0
```
## Single-node Installation

The report here will describe the required steps for setting up a single-node Hadoop cluster backed by the Hadoop Distributed File System, running on Ubuntu Linux. Hadoop is a framework written in Java for running applications on large clusters of commodity hardware and incorporates features similar to those of the Google File System (GFS) and of the MapReduce computing paradigm. Hadoop’s HDFS is a highly fault-tolerant distributed file system and, like Hadoop in general, designed to be deployed on low-cost hardware. It provides high throughput access to application data and is suitable for applications that have large data sets.

Before we start, we will understand the meaning of the following:

## DataNode

A DataNode stores data in the Hadoop File System. A functional file system has more than one DataNode, with the data replicated across them.

## NameNode

The NameNode is the centrepiece of an HDFS file system. It keeps the directory of all files in the file system, and tracks where across the cluster the file data is kept. It does not store the data of these file itself.

## NodeManager

The NodeManager (NM) is YARN’s per-node agent, and takes care of the individual compute nodes in a Hadoop cluster. This includes keeping up-to date with the ResourceManager (RM), overseeing containers’ life-cycle management; monitoring resource usage (memory, CPU) of individual containers, tracking node-health, log’s management and auxiliary services which may be exploited by different YARN applications.

## ResourceManager

ResourceManager (RM) is the master that arbitrates all the available cluster resources and thus helps manage the distributed applications running on the YARN system. It works together with the per-node NodeManagers (NMs) and the per-application ApplicationMasters (AMs).

## Secondary Namenode

Secondary Namenode whole purpose is to have a checkpoint in HDFS. It is just a helper node for namenode.


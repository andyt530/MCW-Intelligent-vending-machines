# Intelligent vending machines hands-on lab

## Contents

- [Abstract](#abstract)
- [Overview](#overview)
- [Solution architecture](#solution-architecture)
- [Requirements](#requirements)
- [Before the hands-on lab](#before-the-hands-on-lab)
- [Hands-on lab](#hands-on-lab)

## Abstract

In this hands-on lab, you will implement an IoT solution for intelligent vending machines, leveraging facial feature recognition and Azure Machine Learning, to gain a better understanding of building cloud-based machine learning apps and real-time analytics with SQL Database in-memory and columnar indexing.

At the end of this hands-on lab, you will be better able to build IoT solutions leveraging cloud-based machine learning services and real-time analytics.

## Overview

Trey Research Inc. looks at the old way of doing things in retail and introduces innovative experiences that delight customers and drive sales. Their latest initiative focuses on intelligent vending machines that support commerce, engagement analytics, and intelligent promotions.

## Solution architecture

Below is a diagram of the solution architecture you will build in this lab. Please study this carefully, so you understand the whole of the solution as you are working on the various components.

![Diagram of the preferred solution. From a high-level, the commerce solution uses an API App to host the Payments web service with which the Vending Machine interacts to conduct purchase transactions. The Payment Web API invokes a 3rd party payment gateway as needed for authorizing and capturing credit card payments, and logs the purchase transaction to SQL DB. The data for these purchase transactions is stored using an In-Memory table with a Columnar Index, which will support the write-heavy workload while still allowing analytics to operate, such as queries coming from Power BI Desktop.](./media/preferred-solution-architecture.png "Preferred high-level architecture")

## Requirements

- Microsoft Azure subscription must be pay-as-you-go or MSDN
  - Trial subscriptions will not work
- A virtual machine configured with:
  - Visual Studio Community 2017 15.6 or later
  - Azure SDK 2.9 or later (Included with Visual Studio 2017)
  - [R Tools for Visual Studio](https://aka.ms/rtvs-current) 0.3.2 or later
  - [Power BI Desktop](https://powerbi.microsoft.com/desktop) (June 2016 build or later)
  - A running R Server on HD Insight Spark cluster (see [Before the hands-on lab](#before-the-hands-on-lab))

## Before the hands-on lab

Before attending the hands-on lab workshop, you should set up your environment for use in the rest of the hands-on lab.

You should follow all the steps provided in the [Before the hands-on lab](./Setup.md) section to prepare your environment before attending the hands-on lab. Failure to complete the Before the hands-on lab setup may result in an inability to complete the lab with in the time allowed.

## Hands-on lab

Select the guide you are using to complete the Hands-on lab below.

- [Step-by-step guide](./HOL-step-by-step-Intelligent-vending-machines.md)
  - Provides detailed, step-by-step instructions for completing the lab.
- [Unguided](./HOL-uguided-Intelligent-vending-machines.md)
  - This guide provides minimal instruction, and assumes a high-level of knowledge about the technologies used in this lab. This should typically only be used if you are doing this as part of a group.
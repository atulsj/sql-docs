---
title: "Multidimensional Model Solution Deployment | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
  - "analysis-services/multidimensional-tabular"
  - "analysis-services/data-mining"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Analysis Services deployments, planning"
  - "deploying [Analysis Services]"
  - "deploying [Analysis Services], planning"
ms.assetid: 7259c201-ff54-43e8-bda5-a6d51474e0e6
caps.latest.revision: 39
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
---
# Multidimensional Model Solution Deployment
  After you have completed the development of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you can deploy the database to an Analysis Services server. Analysis Services provides six possible deployment methods that can be used to move the database to a test or production server. The methods are listed here in order of advantage: AMO Automation, XMLA, Deployment Wizard, Deployment Utility, Synchronize Wizard, Backup and Restore.  
  
 This topic includes the following sections:  
  
 [Deployment Methods](#bkmk_meth)  
  
 [Deployment considerations](#bkmk_considerations)  
  
 [Related Tasks](#bkmk_rel)  
  
##  <a name="bkmk_meth"></a> Deployment Methods  
  
|Method|Description|Link|  
|------------|-----------------|----------|  
|**Analysis Management Objects (AMO) Automation**|AMO provides a programmatic interface to the complete command set for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], including commands that can be used for solution deployment. As an approach for solution deployment, AMO automation is the most flexible, but it also requires a programming effort.  A key advantage to using AMO is that you can use SQL Server Agent with your AMO application to run deployment on a preset schedule.|[Developing with Analysis Management Objects &#40;AMO&#41;](../../analysis-services/multidimensional-models/analysis-management-objects/developing-with-analysis-management-objects-amo.md)|  
|**XMLA**|Use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to generate an XMLA script of the metadata of an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, and then run that script on another server to recreate the initial database. XMLA scripts are easily formed in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by defining the deployment process, then codifying it and saving it in an XMLA script. Once you have the XMLA script in a saved file, you can easily run the script according to a schedule, or embed the script in an application that connects directly to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].<br /><br /> You can also run XMLA Scripts on a preset basis using SQL Server Agent, but you do not have the same flexibility with XMLA Scripts as with AMO. AMO provides a larger breadth of functionality by hosting the complete spectrum of administrative commands.|[Deploy Model Solutions Using XMLA](../../analysis-services/multidimensional-models/deploy-model-solutions-using-xmla.md)|  
|**Deployment Wizard**|Use the Deployment Wizard to use the XMLA output files generated by an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to deploy the project's metadata to a destination server. With the Deployment Wizard, you can deploy directly from the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] file, as created by the output directory by project build.<br /><br /> The primary advantage of using the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard is convenience. Just as you can save an XMLA script for use later in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can save Deployment Wizard scripts. The Deployment Wizard can be run both interactively and at the command prompt via the Deployment Utility.|[Deploy Model Solutions Using the Deployment Wizard](../../analysis-services/multidimensional-models/deploy-model-solutions-using-the-deployment-wizard.md)|  
|**Deployment Utility**|The Deployment utility lets you start the Analysis Services deployment engine from a command prompt.|[Deploy Model Solutions with the Deployment Utility](../../analysis-services/multidimensional-models/deploy-model-solutions-with-the-deployment-utility.md)|  
|**Synchronize Database Wizard**|Use the Synchronize Database Wizard to synchronize the metadata and data between any two [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases.<br /><br /> The Synchronize Wizard can be used to copy both data and metadata from a source server to a destination server. If the destination server does not have a copy of the database that you want to deploy, a new database is copied to the destination server. If the destination server already has a copy of the same database, the database on the destination server is updated to use the metadata and data of the source database.|[Synchronize Analysis Services Databases](../../analysis-services/multidimensional-models/synchronize-analysis-services-databases.md)|  
|**Backup and Restore**|Backup offers the simplest approach to transferring [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases. From the **Backup** dialog box, you can set the options configuration, and then you can run the backup from the dialog box itself. Or, you can create a script that can be saved and run as frequently as required.<br /><br /> Backup and restore is not used as frequently as the other deployment methods, but is a way to quickly complete a deployment with minimal infrastructure requirements.|[Backup and Restore of Analysis Services Databases](../../analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases.md)|  
  
##  <a name="bkmk_considerations"></a> Deployment considerations  
 Before you deploy an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, consider which of these questions apply to your solution and then review the related link to learn ways of addressing the issue:  
  
|Consideration|Link to more information|  
|-------------------|------------------------------|  
|What hardware and software resources are required for this solution?|[Requirements and Considerations for Analysis Services Deployment](../../analysis-services/multidimensional-models/requirements-and-considerations-for-analysis-services-deployment.md)|  
|How will you deploy related objects that are outside the scope of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, such as [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, reports, or relational database schemas?||  
|How will you load and update the data in the deployed [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database?<br /><br /> How will you update the metadata (such as calculations) in the deployed [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database?|[Deployment Methods](#bkmk_meth) in this topic.|  
|Do you want to give users access to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data through the Internet?|[Configure HTTP Access to Analysis Services on Internet Information Services &#40;IIS&#41; 8.0](../../analysis-services/instances/configure-http-access-to-analysis-services-on-iis-8-0.md)|  
|Do you want to provide continuous query access to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data?|[Requirements and Considerations for Analysis Services Deployment](../../analysis-services/multidimensional-models/requirements-and-considerations-for-analysis-services-deployment.md)|  
|Do you want to deploy objects in a distributed environment by using linked objects or remote partitions?|[Create and Manage a Local Partition &#40;Analysis Services&#41;](../../analysis-services/multidimensional-models/create-and-manage-a-local-partition-analysis-services.md), [Create and Manage a Remote Partition &#40;Analysis Services&#41;](../../analysis-services/multidimensional-models/create-and-manage-a-remote-partition-analysis-services.md) and [Linked Measure Groups](../../analysis-services/multidimensional-models/linked-measure-groups.md).|  
|How will you secure the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data?|[Authorizing access to objects and operations &#40;Analysis Services&#41;](../../analysis-services/multidimensional-models/authorizing-access-to-objects-and-operations-analysis-services.md)|  
  
##  <a name="bkmk_rel"></a> Related Tasks  
 [Requirements and Considerations for Analysis Services Deployment](../../analysis-services/multidimensional-models/requirements-and-considerations-for-analysis-services-deployment.md)  
  
 [Deploy Model Solutions Using XMLA](../../analysis-services/multidimensional-models/deploy-model-solutions-using-xmla.md)  
  
 [Deploy Model Solutions Using the Deployment Wizard](../../analysis-services/multidimensional-models/deploy-model-solutions-using-the-deployment-wizard.md)  
  
 [Deploy Model Solutions with the Deployment Utility](../../analysis-services/multidimensional-models/deploy-model-solutions-with-the-deployment-utility.md)  
  
  
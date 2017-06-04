---
title: "Almac&#233;n de instancias de flujo de trabajo de SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8cd2f8a5-4bf8-46ea-8909-c7fdb314fabc
caps.latest.revision: 26
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 26
---
# Almac&#233;n de instancias de flujo de trabajo de SQL
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] se distribuye con el almacén de instancias de flujo de trabajo de SQL, que permite a los flujos de trabajo conservar información de estado sobre las instancias de flujo de trabajo en una base de datos de SQL Server 2005 o SQL Server 2008.Esta característica se implementa principalmente en el formulario de la clase <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, que deriva de la clase <xref:System.Runtime.Persistence.InstanceStore> abstracta del marco de persistencia.La característica Almacén de instancias de flujo de trabajo de SQL constituye un proveedor de persistencia de SQL, que es una implementación concreta de la API de persistencia que un host usa para enviar los comandos de persistencia al almacén.  
  
 El Almacén de instancias de flujo de trabajo de SQL admite ambos flujos de trabajo auto\-hospedados o servicios de flujo de trabajo que usan <xref:System.Activities.WorkflowApplication> o <xref:System.ServiceModel.WorkflowServiceHost>, así como los servicios hospedados en WAS que usen <xref:System.ServiceModel.WorkflowServiceHost>.Puede configurar la característica Almacén de instancias de flujo de trabajo de SQL para servicos auto\-hospedados mediante programación usando para ello el modelo de objeto expuesto por la característica.Puede configurar esta característica para los servicios hospedados por <xref:System.ServiceModel.WorkflowServiceHost> mediante programación al usar el modelo de objetos y también un archivo de configuración XML.  
  
 La característica Almacén de instancias de flujo de trabajo de SQL \(**SqlWorkflowInstanceStore**\) no implementa <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> y, por tanto, no proporciona el soporte técnico de persistencia para los servicios WCF duraderos que no sean del flujo de trabajo.Tampoco implementa <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> y, por tanto, tampoco ofrece soporte técnico de persistencia para flujos de trabajo 3.x.La característica admite la persistencia únicamente para los flujos de trabajo de WF 4.0 \(y posterior\) y servicios de flujo de trabajo.La característica admite también cualquier base de datos distinta de SQL Server 2005 y SQL Server 2008.  
  
 Los temas en esta sección describen las propiedades y características del almacén de instancias de flujo de trabajo de SQL y le proporcionan los detalles sobre cómo configurar el almacén.  
  
 Windows Server App Fabric proporciona su propio almacén y herramientas de instancia para simplificar la configuración y el uso del almacén de instancias.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)] vea [Proveedores de almacenes de instancias, consultas y control](http://go.microsoft.com/fwlink/?LinkId=201201).[!INCLUDE[crabout](../../../includes/crabout-md.md)] la base de datos de persistencia de App Fabric SQL Server, vea [Base de datos de persistencia de SQL Server](http://go.microsoft.com/fwlink/?LinkId=201202).  
  
## En esta sección  
  
-   [Propiedades del almacén de instancias de flujo de trabajo de SQL](../../../docs/framework/windows-workflow-foundation//properties-of-sql-workflow-instance-store.md)  
  
-   [Cómo: Habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
-   [Activación de instancias](../../../docs/framework/windows-workflow-foundation//instance-activation.md)  
  
-   [Soporte técnico para consultas](../../../docs/framework/windows-workflow-foundation//support-for-queries.md)  
  
-   [Extensibilidad de almacén](../../../docs/framework/windows-workflow-foundation//store-extensibility.md)  
  
-   [Seguridad](../../../docs/framework/windows-workflow-foundation//security.md)  
  
-   [Base de datos de persistencia de SQL Server](../../../docs/framework/windows-workflow-foundation//sql-server-persistence-database.md)  
  
## Vea también  
 [Ejemplos de persistencia](http://go.microsoft.com/fwlink/?LinkID=177735)
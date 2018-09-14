---
title: Almacén de instancias de flujo de trabajo de SQL
ms.date: 03/30/2017
ms.assetid: 8cd2f8a5-4bf8-46ea-8909-c7fdb314fabc
ms.openlocfilehash: 680a233ca721cd8a0c620b797832419f460b13b6
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45594290"
---
# <a name="sql-workflow-instance-store"></a>Almacén de instancias de flujo de trabajo de SQL
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] se distribuye con el almacén de instancias de flujo de trabajo de SQL, que permite a los flujos de trabajo conservar información de estado sobre las instancias de flujo de trabajo en una base de datos de SQL Server 2005 o SQL Server 2008. Esta característica se implementa principalmente en el formulario de la clase <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, que deriva de la clase <xref:System.Runtime.DurableInstancing.InstanceStore> abstracta del marco de persistencia. La característica Almacén de instancias de flujo de trabajo de SQL constituye un proveedor de persistencia de SQL, que es una implementación concreta de la API de persistencia que un host usa para enviar los comandos de persistencia al almacén.  
  
 El Almacén de instancias de flujo de trabajo de SQL admite ambos flujos de trabajo auto-hospedados o servicios de flujo de trabajo que usan <xref:System.Activities.WorkflowApplication> o <xref:System.ServiceModel.WorkflowServiceHost>, así como los servicios hospedados en WAS que usen <xref:System.ServiceModel.WorkflowServiceHost>. Puede configurar la característica Almacén de instancias de flujo de trabajo de SQL para servicios auto-hospedados mediante programación usando para ello el modelo de objeto expuesto por la característica. Puede configurar esta característica para los servicios hospedados por <xref:System.ServiceModel.WorkflowServiceHost> mediante programación al usar el modelo de objetos y también un archivo de configuración XML.  
  
 La característica de Store de instancia de flujo de trabajo de SQL (**SqlWorkflowInstanceStore** clase) no implementa <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> y, por tanto, no ofrece compatibilidad con la persistencia para los servicios WCF duraderos sin flujo de trabajo. Tampoco implementa <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> y, por tanto, tampoco ofrece soporte técnico de persistencia para flujos de trabajo 3.x. La característica admite la persistencia únicamente para los flujos de trabajo de WF 4.0 (y posteriores) y servicios de flujo de trabajo. La característica admite también cualquier base de datos distinta de SQL Server 2005 y SQL Server 2008.  
  
 Los temas en esta sección describen las propiedades y características del almacén de instancias de flujo de trabajo de SQL y le proporcionan los detalles sobre cómo configurar el almacén.  
  
 Windows Server App Fabric proporciona su propio almacén y herramientas de instancia para simplificar la configuración y el uso del almacén de instancias. Para obtener más información, consulte vea [Windows Server App Fabric instancia Store](https://go.microsoft.com/fwlink/?LinkId=201201). Para obtener más información acerca de la aplicación Fabric SQL Server, vea [App Fabric SQL Server Database de persistencia](https://go.microsoft.com/fwlink/?LinkId=201202)  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Propiedades del almacén de instancias de flujo de trabajo de SQL](../../../docs/framework/windows-workflow-foundation/properties-of-sql-workflow-instance-store.md)  
  
-   [Cómo habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
-   [Activación de instancias](../../../docs/framework/windows-workflow-foundation/instance-activation.md)  
  
-   [Soporte técnico para consultas](../../../docs/framework/windows-workflow-foundation/support-for-queries.md)  
  
-   [Extensibilidad de almacén](../../../docs/framework/windows-workflow-foundation/store-extensibility.md)  
  
-   [Seguridad](../../../docs/framework/windows-workflow-foundation/security.md)  
  
-   [Base de datos de persistencia de SQL Server](../../../docs/framework/windows-workflow-foundation/sql-server-persistence-database.md)  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de persistencia](https://go.microsoft.com/fwlink/?LinkID=177735)

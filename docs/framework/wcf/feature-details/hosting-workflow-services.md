---
title: Hospedar servicios de flujo de trabajo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d55217e-8697-4113-94ce-10b60863342e
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ad4e5af26291c210f4f46f20e5b9585e3e095ae7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="hosting-workflow-services"></a>Hospedar servicios de flujo de trabajo
Debe hospedarse un servicio del flujo de trabajo para que responda a los mensajes entrantes. Los servicios del flujo de trabajo usan la infraestructura de mensajería de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y, por lo tanto, se hospedan de maneras similares. Como los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], los servicios de flujo de trabajo se pueden hospedar en cualquier aplicación administrada, en Internet Information Services (IIS) o en Windows Process Activation Services (WAS). Además, los servicios de flujo de trabajo se pueden hospedar en Windows Server App Fabric. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Vea Windows Server App Fabric [documentación de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193037), [características de hospedaje de AppFabric](http://go.microsoft.com/fwlink/?LinkId=196494), y [conceptos de hospedaje de AppFabric](http://go.microsoft.com/fwlink/?LinkId=196495). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]las diversas maneras host [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services; vea [servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="hosting-in-a-managed-application"></a>Hospedar en una aplicación administrada  
 Para hospedar un servicio de flujo de trabajo en una aplicación administrada, use la clase <xref:System.ServiceModel.Activities.WorkflowServiceHost>. El constructor <xref:System.ServiceModel.Activities.WorkflowServiceHost> le permite especificar una instancia de servicio del flujo de trabajo singleton, una definición del servicio de flujo de trabajo o una actividad que usa las actividades de mensajería de flujo de trabajo. Llamar a <<!--zz xref:System.ServiceModel.Activities.WorkflowServiceHost.Open%2A--> `System.ServiceModel.Activities.WorkflowServiceHost.Open`> hace que el servicio se inicia la escucha para los mensajes entrantes.  
  
## <a name="hosting-under-iis-or-was"></a>Hospedar en IIS o WAS  
 Hospedar un servicio de flujo de trabajo en IIS o FUE implica la creación de un directorio virtual y la colocación de archivos en el directorio virtual para definir el servicio y su comportamiento. Al hospedar un servicio de flujo de trabajo en IIS o WAS, existen varias posibilidades:  
  
-   Coloque un archivo .xamlx que defina el servicio de flujo de trabajo en un directorio virtual de IIS/WAS junto con un archivo Web.config que especifique los comportamientos del servicio, los extremos y otros elementos de configuración.  
  
-   Coloque en un directorio virtual de IIS/WAS un archivo .xamlx que defina el servicio del flujo de trabajo. El archivo .xamlx especifica los extremos que se van a exponer. Los extremos se especifican en un elemento `WorkflowService.Endpoints`, como se muestra en el siguiente ejemplo.  
  
    ```xml  
    <WorkflowService xmlns="http://schemas.microsoft.com/netfx/2009/xaml/servicemodel"  xmlns:p1="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:sad="clr-namespace:System.Activities.Debugger;assembly=System.Activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
      <WorkflowService.Endpoints>  
        <Endpoint ServiceContractName="IWorkFlowEchoService" AddressUri="">  
          <Endpoint.Binding>  
            <BasicHttpBinding />  
          </Endpoint.Binding>  
        </Endpoint>  
      </WorkflowService.Endpoints>  
    <!-- ... -->  
    </WorkflowService>  
    ```  
  
    > [!NOTE]
    >  Los comportamientos no se pueden especificar en un archivo .xamlx, de modo que debe usar un archivo Web.config si necesita especificar la configuración del comportamiento.  
  
-   Coloque en un directorio virtual de IIS/WAS un archivo .xamlx que defina el servicio del flujo de trabajo. Además, coloque un archivo .svc en el directorio virtual. El archivo .svc le permite especificar un generador de host de servicio Web personalizado, aplicar el comportamiento personalizado o cargar la configuración desde una ubicación personalizada.  
  
-   Coloque en el directorio virtual de IIS/WAS un ensamblado que contenga una actividad que use las actividades de mensajería de WF.  
  
 Un archivo .xamlx que define un servicio de flujo de trabajo debe contener un <`Service`> elemento raíz o un elemento raíz que contiene cualquier tipo derivado de <xref:System.Workflow.ComponentModel.Activity>. Al utilizar la plantilla Actividad de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], se crea un archivo .xamlx. Al utilizar la plantilla del servicio de flujo de trabajo de WCF, se crea un archivo .xamlx.  
  
## <a name="hosting-workflow-services-under-windows-server-app-fabric"></a>Hospedar servicios de flujo de trabajo en Windows Server App Fabric  
 El hospedaje de un servicio de flujo de trabajo en Windows Server App Fabric se realiza del mismo modo que el hospedaje en IIS/WAS. La única diferencia es el hecho de que Windows Server App Fabric se instala. Windows Server App Fabric proporciona herramientas que se agregan al Administrador de Internet Information Services, además de los commandlets de PowerShell. Estas herramientas simplifican la implementación, la administración y el seguimiento de los servicios de flujo de trabajo y los servicios WCF. . [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Vea Windows Server App Fabric [Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193037)  
  
## <a name="referencing-custom-activities"></a>Hacer referencia a actividades personalizadas  
 Las referencias a las actividades personalizadas deben agregarse a la <`Assemblies`> en la sección <`System.Web.Compilation`> para que se cargan en el dominio de aplicación y el deserializador XAML es capaz de encontrar los tipos. Esta configuración se puede realizar en el nivel de la aplicación o en el archivo Web.config de la raíz si la configuración se debe aplicar a todas las aplicaciones del equipo.  
  
## <a name="deployment"></a>Implementación  
 La herramienta de implementación web se ha creado para facilitar el trabajo de implementación. La herramienta le permite migrar las aplicaciones entre IIS 6.0 e IIS 7.0, sincronizar las granjas de servidores y empaquetar, archivar e implementar las aplicaciones web. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Herramienta de implementación de MS](http://go.microsoft.com/fwlink/?LinkId=178690)  
  
## <a name="see-also"></a>Vea también  
 [Funcionamiento interno de Host de servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 [Configurar WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)

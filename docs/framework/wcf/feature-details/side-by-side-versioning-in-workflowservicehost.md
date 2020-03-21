---
title: Control de versiones en paralelo en WorkflowServiceHost
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 60887eed-df40-4412-b812-41e1dd329d15
ms.openlocfilehash: bc662e51c96a06737e1bd6fd78d5f70f3922d080
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184470"
---
# <a name="side-by-side-versioning-in-workflowservicehost"></a>Control de versiones en paralelo en WorkflowServiceHost
El <xref:System.ServiceModel.Activities.WorkflowServiceHost> control de versiones en paralelo introducido en .NET Framework 4.5 proporciona la capacidad de hospedar varias versiones de un servicio de flujo de trabajo en un único punto de conexión. La funcionalidad en paralelo proporcionada permite configurar un servicio de flujo de trabajo para crear nuevas instancias del servicio de flujo de trabajo usando la nueva definición de flujo de trabajo, mientras que las instancias en ejecución se completan usando la definición existente. Este tema proporciona información general sobre la ejecución en paralelo del servicio de flujo de trabajo mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
> [!NOTE]
> Para descargar un ejemplo y ver un tutorial de vídeo de control de versiones en paralelo del servicio de flujo de trabajo, consulte Control de versiones en paralelo con un servicio de flujo de trabajo [Xamlx hospedado](https://go.microsoft.com/fwlink/?LinkId=393746)en Web .  
  
## <a name="hosting-multiple-versions-in-a-workflow-service"></a>Hospedar varias versiones en un servicio de flujo de trabajo  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost> contiene dos propiedades que se pueden configurar para permitir la ejecución en paralelo de varias versiones de un flujo de trabajo: <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> y <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>. <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> contiene las versiones admitidas del servicio de flujo de trabajo y <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> se usa para identificar de forma única cada servicio de flujo de trabajo. Esto se hace asociando <xref:System.Activities.WorkflowIdentity> al servicio de flujo de trabajo. <xref:System.Activities.WorkflowIdentity> contiene tres elementos de información de identificación. <xref:System.Activities.WorkflowIdentity.Name%2A> y <xref:System.Activities.WorkflowIdentity.Version%2A> contienen un nombre y <xref:System.Version> y son necesarios, y <xref:System.Activities.WorkflowIdentity.Package%2A> es opcional y se puede usar para especificar una cadena adicional que contiene información como el nombre del ensamblado u otra información deseada. Cada servicio de flujo de trabajo contenido en la colección <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> debe tener una <xref:System.Activities.WorkflowIdentity> única. <xref:System.Activities.WorkflowIdentity> es único si cualquiera de sus tres propiedades son diferentes de otra <xref:System.Activities.WorkflowIdentity>. A `null` <xref:System.Activities.WorkflowIdentity> es un valor <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>permitido para , pero solo una `null` <xref:System.Activities.WorkflowIdentity>versión anterior de un servicio de flujo de trabajo puede tener un archivo .  
  
> [!IMPORTANT]
> Un objeto <xref:System.Activities.WorkflowIdentity> no debe contener información de identificación personal (PII). <xref:System.Activities.WorkflowIdentity> se compone de tres partes: <xref:System.Activities.WorkflowIdentity.Name%2A> (<xref:System.String>), <xref:System.Activities.WorkflowIdentity.Version%2A> (<xref:System.Version>) y <xref:System.Activities.WorkflowIdentity.Package%2A> (<xref:System.String>). El runtime emite la información acerca del elemento <xref:System.Activities.WorkflowIdentity> usado para crear una instancia a cualquier servicio de seguimiento configurado en diferentes puntos del ciclo de vida de actividad. El seguimiento de WF no tiene ningún mecanismo para ocultar la PII (datos de usuario confidenciales). Por lo tanto, una instancia de <xref:System.Activities.WorkflowIdentity> no debe contener datos PII ya que el runtime los emitirá en registros de seguimiento y serán visibles para cualquiera que tenga acceso para ver los registros de seguimiento.  
  
### <a name="rules-for-hosting-multiple-versions-of-a-workflow-service"></a>Reglas para hospedar varias versiones de un servicio de flujo de trabajo  
 Cuando un usuario agrega una versión adicional a <xref:System.ServiceModel.Activities.WorkflowServiceHost>, se deben cumplir varias condiciones para que un servicio de flujo de trabajo se hospede con el mismo conjunto de puntos de conexión y descripción. Si cualquiera de las versiones adicionales no cumple estas condiciones, <xref:System.ServiceModel.Activities.WorkflowServiceHost> produce una excepción cuando se llama a `Open`. Cada definición de flujo de trabajo proporcionada al host como versión adicional debe cumplir los requisitos siguientes (donde la versión principal es la definición de servicio de flujo de trabajo que se proporciona al constructor de host). La versión adicional del flujo de trabajo debe:  
  
- Tenga el mismo <xref:System.ServiceModel.Activities.WorkflowService.Name%2A> que la versión principal del servicio de flujo de trabajo.  
  
- No debe tener ninguna actividad <xref:System.ServiceModel.Activities.Receive> o <xref:System.ServiceModel.Activities.SendReply> en su <xref:System.ServiceModel.Activities.WorkflowService.Body%2A> que no esté en la versión principal y deben coincidir con el contrato de operación.  
  
- Tenga una <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> única. Una única definición de flujo de trabajo puede tener una `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.  
  
 Se permiten algunos cambios. Los elementos siguientes pueden ser diferentes en las versiones:  
  
- <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> puede tener un nombre y un paquete diferentes que la versión principal.  
  
- El valor de <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> puede ser diferente que el de la versión principal.  
  
- <xref:System.ServiceModel.Activities.WorkflowService.ConfigurationName%2A> puede ser diferente que el de la versión principal.  
  
- <xref:System.ServiceModel.Activities.WorkflowService.ImplementedContracts%2A> puede ser diferente que el de la versión principal.  
  
### <a name="configuring-the-definitionidentity"></a>Configurar DefinitionIdentity  
 Cuando se crea un servicio de <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> flujo de trabajo mediante el diseñador de flujo de trabajo, se establece mediante la ventana **Propiedades.** Haga clic fuera de la actividad raíz del servicio en el diseñador para seleccionar el servicio de flujo de trabajo y elija **Ventana de propiedades** en el menú **Ver.** Seleccione **WorkflowIdentity** en la lista desplegable que aparece junto a la propiedad <xref:System.Activities.WorkflowIdentity> **DefinitionIdentity** y, a continuación, expanda y especifique las propiedades deseadas. En el ejemplo <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> siguiente se <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` configura <xref:System.Activities.WorkflowIdentity.Version%2A> `1.0.0.0`con el y a de . <xref:System.Activities.WorkflowIdentity.Package%2A> es opcional y en este ejemplo es `null`.  
  
 ![Captura de pantalla que muestra la propiedad DefinitionIdentity.](./media/side-by-side-versioning-in-workflowservicehost/definitionidentity-property.bmp)  
  
 Cuando un servicio de flujo de trabajo se hospeda a sí mismo, se configura <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> cuando se construye el servicio de flujo de trabajo. En el ejemplo <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> siguiente, se configura con los mismos <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` valores <xref:System.Activities.WorkflowIdentity.Name%2A> `1.0.0.0`que el ejemplo anterior, con el y a de .  
  
```csharp  
WorkflowService service = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflow(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    }  
};  
```  
  
```vb  
Dim service As New WorkflowService  
With service  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflow  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(1, 0, 0, 0) _  
    }  
End With  
```  
  
 A <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> no es necesario, aunque solo una versión del servicio de flujo de trabajo puede tener un **valor null**<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.  
  
> [!NOTE]
> Esto es útil si el servicio se implementó inicialmente sin una <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> configurada y, a continuación, se creó una versión actualizada.  
  
### <a name="adding-a-new-version-to-a-web-hosted-workflow-service"></a>Agregar una nueva versión a un servicio de flujo de trabajo hospedado en web  
 El primer paso para configurar una nueva versión de un servicio de flujo de trabajo en un servicio hospedado en web es crear una nueva carpeta en la carpeta `App_Code` que tiene el mismo nombre que el archivo de servicio. Si el archivo `xamlx` del servicio se denomina `MortgageWorkflow.xamlx`, la carpeta se debe llamar `MortgageWorkflow`. Coloque una copia del archivo `xamlx` del servicio original en esta carpeta y asígnele un nuevo nombre, como `MortgageWorkflowV1.xamlx`. Realice los cambios deseados al servicio primario, actualice su <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> y después implemente el servicio. En el ejemplo siguiente se ha actualizado <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> con un <xref:System.Activities.WorkflowIdentity.Name%2A> de `MortgageWorkflow` y una <xref:System.Activities.WorkflowIdentity.Version%2A> de `2.0.0.0`.  
  
 ![Captura de pantalla que muestra DefinitionIdentity de WorkflowIdentity.](./media/side-by-side-versioning-in-workflowservicehost/definitionidentity-workflowidentity.bmp)  
  
 Cuando se reinicie el servicio, la versión anterior se agregará automáticamente a la colección <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> porque se encuentra en la subcarpeta `App_Code` designada. Tenga en cuenta que si la `null` <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> versión principal del servicio de flujo de trabajo tiene una versión anterior no se agregará. Una versión puede tener una `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, pero si hay varias versiones la versión principal no debe ser la que tenga una `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> o bien las versiones anteriores no se agregarán a la colección <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>.  
  
### <a name="adding-a-new-version-to-a-self-hosted-workflow-service"></a>Agregar una nueva versión a un servicio de flujo de trabajo autohospedado  
 Al agregar una nueva versión a un servicio de flujo de trabajo autohospedado, <xref:System.ServiceModel.Activities.WorkflowServiceHost> se configura con la versión principal del servicio de flujo de trabajo y las versiones anteriores deben agregarse explícitamente a la colección <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>. En el ejemplo siguiente, <xref:System.ServiceModel.Activities.WorkflowServiceHost> se configura con un servicio primario de flujo de trabajo que usa una definición de flujo de trabajo de `MortgageWorkflowV2` y se agrega un servicio de flujo de trabajo configurado con una definición de flujo de trabajo de `MortgageWorkflowV1` a la colección <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>. Cada servicio de flujo de trabajo se configura con una <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> única que refleja la versión de la definición de flujo de trabajo.  
  
```csharp  
// Create the primary version of the workflow service.  
WorkflowService serviceV2 = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflowV2(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(2, 0, 0, 0)  
    }  
};  
  
// Configure the WorkflowServiceHost with the current version  
// of the workflow service. This code requires Administrator  
// privileges to function correctly. If running from Visual  
// Studio, Visual Studio must be run with Administrator privileges.  
WorkflowServiceHost host = new WorkflowServiceHost(serviceV2,
    new Uri("http://localhost:8080/MortgageWorkflowService"));  
  
// Create the previous version of the workflow service.  
WorkflowService serviceV1 = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflowV1(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    }  
};  
  
// Add the previous version of the service to the SupportedVersions collection.  
host.SupportedVersions.Add(serviceV1);  
```  
  
```vb  
'Create the primary version of the workflow service  
Dim serviceV2 As New WorkflowService  
With serviceV2  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflowV2  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(2, 0, 0, 0) _  
    }  
End With  
  
'Configure the WorkflowServiceHost with the current version  
'of the workflow service. This code requires Administrator  
'privileges to function correctly. If running from Visual  
'Studio, Visual Studio must be run with Administrator privileges.  
  
Dim host As New WorkflowServiceHost(serviceV2, _  
    New Uri("http://localhost:8080/MortgageWorkflowService"))  
  
'Create the previous version of the workflow service.  
Dim serviceV1 As New WorkflowService  
With serviceV1  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflowV1  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(1, 0, 0, 0) _  
    }  
End With  
  
'Add the previous version of the service to the SupportedVersions collection.  
host.SupportedVersions.Add(serviceV1)  
```

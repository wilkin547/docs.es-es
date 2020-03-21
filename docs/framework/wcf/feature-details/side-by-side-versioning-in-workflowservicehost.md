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
# <a name="side-by-side-versioning-in-workflowservicehost"></a><span data-ttu-id="bc451-102">Control de versiones en paralelo en WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="bc451-102">Side by Side Versioning in WorkflowServiceHost</span></span>
<span data-ttu-id="bc451-103">El <xref:System.ServiceModel.Activities.WorkflowServiceHost> control de versiones en paralelo introducido en .NET Framework 4.5 proporciona la capacidad de hospedar varias versiones de un servicio de flujo de trabajo en un único punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bc451-103">The <xref:System.ServiceModel.Activities.WorkflowServiceHost> side-by-side versioning introduced in .NET Framework 4.5 provides the capability to host multiple versions of a workflow service on a single endpoint.</span></span> <span data-ttu-id="bc451-104">La funcionalidad en paralelo proporcionada permite configurar un servicio de flujo de trabajo para crear nuevas instancias del servicio de flujo de trabajo usando la nueva definición de flujo de trabajo, mientras que las instancias en ejecución se completan usando la definición existente.</span><span class="sxs-lookup"><span data-stu-id="bc451-104">The side-by-side functionality provided allows a workflow service to be configured so that new instances of the workflow service are created using the new workflow definition, while running instances complete using the existing definition.</span></span> <span data-ttu-id="bc451-105">Este tema proporciona información general sobre la ejecución en paralelo del servicio de flujo de trabajo mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="bc451-105">This topic provides an overview of workflow service side-by-side execution using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bc451-106">Para descargar un ejemplo y ver un tutorial de vídeo de control de versiones en paralelo del servicio de flujo de trabajo, consulte Control de versiones en paralelo con un servicio de flujo de trabajo [Xamlx hospedado](https://go.microsoft.com/fwlink/?LinkId=393746)en Web .</span><span class="sxs-lookup"><span data-stu-id="bc451-106">To download a sample and watch a video walkthrough of workflow service side-by-side versioning, see [Side by Side Versioning with a Web-Hosted Xamlx Workflow Service](https://go.microsoft.com/fwlink/?LinkId=393746).</span></span>  
  
## <a name="hosting-multiple-versions-in-a-workflow-service"></a><span data-ttu-id="bc451-107">Hospedar varias versiones en un servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="bc451-107">Hosting Multiple Versions in a Workflow Service</span></span>  
 <span data-ttu-id="bc451-108"><xref:System.ServiceModel.Activities.WorkflowServiceHost> contiene dos propiedades que se pueden configurar para permitir la ejecución en paralelo de varias versiones de un flujo de trabajo: <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> y <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc451-108"><xref:System.ServiceModel.Activities.WorkflowServiceHost> contains two properties that can be configured to allow multiple versions of a workflow to execute side-by-side: <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> and <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span> <span data-ttu-id="bc451-109"><xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> contiene las versiones admitidas del servicio de flujo de trabajo y <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> se usa para identificar de forma única cada servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bc451-109"><xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> contains the supported versions of the workflow service, and <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is used to uniquely identify each workflow service.</span></span> <span data-ttu-id="bc451-110">Esto se hace asociando <xref:System.Activities.WorkflowIdentity> al servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bc451-110">This is done by associating a <xref:System.Activities.WorkflowIdentity> with the workflow service.</span></span> <span data-ttu-id="bc451-111"><xref:System.Activities.WorkflowIdentity> contiene tres elementos de información de identificación.</span><span class="sxs-lookup"><span data-stu-id="bc451-111">A <xref:System.Activities.WorkflowIdentity> contains three identifying pieces of information.</span></span> <span data-ttu-id="bc451-112"><xref:System.Activities.WorkflowIdentity.Name%2A> y <xref:System.Activities.WorkflowIdentity.Version%2A> contienen un nombre y <xref:System.Version> y son necesarios, y <xref:System.Activities.WorkflowIdentity.Package%2A> es opcional y se puede usar para especificar una cadena adicional que contiene información como el nombre del ensamblado u otra información deseada.</span><span class="sxs-lookup"><span data-stu-id="bc451-112"><xref:System.Activities.WorkflowIdentity.Name%2A> and <xref:System.Activities.WorkflowIdentity.Version%2A> contain a name and a <xref:System.Version> and are required, and <xref:System.Activities.WorkflowIdentity.Package%2A> is optional and can be used to specify an additional string containing information such as assembly name or other desired information.</span></span> <span data-ttu-id="bc451-113">Cada servicio de flujo de trabajo contenido en la colección <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> debe tener una <xref:System.Activities.WorkflowIdentity> única.</span><span class="sxs-lookup"><span data-stu-id="bc451-113">Each workflow service contained in the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection must have a unique <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="bc451-114"><xref:System.Activities.WorkflowIdentity> es único si cualquiera de sus tres propiedades son diferentes de otra <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="bc451-114">A <xref:System.Activities.WorkflowIdentity> is unique if any of its three properties are different from another <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="bc451-115">A `null` <xref:System.Activities.WorkflowIdentity> es un valor <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>permitido para , pero solo una `null` <xref:System.Activities.WorkflowIdentity>versión anterior de un servicio de flujo de trabajo puede tener un archivo .</span><span class="sxs-lookup"><span data-stu-id="bc451-115">A `null` <xref:System.Activities.WorkflowIdentity> is an allowable value for <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, but only one previous version of a workflow service may have a `null` <xref:System.Activities.WorkflowIdentity>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bc451-116">Un objeto <xref:System.Activities.WorkflowIdentity> no debe contener información de identificación personal (PII).</span><span class="sxs-lookup"><span data-stu-id="bc451-116">A <xref:System.Activities.WorkflowIdentity> should not contain any personally identifiable information (PII).</span></span> <span data-ttu-id="bc451-117"><xref:System.Activities.WorkflowIdentity> se compone de tres partes: <xref:System.Activities.WorkflowIdentity.Name%2A> (<xref:System.String>), <xref:System.Activities.WorkflowIdentity.Version%2A> (<xref:System.Version>) y <xref:System.Activities.WorkflowIdentity.Package%2A> (<xref:System.String>).</span><span class="sxs-lookup"><span data-stu-id="bc451-117"><xref:System.Activities.WorkflowIdentity> is composed of three parts: a <xref:System.Activities.WorkflowIdentity.Name%2A> (<xref:System.String>), a <xref:System.Activities.WorkflowIdentity.Version%2A> (<xref:System.Version>), and a <xref:System.Activities.WorkflowIdentity.Package%2A> (<xref:System.String>).</span></span> <span data-ttu-id="bc451-118">El runtime emite la información acerca del elemento <xref:System.Activities.WorkflowIdentity> usado para crear una instancia a cualquier servicio de seguimiento configurado en diferentes puntos del ciclo de vida de actividad.</span><span class="sxs-lookup"><span data-stu-id="bc451-118">Information about the <xref:System.Activities.WorkflowIdentity> used to create an instance is emitted to any configured tracking services at several different points of the activity life-cycle by the runtime.</span></span> <span data-ttu-id="bc451-119">El seguimiento de WF no tiene ningún mecanismo para ocultar la PII (datos de usuario confidenciales).</span><span class="sxs-lookup"><span data-stu-id="bc451-119">WF Tracking does not have any mechanism to hide PII (sensitive user data).</span></span> <span data-ttu-id="bc451-120">Por lo tanto, una instancia de <xref:System.Activities.WorkflowIdentity> no debe contener datos PII ya que el runtime los emitirá en registros de seguimiento y serán visibles para cualquiera que tenga acceso para ver los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="bc451-120">Therefore, a <xref:System.Activities.WorkflowIdentity> instance should not contain any PII data as it will be emitted by the runtime in tracking records and may be visible to anyone with access to view the tracking records.</span></span>  
  
### <a name="rules-for-hosting-multiple-versions-of-a-workflow-service"></a><span data-ttu-id="bc451-121">Reglas para hospedar varias versiones de un servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="bc451-121">Rules for Hosting Multiple Versions of a Workflow Service</span></span>  
 <span data-ttu-id="bc451-122">Cuando un usuario agrega una versión adicional a <xref:System.ServiceModel.Activities.WorkflowServiceHost>, se deben cumplir varias condiciones para que un servicio de flujo de trabajo se hospede con el mismo conjunto de puntos de conexión y descripción.</span><span class="sxs-lookup"><span data-stu-id="bc451-122">When a user adds an additional version to the <xref:System.ServiceModel.Activities.WorkflowServiceHost>, there are several conditions that must be met in order for a workflow service to be hosted with the same set of endpoints and description.</span></span> <span data-ttu-id="bc451-123">Si cualquiera de las versiones adicionales no cumple estas condiciones, <xref:System.ServiceModel.Activities.WorkflowServiceHost> produce una excepción cuando se llama a `Open`.</span><span class="sxs-lookup"><span data-stu-id="bc451-123">If any of the additional versions fail to meet these conditions, the <xref:System.ServiceModel.Activities.WorkflowServiceHost> throws an exception when `Open` is called.</span></span> <span data-ttu-id="bc451-124">Cada definición de flujo de trabajo proporcionada al host como versión adicional debe cumplir los requisitos siguientes (donde la versión principal es la definición de servicio de flujo de trabajo que se proporciona al constructor de host).</span><span class="sxs-lookup"><span data-stu-id="bc451-124">Each workflow definition provided to the host as an additional version must meet the following requirements (where the primary version is the workflow service definition that is provided to the host constructor).</span></span> <span data-ttu-id="bc451-125">La versión adicional del flujo de trabajo debe:</span><span class="sxs-lookup"><span data-stu-id="bc451-125">The additional workflow version must:</span></span>  
  
- <span data-ttu-id="bc451-126">Tenga el mismo <xref:System.ServiceModel.Activities.WorkflowService.Name%2A> que la versión principal del servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bc451-126">Have the same the <xref:System.ServiceModel.Activities.WorkflowService.Name%2A> as the primary version of the workflow service.</span></span>  
  
- <span data-ttu-id="bc451-127">No debe tener ninguna actividad <xref:System.ServiceModel.Activities.Receive> o <xref:System.ServiceModel.Activities.SendReply> en su <xref:System.ServiceModel.Activities.WorkflowService.Body%2A> que no esté en la versión principal y deben coincidir con el contrato de operación.</span><span class="sxs-lookup"><span data-stu-id="bc451-127">Must not have any <xref:System.ServiceModel.Activities.Receive> or <xref:System.ServiceModel.Activities.SendReply> activities in its <xref:System.ServiceModel.Activities.WorkflowService.Body%2A> that are not in the primary version, and they must match the operation contract.</span></span>  
  
- <span data-ttu-id="bc451-128">Tenga una <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> única.</span><span class="sxs-lookup"><span data-stu-id="bc451-128">Have a unique <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span> <span data-ttu-id="bc451-129">Una única definición de flujo de trabajo puede tener una `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc451-129">One and only one workflow definition may have a `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span>  
  
 <span data-ttu-id="bc451-130">Se permiten algunos cambios.</span><span class="sxs-lookup"><span data-stu-id="bc451-130">Some changes are permitted.</span></span> <span data-ttu-id="bc451-131">Los elementos siguientes pueden ser diferentes en las versiones:</span><span class="sxs-lookup"><span data-stu-id="bc451-131">The following items may be different between the versions:</span></span>  
  
- <span data-ttu-id="bc451-132"><xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> puede tener un nombre y un paquete diferentes que la versión principal.</span><span class="sxs-lookup"><span data-stu-id="bc451-132">The <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> may have a different Name and Package than the primary version.</span></span>  
  
- <span data-ttu-id="bc451-133">El valor de <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> puede ser diferente que el de la versión principal.</span><span class="sxs-lookup"><span data-stu-id="bc451-133">The <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> value may be different than the primary version.</span></span>  
  
- <span data-ttu-id="bc451-134"><xref:System.ServiceModel.Activities.WorkflowService.ConfigurationName%2A> puede ser diferente que el de la versión principal.</span><span class="sxs-lookup"><span data-stu-id="bc451-134">The <xref:System.ServiceModel.Activities.WorkflowService.ConfigurationName%2A> may be different than the primary version.</span></span>  
  
- <span data-ttu-id="bc451-135"><xref:System.ServiceModel.Activities.WorkflowService.ImplementedContracts%2A> puede ser diferente que el de la versión principal.</span><span class="sxs-lookup"><span data-stu-id="bc451-135">The <xref:System.ServiceModel.Activities.WorkflowService.ImplementedContracts%2A> may be different than the primary version.</span></span>  
  
### <a name="configuring-the-definitionidentity"></a><span data-ttu-id="bc451-136">Configurar DefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="bc451-136">Configuring the DefinitionIdentity</span></span>  
 <span data-ttu-id="bc451-137">Cuando se crea un servicio de <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> flujo de trabajo mediante el diseñador de flujo de trabajo, se establece mediante la ventana **Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="bc451-137">When a workflow service is created using the workflow designer, the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is set using the **Properties** window.</span></span> <span data-ttu-id="bc451-138">Haga clic fuera de la actividad raíz del servicio en el diseñador para seleccionar el servicio de flujo de trabajo y elija **Ventana de propiedades** en el menú **Ver.**</span><span class="sxs-lookup"><span data-stu-id="bc451-138">Click outside of the service’s root activity in the designer to select the workflow service, and choose **Properties Window** from the **View** menu.</span></span> <span data-ttu-id="bc451-139">Seleccione **WorkflowIdentity** en la lista desplegable que aparece junto a la propiedad <xref:System.Activities.WorkflowIdentity> **DefinitionIdentity** y, a continuación, expanda y especifique las propiedades deseadas.</span><span class="sxs-lookup"><span data-stu-id="bc451-139">Select **WorkflowIdentity** from the drop-down list that appears beside the **DefinitionIdentity** property, and then expand and specify the desired <xref:System.Activities.WorkflowIdentity> properties.</span></span> <span data-ttu-id="bc451-140">En el ejemplo <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> siguiente se <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` configura <xref:System.Activities.WorkflowIdentity.Version%2A> `1.0.0.0`con el y a de .</span><span class="sxs-lookup"><span data-stu-id="bc451-140">In the following example the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is configured with the <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` and a <xref:System.Activities.WorkflowIdentity.Version%2A> of `1.0.0.0`.</span></span> <span data-ttu-id="bc451-141"><xref:System.Activities.WorkflowIdentity.Package%2A> es opcional y en este ejemplo es `null`.</span><span class="sxs-lookup"><span data-stu-id="bc451-141"><xref:System.Activities.WorkflowIdentity.Package%2A> is optional and in this example is `null`.</span></span>  
  
 ![Captura de pantalla que muestra la propiedad DefinitionIdentity.](./media/side-by-side-versioning-in-workflowservicehost/definitionidentity-property.bmp)  
  
 <span data-ttu-id="bc451-143">Cuando un servicio de flujo de trabajo se hospeda a sí mismo, se configura <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> cuando se construye el servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bc451-143">When a workflow service is self-hosted, the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is configured when the workflow service is constructed.</span></span> <span data-ttu-id="bc451-144">En el ejemplo <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> siguiente, se configura con los mismos <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` valores <xref:System.Activities.WorkflowIdentity.Name%2A> `1.0.0.0`que el ejemplo anterior, con el y a de .</span><span class="sxs-lookup"><span data-stu-id="bc451-144">In the following example, the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is configured with the same values as the previous example, with the <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` and a <xref:System.Activities.WorkflowIdentity.Name%2A> of `1.0.0.0`.</span></span>  
  
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
  
 <span data-ttu-id="bc451-145">A <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> no es necesario, aunque solo una versión del servicio de flujo de trabajo puede tener un **valor null**<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc451-145">A <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is not required, although only one version of the workflow service may have a **null**<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bc451-146">Esto es útil si el servicio se implementó inicialmente sin una <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> configurada y, a continuación, se creó una versión actualizada.</span><span class="sxs-lookup"><span data-stu-id="bc451-146">This is useful if the service was deployed initially without a <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> configured, and then an updated version is created.</span></span>  
  
### <a name="adding-a-new-version-to-a-web-hosted-workflow-service"></a><span data-ttu-id="bc451-147">Agregar una nueva versión a un servicio de flujo de trabajo hospedado en web</span><span class="sxs-lookup"><span data-stu-id="bc451-147">Adding a New Version to a Web-hosted Workflow Service</span></span>  
 <span data-ttu-id="bc451-148">El primer paso para configurar una nueva versión de un servicio de flujo de trabajo en un servicio hospedado en web es crear una nueva carpeta en la carpeta `App_Code` que tiene el mismo nombre que el archivo de servicio.</span><span class="sxs-lookup"><span data-stu-id="bc451-148">The first step in configuring a new version of a workflow service in a web-hosted service is to create a new folder in the `App_Code` folder that has the same name as the service file.</span></span> <span data-ttu-id="bc451-149">Si el archivo `xamlx` del servicio se denomina `MortgageWorkflow.xamlx`, la carpeta se debe llamar `MortgageWorkflow`.</span><span class="sxs-lookup"><span data-stu-id="bc451-149">If the service’s `xamlx` file is named `MortgageWorkflow.xamlx`, then the folder must be named `MortgageWorkflow`.</span></span> <span data-ttu-id="bc451-150">Coloque una copia del archivo `xamlx` del servicio original en esta carpeta y asígnele un nuevo nombre, como `MortgageWorkflowV1.xamlx`.</span><span class="sxs-lookup"><span data-stu-id="bc451-150">Place a copy of the original service’s `xamlx` file into this folder and rename it to a new name, such as `MortgageWorkflowV1.xamlx`.</span></span> <span data-ttu-id="bc451-151">Realice los cambios deseados al servicio primario, actualice su <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> y después implemente el servicio.</span><span class="sxs-lookup"><span data-stu-id="bc451-151">Make the desired changes to the primary service, update its <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, and then deploy the service.</span></span> <span data-ttu-id="bc451-152">En el ejemplo siguiente se ha actualizado <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> con un <xref:System.Activities.WorkflowIdentity.Name%2A> de `MortgageWorkflow` y una <xref:System.Activities.WorkflowIdentity.Version%2A> de `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="bc451-152">In the following example the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> has been updated with a <xref:System.Activities.WorkflowIdentity.Name%2A> of `MortgageWorkflow` and a <xref:System.Activities.WorkflowIdentity.Version%2A> of `2.0.0.0`.</span></span>  
  
 ![Captura de pantalla que muestra DefinitionIdentity de WorkflowIdentity.](./media/side-by-side-versioning-in-workflowservicehost/definitionidentity-workflowidentity.bmp)  
  
 <span data-ttu-id="bc451-154">Cuando se reinicie el servicio, la versión anterior se agregará automáticamente a la colección <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> porque se encuentra en la subcarpeta `App_Code` designada.</span><span class="sxs-lookup"><span data-stu-id="bc451-154">When the service restarts, the previous version will automatically be added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection because it is located in the designated `App_Code` subfolder.</span></span> <span data-ttu-id="bc451-155">Tenga en cuenta que si la `null` <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> versión principal del servicio de flujo de trabajo tiene una versión anterior no se agregará.</span><span class="sxs-lookup"><span data-stu-id="bc451-155">Note that if the primary version of the workflow service has a `null` <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> the previous versions will not be added.</span></span> <span data-ttu-id="bc451-156">Una versión puede tener una `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, pero si hay varias versiones la versión principal no debe ser la que tenga una `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> o bien las versiones anteriores no se agregarán a la colección <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc451-156">One version may have a `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, but if there are multiple versions the primary version must not be the one with the `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> or else the previous versions will not be added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection.</span></span>  
  
### <a name="adding-a-new-version-to-a-self-hosted-workflow-service"></a><span data-ttu-id="bc451-157">Agregar una nueva versión a un servicio de flujo de trabajo autohospedado</span><span class="sxs-lookup"><span data-stu-id="bc451-157">Adding a New Version to a Self-hosted Workflow Service</span></span>  
 <span data-ttu-id="bc451-158">Al agregar una nueva versión a un servicio de flujo de trabajo autohospedado, <xref:System.ServiceModel.Activities.WorkflowServiceHost> se configura con la versión principal del servicio de flujo de trabajo y las versiones anteriores deben agregarse explícitamente a la colección <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc451-158">When adding a new version to a self-hosted workflow service, the <xref:System.ServiceModel.Activities.WorkflowServiceHost> is configured with the primary version of the workflow service, and previous versions must be explicitly added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection.</span></span> <span data-ttu-id="bc451-159">En el ejemplo siguiente, <xref:System.ServiceModel.Activities.WorkflowServiceHost> se configura con un servicio primario de flujo de trabajo que usa una definición de flujo de trabajo de `MortgageWorkflowV2` y se agrega un servicio de flujo de trabajo configurado con una definición de flujo de trabajo de `MortgageWorkflowV1` a la colección <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc451-159">In the following example, a <xref:System.ServiceModel.Activities.WorkflowServiceHost> is configured with a primary workflow service that uses a `MortgageWorkflowV2` workflow definition, and a workflow service configured with a `MortgageWorkflowV1` workflow definition is added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection.</span></span> <span data-ttu-id="bc451-160">Cada servicio de flujo de trabajo se configura con una <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> única que refleja la versión de la definición de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bc451-160">Each workflow service is configured with a unique <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> that reflects the version of the workflow definition.</span></span>  
  
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

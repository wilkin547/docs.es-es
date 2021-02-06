---
description: 'Más información sobre: <behavior> de <serviceBehaviors>'
title: <behavior> de <serviceBehaviors>
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: e34254661026ad6dcb3429ad1b381cc3e6718f27
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639541"
---
# <a name="behavior-of-servicebehaviors"></a><span data-ttu-id="53fe8-103">\<behavior> de \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="53fe8-103">\<behavior> of \<serviceBehaviors></span></span>

<span data-ttu-id="53fe8-104">El elemento `behavior` contiene una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="53fe8-104">The `behavior` element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="53fe8-105">Su `name` indiza cada comportamiento.</span><span class="sxs-lookup"><span data-stu-id="53fe8-105">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="53fe8-106">Los servicios se pueden vincular a cada comportamiento a través de este nombre mediante el `behaviorConfiguration` atributo del [\<endpoint>](endpoint-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="53fe8-106">Services can link to each behavior through this name using the `behaviorConfiguration` attribute of the [\<endpoint>](endpoint-element.md) element.</span></span> <span data-ttu-id="53fe8-107">De esta forma, los extremos pueden compartir configuraciones de comportamientos comunes sin volver a definir la configuración.</span><span class="sxs-lookup"><span data-stu-id="53fe8-107">This allows endpoints to share common behavior configurations without redefining the settings.</span></span> <span data-ttu-id="53fe8-108">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="53fe8-108">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="53fe8-109">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="53fe8-109">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53fe8-110">Los elementos de comportamiento específicos de las actividades de flujo de trabajo de Windows, como el [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) elemento, se documentan en la [ \<behavior> de \<serviceBehaviors> ](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) la página.</span><span class="sxs-lookup"><span data-stu-id="53fe8-110">Behavior elements specific to Windows Workflow activities, such as the [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) element, are documented in the [\<behavior> of \<serviceBehaviors>](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) page.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="53fe8-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53fe8-111">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <serviceBehaviors>
       <behavior name="String" />
    </serviceBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53fe8-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="53fe8-112">Attributes and Elements</span></span>  

 <span data-ttu-id="53fe8-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="53fe8-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53fe8-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="53fe8-114">Attributes</span></span>  
  
|<span data-ttu-id="53fe8-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="53fe8-115">Attribute</span></span>|<span data-ttu-id="53fe8-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="53fe8-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53fe8-117">name</span><span class="sxs-lookup"><span data-stu-id="53fe8-117">name</span></span>|<span data-ttu-id="53fe8-118">Una cadena única que contiene el nombre de la configuración del comportamiento.</span><span class="sxs-lookup"><span data-stu-id="53fe8-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="53fe8-119">Este valor es una cadena definida por el usuario que debe ser única, ya que actúa como cadena de identificación del elemento.</span><span class="sxs-lookup"><span data-stu-id="53fe8-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="53fe8-120">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="53fe8-120">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="53fe8-121">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="53fe8-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53fe8-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="53fe8-122">Child Elements</span></span>  
  
|<span data-ttu-id="53fe8-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="53fe8-123">Element</span></span>|<span data-ttu-id="53fe8-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="53fe8-124">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-element.md)|<span data-ttu-id="53fe8-125">Contiene los datos de configuración para DataContractSerializer.</span><span class="sxs-lookup"><span data-stu-id="53fe8-125">Contains configuration data for the DataContractSerializer.</span></span>|  
|[\<persistenceProvider>](persistenceprovider.md)|<span data-ttu-id="53fe8-126">Especifica el tipo de la implementación de proveedor de persistencia que se va a usar, así como el tiempo de espera que se va a utilizar en las operaciones de persistencia.</span><span class="sxs-lookup"><span data-stu-id="53fe8-126">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>|  
|[\<routing>](routing-of-servicebehavior.md)|<span data-ttu-id="53fe8-127">Proporciona acceso en tiempo de ejecución al servicio de enrutamiento para permitir la modificación dinámica de la configuración del enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="53fe8-127">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>|  
|[\<serviceAuthenticationManager>](serviceauthenticationmanager.md)|<span data-ttu-id="53fe8-128">Proporciona un elemento de configuración del flujo de trabajo que establece la validez de una transmisión, mensaje o autor en el nivel del servicio.</span><span class="sxs-lookup"><span data-stu-id="53fe8-128">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>|  
|[\<serviceAuthorization>](serviceauthorization-element.md)|<span data-ttu-id="53fe8-129">Especifica valores que autorizan que el acceso repare las operaciones.</span><span class="sxs-lookup"><span data-stu-id="53fe8-129">Specifies settings that authorize access to service operations.</span></span>|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="53fe8-130">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="53fe8-130">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>|  
|[\<serviceDebug>](servicedebug.md)|<span data-ttu-id="53fe8-131">Especifica las características de depuración y de información de ayuda para un servicio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="53fe8-131">Specifies debugging and help information features for a Windows Communication Foundation (WCF) service.</span></span>|  
|[\<serviceDiscovery>](servicediscovery.md)|<span data-ttu-id="53fe8-132">Especifica la detectabilidad de extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="53fe8-132">Specifies the discoverability of service endpoints.</span></span>|  
|[\<serviceMetadata>](servicemetadata.md)|<span data-ttu-id="53fe8-133">Especifica la publicación de metadatos e información asociada del servicio.</span><span class="sxs-lookup"><span data-stu-id="53fe8-133">Specifies the publication of service metadata and associated information.</span></span>|  
|[\<serviceSecurityAudit>](servicesecurityaudit.md)|<span data-ttu-id="53fe8-134">Especifica valores que habilitan la auditoría de eventos de seguridad durante las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="53fe8-134">Specifies settings that enable auditing of security events during service operations.</span></span>|  
|[\<serviceThrottling>](servicethrottling.md)|<span data-ttu-id="53fe8-135">Especifica el mecanismo de limitación de un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="53fe8-135">Specifies the throttling mechanism of a WCF service.</span></span>|  
|[\<serviceTimeouts>](servicetimeouts.md)|<span data-ttu-id="53fe8-136">Especifica el tiempo de espera para un servicio.</span><span class="sxs-lookup"><span data-stu-id="53fe8-136">Specifies the timeout for a service.</span></span>|  
|[\<workflowRuntime>](workflowruntime.md)|<span data-ttu-id="53fe8-137">Especifica la configuración de una instancia de WorkflowRuntime para hospedar servicios WCF basados en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="53fe8-137">Specifies settings for an instance of WorkflowRuntime for hosting workflow-based WCF services.</span></span>|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="53fe8-138">Habilita la recuperación de información de direcciones de metadatos de los encabezados de mensajes de solicitud.</span><span class="sxs-lookup"><span data-stu-id="53fe8-138">Enables the retrieval of metadata address information from the request message headers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="53fe8-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="53fe8-139">Parent Elements</span></span>  
  
|<span data-ttu-id="53fe8-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="53fe8-140">Element</span></span>|<span data-ttu-id="53fe8-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="53fe8-141">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors.md)|<span data-ttu-id="53fe8-142">Colección de elementos de comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="53fe8-142">A collection of service behavior elements.</span></span>|

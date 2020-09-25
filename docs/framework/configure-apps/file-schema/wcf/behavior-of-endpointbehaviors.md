---
title: <behavior> de <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: d191b968e1c3fd1db0837ba7e03f210a1b00062d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201504"
---
# <a name="behavior-of-endpointbehaviors"></a><span data-ttu-id="9102e-102">\<behavior> de \<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="9102e-102">\<behavior> of \<endpointBehaviors></span></span>

<span data-ttu-id="9102e-103">El elemento `behavior` contiene una colección de valores para el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9102e-103">The `behavior` element contains a collection of settings for the behavior of an endpoint.</span></span> <span data-ttu-id="9102e-104">Su `name` indiza cada comportamiento.</span><span class="sxs-lookup"><span data-stu-id="9102e-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="9102e-105">Los puntos de conexión se pueden vincular a cada comportamiento a través de este nombre.</span><span class="sxs-lookup"><span data-stu-id="9102e-105">Endpoints can link to each behavior through this name.</span></span> <span data-ttu-id="9102e-106">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="9102e-106">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9102e-107">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="9102e-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="9102e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9102e-108">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9102e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9102e-109">Attributes and Elements</span></span>  

 <span data-ttu-id="9102e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9102e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9102e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9102e-111">Attributes</span></span>  
  
|<span data-ttu-id="9102e-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="9102e-112">Attribute</span></span>|<span data-ttu-id="9102e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9102e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9102e-114">name</span><span class="sxs-lookup"><span data-stu-id="9102e-114">name</span></span>|<span data-ttu-id="9102e-115">Una cadena única que contiene el nombre de la configuración del comportamiento.</span><span class="sxs-lookup"><span data-stu-id="9102e-115">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="9102e-116">Este valor es una cadena definida por el usuario que debe ser única, ya que actúa como cadena de identificación del elemento.</span><span class="sxs-lookup"><span data-stu-id="9102e-116">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="9102e-117">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="9102e-117">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9102e-118">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="9102e-118">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9102e-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9102e-119">Child Elements</span></span>  
  
|<span data-ttu-id="9102e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="9102e-120">Element</span></span>|<span data-ttu-id="9102e-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="9102e-121">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="9102e-122">Especifica las credenciales usadas para autenticar el cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="9102e-122">Specifies the credentials used to authenticate the client to a service.</span></span>|  
|[\<callbackDebug>](callbackdebug.md)|<span data-ttu-id="9102e-123">Especifica la depuración del servicio para un objeto de devolución de llamada de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9102e-123">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>|  
|[\<callbackTimeouts>](callbacktimeouts.md)|<span data-ttu-id="9102e-124">Especifica el tiempo de espera para la devolución de la llamada del cliente.</span><span class="sxs-lookup"><span data-stu-id="9102e-124">Specifies the timeout for the client callback.</span></span>|  
|[\<clientVia>](clientvia.md)|<span data-ttu-id="9102e-125">Especifica la ruta que un mensaje debe tomar.</span><span class="sxs-lookup"><span data-stu-id="9102e-125">Specifies the route a message should take.</span></span>|  
|[\<dataContractSerializer>](datacontractserializer.md)|<span data-ttu-id="9102e-126">Contiene los datos de configuración para DataContractSerializer.</span><span class="sxs-lookup"><span data-stu-id="9102e-126">Contains configuration data for the DataContractSerializer.</span></span>|  
|[\<dispatcherSynchronization>](dispatchersynchronization.md)|<span data-ttu-id="9102e-127">Especifica un comportamiento del extremo que permite que un servicio envíe respuestas de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="9102e-127">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>|  
|[\<enableWebScript>](enablewebscript.md)|<span data-ttu-id="9102e-128">Habilita el comportamiento del extremo que permite utilizar el servicio de las páginas web de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="9102e-128">Enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span> <span data-ttu-id="9102e-129">El comportamiento solo se debe usar junto con el \<webHttpBinding> enlace estándar o el \<webMessageEncoding> elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="9102e-129">The behavior should only be used in conjunction with either the \<webHttpBinding> standard binding, or the \<webMessageEncoding> binding element.</span></span>|  
|[\<endpointDiscovery>](endpointdiscovery.md)|<span data-ttu-id="9102e-130">Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="9102e-130">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
|[\<soapProcessing>](soapprocessing.md)|<span data-ttu-id="9102e-131">Define el comportamiento del punto de conexión de cliente usado para serializar entre distintos tipos de enlaces y versiones de mensajes.</span><span class="sxs-lookup"><span data-stu-id="9102e-131">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>|  
|[\<synchronousReceive>](synchronousreceive-element.md)|<span data-ttu-id="9102e-132">Especifica el comportamiento de tiempo de ejecución para recibir los mensajes en una aplicación de servicio o de cliente.</span><span class="sxs-lookup"><span data-stu-id="9102e-132">Specifies run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="9102e-133">No tiene ningún atributo o elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="9102e-133">It does not have any attributes or child elements.</span></span>|  
|[\<transactedBatching>](transactedbatching.md)|<span data-ttu-id="9102e-134">Especifica si el procesamiento por lotes de la transacción se admite para las operaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="9102e-134">Specifies whether transaction batching is supported for receive operations.</span></span>|  
|[\<webHttp>](webhttp.md)|<span data-ttu-id="9102e-135">Especifica WebHttpBehavior en un punto de conexión a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="9102e-135">Specifies the WebHttpBehavior on an endpoint through configuration.</span></span> <span data-ttu-id="9102e-136">Este comportamiento, cuando se usa junto con el \<webHttpBinding> enlace estándar, habilita el modelo de programación web para un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="9102e-136">This behavior, when used in conjunction with the \<webHttpBinding> standard binding, enables the Web programming model for a WCF service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9102e-137">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9102e-137">Parent Elements</span></span>  
  
|<span data-ttu-id="9102e-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="9102e-138">Element</span></span>|<span data-ttu-id="9102e-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="9102e-139">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|<span data-ttu-id="9102e-140">Una colección de elementos de comportamiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="9102e-140">A collection of endpoint behavior elements.</span></span>|

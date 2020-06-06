---
title: <system.serviceModel>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
ms.openlocfilehash: 2125ce00b0e23f2e93ff251549f9c1276892b16b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399453"
---
# \<system.serviceModel>
<span data-ttu-id="e8370-102">Esta sección de configuración contiene todos los elementos de configuración de ServiceModel Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e8370-102">This configuration section contains all the Windows Communication Foundation (WCF) ServiceModel configuration elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.serviceModel>**  
  
## <a name="syntax"></a><span data-ttu-id="e8370-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8370-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <behaviors>
  </behaviors>
  <bindings>
  </bindings>
  <client>
  </client>
  <comContracts>
  </comContracts>
  <commonBehaviors>
  </commonBehaviors>
  <diagnostics>
  </diagnostics>
  <extensions>
  </extensions>
  <protocolMapping>
  </protocolMapping>
  <routing>
  </routing>
  <serviceHostingEnvironment>
  </serviceHostingEnvironment>
  <services>
  </services>
  <standardEndpoints>
  </standardEndpoints>
  <tracking>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8370-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e8370-104">Attributes and Elements</span></span>  
 <span data-ttu-id="e8370-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e8370-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8370-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="e8370-106">Attributes</span></span>  
 <span data-ttu-id="e8370-107">None</span><span class="sxs-lookup"><span data-stu-id="e8370-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e8370-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e8370-108">Child Elements</span></span>  
  
|<span data-ttu-id="e8370-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8370-109">Element</span></span>|<span data-ttu-id="e8370-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8370-110">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviors>](behaviors.md)|<span data-ttu-id="e8370-111">Esta sección define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="e8370-111">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="e8370-112">Cada colección define los elementos de comportamiento utilizados respectivamente por extremos y servicios.</span><span class="sxs-lookup"><span data-stu-id="e8370-112">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="e8370-113">Su atributo de `name` único identifica cada elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="e8370-113">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[\<bindings>](bindings.md)|<span data-ttu-id="e8370-114">Esta sección contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="e8370-114">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="e8370-115">Su `name` único identifica cada entrada.</span><span class="sxs-lookup"><span data-stu-id="e8370-115">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="e8370-116">Los servicios usan los enlaces vinculándose a ellos mediante `name`.</span><span class="sxs-lookup"><span data-stu-id="e8370-116">Services use bindings by linking them using the `name`.</span></span>|  
|[\<client>](client.md)|<span data-ttu-id="e8370-117">Esta sección contiene una lista de extremos que usa un cliente para conectarse a un servicio.</span><span class="sxs-lookup"><span data-stu-id="e8370-117">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[\<comContracts>](comcontracts.md)|<span data-ttu-id="e8370-118">Esta sección define contratos COM habilitados para WCF e interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="e8370-118">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[\<commonBehaviors>](commonbehaviors.md)|<span data-ttu-id="e8370-119">Esta sección solo se puede definir en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="e8370-119">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="e8370-120">Define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="e8370-120">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="e8370-121">Cada colección define los elementos de comportamiento utilizados por todos los puntos de conexión y servicios de WCF en el equipo, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e8370-121">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="e8370-122">Si un comportamiento se define en las secciones `<commonBehaviors>` y `<behaviors>`, el comportamiento en la sección \<behaviors> tendrá preferencia.</span><span class="sxs-lookup"><span data-stu-id="e8370-122">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="e8370-123">Esta sección contiene la configuración para las características de diagnóstico de WCF.</span><span class="sxs-lookup"><span data-stu-id="e8370-123">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="e8370-124">El usuario puede habilitar/deshabilitar el seguimiento, contadores de rendimiento y el proveedor de WMI, y puede agregar filtros de mensajes personalizados.</span><span class="sxs-lookup"><span data-stu-id="e8370-124">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[\<extensions>](extensions-section.md)|<span data-ttu-id="e8370-125">Esta sección contiene una colección de extensiones, que permiten al usuario crear los enlaces definidos por el usuario, comportamientos y otros aspectos de las extensiones.</span><span class="sxs-lookup"><span data-stu-id="e8370-125">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[\<protocolMapping>](protocolmapping.md)|<span data-ttu-id="e8370-126">En esta sección se define un conjunto de asignación de protocolos predeterminados entre los esquemas de protocolos de transporte (ej., http, net.tcp, net.pipe, etc.) y enlaces WCF.</span><span class="sxs-lookup"><span data-stu-id="e8370-126">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[\<routing>](routing.md)|<span data-ttu-id="e8370-127">En esta sección se define un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="e8370-127">This section defines a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="e8370-128">Esta sección define para qué tipo el entorno de host de servicio crea instancias de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="e8370-128">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="e8370-129">Si esta sección está vacía, se usa el tipo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e8370-129">If this section is empty, the default type is used.</span></span>|  
|[\<services>](services.md)|<span data-ttu-id="e8370-130">Esta sección contiene una colección de servicios.</span><span class="sxs-lookup"><span data-stu-id="e8370-130">The section contains a collection of services.</span></span> <span data-ttu-id="e8370-131">Para cada servicio definido en el ensamblado, este elemento contiene un elemento `service` que especifica la configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="e8370-131">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="e8370-132">Esta sección define una colección de extremos estándar, que son los extremos preconfigurados reutilizables.</span><span class="sxs-lookup"><span data-stu-id="e8370-132">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="e8370-133">Un punto de conexión estándar tendrá uno o más atributos de la dirección, el enlace y el contrato establecidos en un valor fijo.</span><span class="sxs-lookup"><span data-stu-id="e8370-133">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="e8370-134">Por ejemplo, en el punto de conexión de la detección el contrato es fijo.</span><span class="sxs-lookup"><span data-stu-id="e8370-134">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="e8370-135">También puede usar los puntos de conexión estándar para extender el punto de conexión de servicio con nuevas propiedades similares a la definición de enlaces personalizados.</span><span class="sxs-lookup"><span data-stu-id="e8370-135">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|
|[\<tracking>](tracking-of-wcf.md)|<span data-ttu-id="e8370-136">En esta sección se define la configuración de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e8370-136">This section defines tracking settings for a workflow service.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e8370-137">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e8370-137">Parent Elements</span></span>  
  
|<span data-ttu-id="e8370-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8370-138">Element</span></span>|<span data-ttu-id="e8370-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8370-139">Description</span></span>|  
|-------------|-----------------|  
|\<configuration>|<span data-ttu-id="e8370-140">El elemento raíz para todos los elementos de configuración en un archivo de configuración .NET.</span><span class="sxs-lookup"><span data-stu-id="e8370-140">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8370-141">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e8370-141">Remarks</span></span>  
 <span data-ttu-id="e8370-142">WCF no agrega elementos a las secciones de configuración de otros productos.</span><span class="sxs-lookup"><span data-stu-id="e8370-142">WCF does not add elements to the configuration sections of other products.</span></span>  
  
 <span data-ttu-id="e8370-143">Los servicios WCF se definen en la `services` sección del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e8370-143">WCF services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="e8370-144">Un ensamblado puede contener cualquier número de servicios.</span><span class="sxs-lookup"><span data-stu-id="e8370-144">An assembly can contain any number of services.</span></span> <span data-ttu-id="e8370-145">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="e8370-145">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="e8370-146">La sección y su contenido definen el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="e8370-146">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="e8370-147">Sólo se requiere el atributo de `name` del servicio.</span><span class="sxs-lookup"><span data-stu-id="e8370-147">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="e8370-148">De forma predeterminada, el nombre de un servicio describe el tipo CLR subyacente usado para implementar un servicio; sin embargo, puede cambiar la propiedad ConfigurationName en <xref:System.ServiceModel.ServiceContractAttribute> para invalidar el requisito de tipo de CLR.</span><span class="sxs-lookup"><span data-stu-id="e8370-148">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="e8370-149">El atributo `behaviorConfiguration` es opcional.</span><span class="sxs-lookup"><span data-stu-id="e8370-149">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="e8370-150">Identifica el comportamiento del servicio usado por un servicio.</span><span class="sxs-lookup"><span data-stu-id="e8370-150">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="e8370-151">El comportamiento especificado por este atributo debe vincularse a un comportamiento del servicio definido en el ámbito del mismo archivo de configuración (es decir, el mismo archivo o un archivo primario).</span><span class="sxs-lookup"><span data-stu-id="e8370-151">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="e8370-152">Cada servicio expone uno o más puntos de conexión definidos en un elemento `endpoint`.</span><span class="sxs-lookup"><span data-stu-id="e8370-152">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="e8370-153">Cada extremo tiene su propia dirección y enlace.</span><span class="sxs-lookup"><span data-stu-id="e8370-153">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="e8370-154">Todos los enlaces usados dentro del archivo de configuración se deben definir en el ámbito del archivo.</span><span class="sxs-lookup"><span data-stu-id="e8370-154">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="e8370-155">Los enlaces se vinculan a los puntos de conexión a través de la combinación de los atributos `name` y `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="e8370-155">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="e8370-156">El atributo de `binding` define la sección en que está definido el enlace.</span><span class="sxs-lookup"><span data-stu-id="e8370-156">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="e8370-157">El atributo `bindingConfiguration` define el enlace configurado que se usa en la sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="e8370-157">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="e8370-158">Una sección de enlaces puede definir varios enlaces configurados.</span><span class="sxs-lookup"><span data-stu-id="e8370-158">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8370-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8370-159">Example</span></span>  
 <span data-ttu-id="e8370-160">Esto es un ejemplo de un archivo de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="e8370-160">This is an example of a WCF configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors>
      <!-- List of Behaviors -->
    </behaviors>
    <client>
      <!-- List of Endpoints -->
    </client>
    <diagnostics wmiProviderEnabled="false"
                 performanceCountersEnabled="false"
                 tracingEnabled="false">
    </diagnostics>
    <serviceHostingEnvironment>
      <!-- List of entries -->
    </serviceHostingEnvironment>
    <comContracts>
      <!-- List of COM+ Contracts -->
    </comContracts>
    <services>
      <!-- List of Services -->
    </services>
    <bindings>
      <!-- List of Bindings -->
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="e8370-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8370-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>

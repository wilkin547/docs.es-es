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
ms.openlocfilehash: 4fa6916437bb569029efe270ba8296703d89c539
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938915"
---
# <a name="systemservicemodel"></a><span data-ttu-id="6c9f9-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6c9f9-102">\<system.serviceModel></span></span>
<span data-ttu-id="6c9f9-103">Esta sección de configuración contiene todos los elementos de configuración de ServiceModel Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6c9f9-103">This configuration section contains all the Windows Communication Foundation (WCF) ServiceModel configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c9f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c9f9-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c9f9-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6c9f9-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6c9f9-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c9f9-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="6c9f9-107">Attributes</span></span>  
 <span data-ttu-id="6c9f9-108">None</span><span class="sxs-lookup"><span data-stu-id="6c9f9-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6c9f9-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6c9f9-109">Child Elements</span></span>  
  
|<span data-ttu-id="6c9f9-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c9f9-110">Element</span></span>|<span data-ttu-id="6c9f9-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6c9f9-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c9f9-112">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="6c9f9-112">\<behaviors></span></span>](behaviors.md)|<span data-ttu-id="6c9f9-113">Esta sección define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-113">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="6c9f9-114">Cada colección define los elementos de comportamiento utilizados respectivamente por extremos y servicios.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-114">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="6c9f9-115">Su atributo de `name` único identifica cada elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-115">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[<span data-ttu-id="6c9f9-116">\<bindings></span><span class="sxs-lookup"><span data-stu-id="6c9f9-116">\<bindings></span></span>](bindings.md)|<span data-ttu-id="6c9f9-117">Esta sección contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-117">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="6c9f9-118">Su `name` único identifica cada entrada.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-118">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="6c9f9-119">Los servicios usan los enlaces vinculándose a ellos mediante `name`.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-119">Services use bindings by linking them using the `name`.</span></span>|  
|[<span data-ttu-id="6c9f9-120">\<client></span><span class="sxs-lookup"><span data-stu-id="6c9f9-120">\<client></span></span>](client.md)|<span data-ttu-id="6c9f9-121">Esta sección contiene una lista de extremos que usa un cliente para conectarse a un servicio.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-121">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[<span data-ttu-id="6c9f9-122">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="6c9f9-122">\<comContracts></span></span>](comcontracts.md)|<span data-ttu-id="6c9f9-123">Esta sección define contratos COM habilitados para WCF e interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-123">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[<span data-ttu-id="6c9f9-124">\<commonBehaviors></span><span class="sxs-lookup"><span data-stu-id="6c9f9-124">\<commonBehaviors></span></span>](commonbehaviors.md)|<span data-ttu-id="6c9f9-125">Esta sección solo se puede definir en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-125">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="6c9f9-126">Define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-126">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="6c9f9-127">Cada colección define los elementos de comportamiento utilizados por todos los puntos de conexión y servicios de WCF en el equipo, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-127">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="6c9f9-128">Si se define un comportamiento en `<commonBehaviors>` las secciones y `<behaviors>` , el comportamiento de la \<sección Behaviors > tiene preferencia.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-128">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[<span data-ttu-id="6c9f9-129">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="6c9f9-129">\<diagnostics></span></span>](diagnostics.md)|<span data-ttu-id="6c9f9-130">Esta sección contiene la configuración para las características de diagnóstico de WCF.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-130">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="6c9f9-131">El usuario puede habilitar/deshabilitar el seguimiento, contadores de rendimiento y el proveedor de WMI, y puede agregar filtros de mensajes personalizados.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-131">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[<span data-ttu-id="6c9f9-132">\<extensions></span><span class="sxs-lookup"><span data-stu-id="6c9f9-132">\<extensions></span></span>](extensions-section.md)|<span data-ttu-id="6c9f9-133">Esta sección contiene una colección de extensiones, que permiten al usuario crear los enlaces definidos por el usuario, comportamientos y otros aspectos de las extensiones.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-133">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[<span data-ttu-id="6c9f9-134">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="6c9f9-134">\<protocolMapping></span></span>](protocolmapping.md)|<span data-ttu-id="6c9f9-135">En esta sección se define un conjunto de asignaciones de protocolos predeterminados entre los esquemas de protocolo de transporte (por ejemplo, http, net. TCP, net. Pipe, etc.) y los enlaces de WCF.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-135">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[<span data-ttu-id="6c9f9-136">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="6c9f9-136">\<routing></span></span>](routing.md)|<span data-ttu-id="6c9f9-137">En esta sección se define un conjunto de filtros de enrutamiento, que determinan el tipo<xref:System.ServiceModel.Dispatcher.MessageFilter> de Windows Communication Foundation (WCF) que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que enviar mensajes cuando se filtrar coincidencias.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-137">This section defines a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[<span data-ttu-id="6c9f9-138">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="6c9f9-138">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="6c9f9-139">Esta sección define para qué tipo el entorno de host de servicio crea instancias de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-139">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="6c9f9-140">Si esta sección está vacía, se usa el tipo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-140">If this section is empty, the default type is used.</span></span>|  
|[<span data-ttu-id="6c9f9-141">\<services></span><span class="sxs-lookup"><span data-stu-id="6c9f9-141">\<services></span></span>](services.md)|<span data-ttu-id="6c9f9-142">Esta sección contiene una colección de servicios.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-142">The section contains a collection of services.</span></span> <span data-ttu-id="6c9f9-143">Para cada servicio definido en el ensamblado, este elemento contiene un elemento `service` que especifica la configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-143">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[<span data-ttu-id="6c9f9-144">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="6c9f9-144">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="6c9f9-145">Esta sección define una colección de extremos estándar, que son los extremos preconfigurados reutilizables.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-145">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="6c9f9-146">Un punto de conexión estándar tendrá uno o más atributos de la dirección, el enlace y el contrato establecidos en un valor fijo.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-146">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="6c9f9-147">Por ejemplo, en el punto de conexión de la detección el contrato es fijo.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-147">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="6c9f9-148">También puede usar los puntos de conexión estándar para extender el punto de conexión de servicio con nuevas propiedades similares a la definición de enlaces personalizados.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-148">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|
|[<span data-ttu-id="6c9f9-149">\<tracking></span><span class="sxs-lookup"><span data-stu-id="6c9f9-149">\<tracking></span></span>](tracking-of-wcf.md)|<span data-ttu-id="6c9f9-150">En esta sección se define la configuración de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-150">This section defines tracking settings for a workflow service.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6c9f9-151">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6c9f9-151">Parent Elements</span></span>  
  
|<span data-ttu-id="6c9f9-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c9f9-152">Element</span></span>|<span data-ttu-id="6c9f9-153">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6c9f9-153">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c9f9-154">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6c9f9-154">\<configuration></span></span>|<span data-ttu-id="6c9f9-155">El elemento raíz para todos los elementos de configuración en un archivo de configuración .NET.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-155">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c9f9-156">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6c9f9-156">Remarks</span></span>  
 <span data-ttu-id="6c9f9-157">WCF no agrega elementos a las secciones de configuración de otros productos.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-157">WCF does not add elements to the configuration sections of other products.</span></span>  
  
 <span data-ttu-id="6c9f9-158">Los servicios WCF se definen en `services` la sección del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-158">WCF services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="6c9f9-159">Un ensamblado puede contener cualquier número de servicios.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-159">An assembly can contain any number of services.</span></span> <span data-ttu-id="6c9f9-160">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-160">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="6c9f9-161">La sección y su contenido definen el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-161">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="6c9f9-162">Sólo se requiere el atributo de `name` del servicio.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-162">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="6c9f9-163">De forma predeterminada, el nombre de un servicio describe el tipo CLR subyacente usado para implementar un servicio; sin embargo, puede cambiar la propiedad ConfigurationName en <xref:System.ServiceModel.ServiceContractAttribute> para invalidar el requisito de tipo de CLR.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-163">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="6c9f9-164">El atributo `behaviorConfiguration` es opcional.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-164">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="6c9f9-165">Identifica el comportamiento del servicio usado por un servicio.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-165">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="6c9f9-166">El comportamiento especificado por este atributo debe vincularse a un comportamiento del servicio definido en el ámbito del mismo archivo de configuración (es decir, el mismo archivo o un archivo primario).</span><span class="sxs-lookup"><span data-stu-id="6c9f9-166">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="6c9f9-167">Cada servicio expone uno o más puntos de conexión definidos en un elemento `endpoint`.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-167">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="6c9f9-168">Cada extremo tiene su propia dirección y enlace.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-168">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="6c9f9-169">Todos los enlaces usados dentro del archivo de configuración se deben definir en el ámbito del archivo.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-169">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="6c9f9-170">Los enlaces se vinculan a los puntos de conexión a través de la combinación de los atributos `name` y `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-170">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="6c9f9-171">El atributo de `binding` define la sección en que está definido el enlace.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-171">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="6c9f9-172">El atributo `bindingConfiguration` define el enlace configurado que se usa en la sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-172">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="6c9f9-173">Una sección de enlaces puede definir varios enlaces configurados.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-173">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c9f9-174">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c9f9-174">Example</span></span>  
 <span data-ttu-id="6c9f9-175">Esto es un ejemplo de un archivo de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="6c9f9-175">This is an example of a WCF configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6c9f9-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c9f9-176">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>

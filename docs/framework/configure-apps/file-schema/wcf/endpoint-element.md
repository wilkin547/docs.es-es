---
title: elemento de &lt;extremo&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c466d7f7f00d7fd2358f0d5d71c0b705f316f66f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltendpointgt-element"></a><span data-ttu-id="18d15-102">elemento de &lt;extremo&gt;</span><span class="sxs-lookup"><span data-stu-id="18d15-102">&lt;endpoint&gt; element</span></span>
<span data-ttu-id="18d15-103">Especifica enlace, contrato y propiedades de dirección para un punto de conexión de servicio, que se utiliza para exponer los servicios.</span><span class="sxs-lookup"><span data-stu-id="18d15-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
 <span data-ttu-id="18d15-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="18d15-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="18d15-105">\<servicio ></span><span class="sxs-lookup"><span data-stu-id="18d15-105">\<service></span></span>  
<span data-ttu-id="18d15-106">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="18d15-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18d15-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18d15-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"  
   behaviorConfiguration="String"  
   binding="String"  
   bindingConfiguration="String"  
   bindingName="String"  
   bindingNamespace="String"  
   contract="String"  
   endpointConfiguration="String"   isSystemEndpoint="Boolean"   kind="String"   listenUriMode="Explicit/Unique"  
   listenUri="Uri"  
</endpoint>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18d15-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="18d15-108">Attributes and Elements</span></span>  
 <span data-ttu-id="18d15-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="18d15-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18d15-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="18d15-110">Attributes</span></span>  
  
|<span data-ttu-id="18d15-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="18d15-111">Attribute</span></span>|<span data-ttu-id="18d15-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="18d15-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="18d15-113">address</span><span class="sxs-lookup"><span data-stu-id="18d15-113">address</span></span>|<span data-ttu-id="18d15-114">Una cadena que contiene la dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="18d15-114">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="18d15-115">La dirección se puede especificar como una dirección absoluta o relativa.</span><span class="sxs-lookup"><span data-stu-id="18d15-115">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="18d15-116">Si se proporciona una dirección relativa, se espera que el host proporcione una dirección base adecuada para el esquema de transporte usado en el enlace.</span><span class="sxs-lookup"><span data-stu-id="18d15-116">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="18d15-117">Si no se configura una dirección, se supone que la dirección base es la dirección para ese extremo.</span><span class="sxs-lookup"><span data-stu-id="18d15-117">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="18d15-118">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="18d15-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="18d15-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="18d15-119">behaviorConfiguration</span></span>|<span data-ttu-id="18d15-120">Una cadena que contiene el nombre del comportamiento que se va a utilizar en el extremo.</span><span class="sxs-lookup"><span data-stu-id="18d15-120">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="18d15-121">enlace</span><span class="sxs-lookup"><span data-stu-id="18d15-121">binding</span></span>|<span data-ttu-id="18d15-122">Atributo de cadena necesario que especifica el tipo de enlace que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="18d15-122">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="18d15-123">El tipo debe tener una sección de configuración registrada para que se haga referencia al mismo.</span><span class="sxs-lookup"><span data-stu-id="18d15-123">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="18d15-124">El tipo es el registrado por el nombre de sección, en lugar de por el nombre de tipo del enlace.</span><span class="sxs-lookup"><span data-stu-id="18d15-124">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="18d15-125">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="18d15-125">bindingConfiguration</span></span>|<span data-ttu-id="18d15-126">Una cadena que especifica el nombre obligatorio del enlace que se utilizará cuando se creen las instancias del extremo.</span><span class="sxs-lookup"><span data-stu-id="18d15-126">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="18d15-127">El nombre de enlace debe estar en el ámbito en el punto definido del extremo.</span><span class="sxs-lookup"><span data-stu-id="18d15-127">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="18d15-128">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="18d15-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="18d15-129">Este atributo se utiliza junto con `binding` para hacer referencia a una configuración de enlace concreta en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="18d15-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="18d15-130">Establezca este atributo si está intentando utilizar un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="18d15-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="18d15-131">De lo contrario, puede producirse una excepción.</span><span class="sxs-lookup"><span data-stu-id="18d15-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="18d15-132">bindingName</span><span class="sxs-lookup"><span data-stu-id="18d15-132">bindingName</span></span>|<span data-ttu-id="18d15-133">Una cadena que especifica el nombre completo único del enlace para la exportación de la definición a través de WSDL.</span><span class="sxs-lookup"><span data-stu-id="18d15-133">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="18d15-134">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="18d15-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="18d15-135">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="18d15-135">bindingNamespace</span></span>|<span data-ttu-id="18d15-136">Una cadena que especifica el nombre completo del espacio de nombres del enlace para la exportación de la definición a través de WSDL.</span><span class="sxs-lookup"><span data-stu-id="18d15-136">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="18d15-137">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="18d15-137">The default is an empty string.</span></span>|  
|<span data-ttu-id="18d15-138">contrato</span><span class="sxs-lookup"><span data-stu-id="18d15-138">contract</span></span>|<span data-ttu-id="18d15-139">Una cadena que indica qué contrato está exponiendo este extremo.</span><span class="sxs-lookup"><span data-stu-id="18d15-139">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="18d15-140">El ensamblado debe implementar el tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="18d15-140">The assembly must implement the contract type.</span></span> <span data-ttu-id="18d15-141">Si una implementación de servicio implementa un tipo de contrato único, entonces se puede omitir esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="18d15-141">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="18d15-142">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="18d15-142">The default is an empty string.</span></span>|  
|<span data-ttu-id="18d15-143">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="18d15-143">endpointConfiguration</span></span>|<span data-ttu-id="18d15-144">Cadena que especifica el nombre del extremo estándar establecido por el atributo `kind`, que hace referencia a la información de configuración adicional de este extremo estándar.</span><span class="sxs-lookup"><span data-stu-id="18d15-144">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="18d15-145">El mismo nombre se debe definir en la sección `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="18d15-145">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="18d15-146">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="18d15-146">isSystemEndpoint</span></span>|<span data-ttu-id="18d15-147">Valor booleano que especifica si un extremo es un extremo de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="18d15-147">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="18d15-148">kind</span><span class="sxs-lookup"><span data-stu-id="18d15-148">kind</span></span>|<span data-ttu-id="18d15-149">Cadena que especifica el tipo de extremo estándar aplicado.</span><span class="sxs-lookup"><span data-stu-id="18d15-149">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="18d15-150">El tipo se debe registrar en la sección `<extensions>` o en machine.config. Si no se especifica nada, se crea un extremo de servicio común.</span><span class="sxs-lookup"><span data-stu-id="18d15-150">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="18d15-151">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="18d15-151">listenUriMode</span></span>|<span data-ttu-id="18d15-152">Especifica cómo el transporte trata el `ListenUri` proporcionado para el servicio en el que se realizan escuchas.</span><span class="sxs-lookup"><span data-stu-id="18d15-152">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="18d15-153">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="18d15-153">Valid values are</span></span><br /><br /> <span data-ttu-id="18d15-154">-Explícita</span><span class="sxs-lookup"><span data-stu-id="18d15-154">-   Explicit</span></span><br /><span data-ttu-id="18d15-155">-Único</span><span class="sxs-lookup"><span data-stu-id="18d15-155">-   Unique</span></span><br /><br /> <span data-ttu-id="18d15-156">El valor predeterminado es Explicito.</span><span class="sxs-lookup"><span data-stu-id="18d15-156">The default value is Explicit.</span></span>|  
|<span data-ttu-id="18d15-157">listenUri</span><span class="sxs-lookup"><span data-stu-id="18d15-157">listenUri</span></span>|<span data-ttu-id="18d15-158">Una cadena que especifica el URI en el que el extremo de servicio realiza escuchas.</span><span class="sxs-lookup"><span data-stu-id="18d15-158">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="18d15-159">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="18d15-159">The default is an empty string.</span></span>|  
|<span data-ttu-id="18d15-160">name</span><span class="sxs-lookup"><span data-stu-id="18d15-160">name</span></span>|<span data-ttu-id="18d15-161">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="18d15-161">Optional attribute.</span></span> <span data-ttu-id="18d15-162">Cadena que especifica el nombre del extremo del servicio.</span><span class="sxs-lookup"><span data-stu-id="18d15-162">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="18d15-163">El valor predeterminado es la concatenación del nombre de enlace y el nombre de la descripción de contrato.</span><span class="sxs-lookup"><span data-stu-id="18d15-163">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="18d15-164">Los servicios pueden tener varios extremos, por lo que el atributo `name` del extremo es distinto del nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="18d15-164">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18d15-165">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="18d15-165">Child Elements</span></span>  
  
|<span data-ttu-id="18d15-166">Elemento</span><span class="sxs-lookup"><span data-stu-id="18d15-166">Element</span></span>|<span data-ttu-id="18d15-167">Descripción</span><span class="sxs-lookup"><span data-stu-id="18d15-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18d15-168">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="18d15-168">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="18d15-169">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="18d15-169">A collection of address headers.</span></span>|  
|[<span data-ttu-id="18d15-170">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="18d15-170">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="18d15-171">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="18d15-171">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="18d15-172">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="18d15-172">Parent Elements</span></span>  
  
|<span data-ttu-id="18d15-173">Elemento</span><span class="sxs-lookup"><span data-stu-id="18d15-173">Element</span></span>|<span data-ttu-id="18d15-174">Descripción</span><span class="sxs-lookup"><span data-stu-id="18d15-174">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18d15-175">\<servicio ></span><span class="sxs-lookup"><span data-stu-id="18d15-175">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="18d15-176">Una sección de configuración que define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="18d15-176">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="18d15-177">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="18d15-177">Example</span></span>  
 <span data-ttu-id="18d15-178">Éste es un ejemplo de una configuración del punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="18d15-178">This is an example of a service endpoint configuration.</span></span>  
  
```xml  
<endpoint   
    address="/HelloWorld/"  
    bindingConfiguration="usingDefaults"  
    bindingName="MyBinding"  
    binding="customBinding"  
    contract="HelloWorld">  
    <Headers>  
       <Region xmlns="http://tempuri.org/">EastCoast</Region>  
       <Member xmlns="http://tempuri.org/">Gold</Member>  
    </Headers>  
</endpoint>  
```  
  
## <a name="see-also"></a><span data-ttu-id="18d15-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="18d15-179">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceEndpointElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.Description.ServiceEndpoint>  
 [<span data-ttu-id="18d15-180">Los puntos de conexión: Direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="18d15-180">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [<span data-ttu-id="18d15-181">Cómo: crear un extremo de servicio en configuración</span><span class="sxs-lookup"><span data-stu-id="18d15-181">How to: Create a Service Endpoint in Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)

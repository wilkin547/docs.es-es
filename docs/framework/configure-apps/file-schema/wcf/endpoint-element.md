---
description: 'Más información acerca de: <endpoint> elemento'
title: <endpoint> (elemento)
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: d5555ae895e6655d1ce6e3dcb026ddec3ff8cf44
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725810"
---
# <a name="endpoint-element"></a><span data-ttu-id="00fec-103">Elemento \<endpoint></span><span class="sxs-lookup"><span data-stu-id="00fec-103">\<endpoint> element</span></span>

<span data-ttu-id="00fec-104">Especifica enlace, contrato y propiedades de dirección para un extremo de servicio, que se utiliza para exponer los servicios.</span><span class="sxs-lookup"><span data-stu-id="00fec-104">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="00fec-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00fec-105">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          bindingName="String"
          bindingNamespace="String"
          contract="String"
          endpointConfiguration="String"
          isSystemEndpoint="Boolean"
          kind="String"
          listenUriMode="Explicit/Unique"
          listenUri="Uri">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00fec-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="00fec-106">Attributes and Elements</span></span>  

 <span data-ttu-id="00fec-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="00fec-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00fec-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="00fec-108">Attributes</span></span>  
  
|<span data-ttu-id="00fec-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="00fec-109">Attribute</span></span>|<span data-ttu-id="00fec-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="00fec-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="00fec-111">address</span><span class="sxs-lookup"><span data-stu-id="00fec-111">address</span></span>|<span data-ttu-id="00fec-112">Una cadena que contiene la dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="00fec-112">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="00fec-113">La dirección se puede especificar como una dirección absoluta o relativa.</span><span class="sxs-lookup"><span data-stu-id="00fec-113">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="00fec-114">Si se proporciona una dirección relativa, se espera que el host proporcione una dirección base adecuada para el esquema de transporte usado en el enlace.</span><span class="sxs-lookup"><span data-stu-id="00fec-114">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="00fec-115">Si no se configura una dirección, se supone que la dirección base es la dirección para ese punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="00fec-115">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="00fec-116">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="00fec-116">The default is an empty string.</span></span>|  
|<span data-ttu-id="00fec-117">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="00fec-117">behaviorConfiguration</span></span>|<span data-ttu-id="00fec-118">Una cadena que contiene el nombre del comportamiento que se va a utilizar en el extremo.</span><span class="sxs-lookup"><span data-stu-id="00fec-118">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="00fec-119">binding</span><span class="sxs-lookup"><span data-stu-id="00fec-119">binding</span></span>|<span data-ttu-id="00fec-120">Atributo de cadena necesario que especifica el tipo de enlace que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="00fec-120">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="00fec-121">El tipo debe tener una sección de configuración registrada para que se haga referencia al mismo.</span><span class="sxs-lookup"><span data-stu-id="00fec-121">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="00fec-122">El tipo es el registrado por el nombre de sección, en lugar de por el nombre de tipo del enlace.</span><span class="sxs-lookup"><span data-stu-id="00fec-122">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="00fec-123">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="00fec-123">bindingConfiguration</span></span>|<span data-ttu-id="00fec-124">Una cadena que especifica el nombre obligatorio del enlace que se utilizará cuando se creen las instancias del extremo.</span><span class="sxs-lookup"><span data-stu-id="00fec-124">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="00fec-125">El nombre de enlace debe estar en el ámbito en el punto definido del extremo.</span><span class="sxs-lookup"><span data-stu-id="00fec-125">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="00fec-126">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="00fec-126">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="00fec-127">Este atributo se utiliza junto con `binding` para hacer referencia a una configuración de enlace concreta en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="00fec-127">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="00fec-128">Establezca este atributo si está intentando utilizar un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="00fec-128">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="00fec-129">De lo contrario, puede producirse una excepción.</span><span class="sxs-lookup"><span data-stu-id="00fec-129">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="00fec-130">bindingName</span><span class="sxs-lookup"><span data-stu-id="00fec-130">bindingName</span></span>|<span data-ttu-id="00fec-131">Una cadena que especifica el nombre completo único del enlace para la exportación de la definición a través de WSDL.</span><span class="sxs-lookup"><span data-stu-id="00fec-131">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="00fec-132">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="00fec-132">The default is an empty string.</span></span>|  
|<span data-ttu-id="00fec-133">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="00fec-133">bindingNamespace</span></span>|<span data-ttu-id="00fec-134">Una cadena que especifica el nombre completo del espacio de nombres del enlace para la exportación de la definición a través de WSDL.</span><span class="sxs-lookup"><span data-stu-id="00fec-134">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="00fec-135">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="00fec-135">The default is an empty string.</span></span>|  
|<span data-ttu-id="00fec-136">contrato</span><span class="sxs-lookup"><span data-stu-id="00fec-136">contract</span></span>|<span data-ttu-id="00fec-137">Una cadena que indica qué contrato está exponiendo este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="00fec-137">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="00fec-138">El ensamblado debe implementar el tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="00fec-138">The assembly must implement the contract type.</span></span> <span data-ttu-id="00fec-139">Si una implementación de servicio implementa un tipo de contrato único, entonces se puede omitir esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="00fec-139">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="00fec-140">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="00fec-140">The default is an empty string.</span></span>|  
|<span data-ttu-id="00fec-141">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="00fec-141">endpointConfiguration</span></span>|<span data-ttu-id="00fec-142">Cadena que especifica el nombre del punto de conexión estándar establecido por el atributo `kind`, que hace referencia a la información de configuración adicional de este punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="00fec-142">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="00fec-143">El mismo nombre se debe definir en la sección `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="00fec-143">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="00fec-144">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="00fec-144">isSystemEndpoint</span></span>|<span data-ttu-id="00fec-145">Valor booleano que especifica si un punto de conexión es un punto de conexión de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="00fec-145">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="00fec-146">kind</span><span class="sxs-lookup"><span data-stu-id="00fec-146">kind</span></span>|<span data-ttu-id="00fec-147">Cadena que especifica el tipo de extremo estándar aplicado.</span><span class="sxs-lookup"><span data-stu-id="00fec-147">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="00fec-148">El tipo se debe registrar en la sección `<extensions>` o en machine.config. Si no se especifica nada, se crea un punto de conexión de servicio común.</span><span class="sxs-lookup"><span data-stu-id="00fec-148">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="00fec-149">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="00fec-149">listenUriMode</span></span>|<span data-ttu-id="00fec-150">Especifica cómo el transporte trata el `ListenUri` proporcionado para el servicio en el que se realizan escuchas.</span><span class="sxs-lookup"><span data-stu-id="00fec-150">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="00fec-151">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="00fec-151">Valid values are</span></span><br /><br /> <span data-ttu-id="00fec-152">-Explicit</span><span class="sxs-lookup"><span data-stu-id="00fec-152">-   Explicit</span></span><br /><span data-ttu-id="00fec-153">-Único</span><span class="sxs-lookup"><span data-stu-id="00fec-153">-   Unique</span></span><br /><br /> <span data-ttu-id="00fec-154">El valor predeterminado es Explicito.</span><span class="sxs-lookup"><span data-stu-id="00fec-154">The default value is Explicit.</span></span>|  
|<span data-ttu-id="00fec-155">listenUri</span><span class="sxs-lookup"><span data-stu-id="00fec-155">listenUri</span></span>|<span data-ttu-id="00fec-156">Una cadena que especifica el URI en el que el extremo de servicio realiza escuchas.</span><span class="sxs-lookup"><span data-stu-id="00fec-156">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="00fec-157">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="00fec-157">The default is an empty string.</span></span>|  
|<span data-ttu-id="00fec-158">name</span><span class="sxs-lookup"><span data-stu-id="00fec-158">name</span></span>|<span data-ttu-id="00fec-159">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="00fec-159">Optional attribute.</span></span> <span data-ttu-id="00fec-160">Cadena que especifica el nombre del punto de conexión del servicio.</span><span class="sxs-lookup"><span data-stu-id="00fec-160">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="00fec-161">El valor predeterminado es la concatenación del nombre de enlace y el nombre de la descripción de contrato.</span><span class="sxs-lookup"><span data-stu-id="00fec-161">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="00fec-162">Los servicios pueden tener varios puntos de conexión, por lo que el atributo `name` del punto de conexión es distinto del nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="00fec-162">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00fec-163">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="00fec-163">Child Elements</span></span>  
  
|<span data-ttu-id="00fec-164">Elemento</span><span class="sxs-lookup"><span data-stu-id="00fec-164">Element</span></span>|<span data-ttu-id="00fec-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="00fec-165">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="00fec-166">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="00fec-166">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="00fec-167">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="00fec-167">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00fec-168">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="00fec-168">Parent Elements</span></span>  
  
|<span data-ttu-id="00fec-169">Elemento</span><span class="sxs-lookup"><span data-stu-id="00fec-169">Element</span></span>|<span data-ttu-id="00fec-170">Descripción</span><span class="sxs-lookup"><span data-stu-id="00fec-170">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="00fec-171">Una sección de configuración que define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="00fec-171">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="00fec-172">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00fec-172">Example</span></span>  

 <span data-ttu-id="00fec-173">Éste es un ejemplo de una configuración del punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="00fec-173">This is an example of a service endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          bindingName="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
  <headers>
    <region xmlns="http://tempuri.org/">EastCoast</region>
    <member xmlns="http://tempuri.org/">Gold</member>
  </headers>
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="00fec-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="00fec-174">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="00fec-175">Puntos de conexión: direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="00fec-175">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="00fec-176">Procedimiento para crear un punto de conexión de servicio en la configuración</span><span class="sxs-lookup"><span data-stu-id="00fec-176">How to: Create a Service Endpoint in Configuration</span></span>](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)

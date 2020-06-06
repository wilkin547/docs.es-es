---
title: <endpoint> (elemento)
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: fb9d3bf9b5f1a742abcc70d78af026c179ec4c4d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855381"
---
# <a name="endpoint-element"></a><span data-ttu-id="7e3a4-102">Elemento \<endpoint></span><span class="sxs-lookup"><span data-stu-id="7e3a4-102">\<endpoint> element</span></span>
<span data-ttu-id="7e3a4-103">Especifica enlace, contrato y propiedades de dirección para un extremo de servicio, que se utiliza para exponer los servicios.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="7e3a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e3a4-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e3a4-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7e3a4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7e3a4-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e3a4-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="7e3a4-107">Attributes</span></span>  
  
|<span data-ttu-id="7e3a4-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="7e3a4-108">Attribute</span></span>|<span data-ttu-id="7e3a4-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e3a4-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e3a4-110">address</span><span class="sxs-lookup"><span data-stu-id="7e3a4-110">address</span></span>|<span data-ttu-id="7e3a4-111">Una cadena que contiene la dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-111">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="7e3a4-112">La dirección se puede especificar como una dirección absoluta o relativa.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-112">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="7e3a4-113">Si se proporciona una dirección relativa, se espera que el host proporcione una dirección base adecuada para el esquema de transporte usado en el enlace.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-113">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="7e3a4-114">Si no se configura una dirección, se supone que la dirección base es la dirección para ese punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-114">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="7e3a4-115">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-115">The default is an empty string.</span></span>|  
|<span data-ttu-id="7e3a4-116">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="7e3a4-116">behaviorConfiguration</span></span>|<span data-ttu-id="7e3a4-117">Una cadena que contiene el nombre del comportamiento que se va a utilizar en el extremo.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-117">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="7e3a4-118">binding</span><span class="sxs-lookup"><span data-stu-id="7e3a4-118">binding</span></span>|<span data-ttu-id="7e3a4-119">Atributo de cadena necesario que especifica el tipo de enlace que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-119">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="7e3a4-120">El tipo debe tener una sección de configuración registrada para que se haga referencia al mismo.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-120">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="7e3a4-121">El tipo es el registrado por el nombre de sección, en lugar de por el nombre de tipo del enlace.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-121">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="7e3a4-122">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7e3a4-122">bindingConfiguration</span></span>|<span data-ttu-id="7e3a4-123">Una cadena que especifica el nombre obligatorio del enlace que se utilizará cuando se creen las instancias del extremo.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-123">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="7e3a4-124">El nombre de enlace debe estar en el ámbito en el punto definido del extremo.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-124">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="7e3a4-125">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-125">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="7e3a4-126">Este atributo se utiliza junto con `binding` para hacer referencia a una configuración de enlace concreta en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-126">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="7e3a4-127">Establezca este atributo si está intentando utilizar un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-127">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="7e3a4-128">De lo contrario, puede producirse una excepción.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-128">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="7e3a4-129">bindingName</span><span class="sxs-lookup"><span data-stu-id="7e3a4-129">bindingName</span></span>|<span data-ttu-id="7e3a4-130">Una cadena que especifica el nombre completo único del enlace para la exportación de la definición a través de WSDL.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-130">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="7e3a4-131">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="7e3a4-132">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="7e3a4-132">bindingNamespace</span></span>|<span data-ttu-id="7e3a4-133">Una cadena que especifica el nombre completo del espacio de nombres del enlace para la exportación de la definición a través de WSDL.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-133">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="7e3a4-134">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="7e3a4-135">contrato</span><span class="sxs-lookup"><span data-stu-id="7e3a4-135">contract</span></span>|<span data-ttu-id="7e3a4-136">Una cadena que indica qué contrato está exponiendo este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-136">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="7e3a4-137">El ensamblado debe implementar el tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-137">The assembly must implement the contract type.</span></span> <span data-ttu-id="7e3a4-138">Si una implementación de servicio implementa un tipo de contrato único, entonces se puede omitir esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-138">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="7e3a4-139">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-139">The default is an empty string.</span></span>|  
|<span data-ttu-id="7e3a4-140">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="7e3a4-140">endpointConfiguration</span></span>|<span data-ttu-id="7e3a4-141">Cadena que especifica el nombre del punto de conexión estándar establecido por el atributo `kind`, que hace referencia a la información de configuración adicional de este punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-141">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="7e3a4-142">El mismo nombre se debe definir en la sección `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-142">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="7e3a4-143">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="7e3a4-143">isSystemEndpoint</span></span>|<span data-ttu-id="7e3a4-144">Valor booleano que especifica si un punto de conexión es un punto de conexión de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-144">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="7e3a4-145">kind</span><span class="sxs-lookup"><span data-stu-id="7e3a4-145">kind</span></span>|<span data-ttu-id="7e3a4-146">Cadena que especifica el tipo de extremo estándar aplicado.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-146">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="7e3a4-147">El tipo se debe registrar en la `<extensions>` sección o en Machine. config. Si no se especifica nada, se crea un punto de conexión de servicio común.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-147">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="7e3a4-148">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="7e3a4-148">listenUriMode</span></span>|<span data-ttu-id="7e3a4-149">Especifica cómo el transporte trata el `ListenUri` proporcionado para el servicio en el que se realizan escuchas.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-149">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="7e3a4-150">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="7e3a4-150">Valid values are</span></span><br /><br /> <span data-ttu-id="7e3a4-151">-Explicit</span><span class="sxs-lookup"><span data-stu-id="7e3a4-151">-   Explicit</span></span><br /><span data-ttu-id="7e3a4-152">-Único</span><span class="sxs-lookup"><span data-stu-id="7e3a4-152">-   Unique</span></span><br /><br /> <span data-ttu-id="7e3a4-153">El valor predeterminado es Explicito.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-153">The default value is Explicit.</span></span>|  
|<span data-ttu-id="7e3a4-154">listenUri</span><span class="sxs-lookup"><span data-stu-id="7e3a4-154">listenUri</span></span>|<span data-ttu-id="7e3a4-155">Una cadena que especifica el URI en el que el extremo de servicio realiza escuchas.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-155">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="7e3a4-156">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-156">The default is an empty string.</span></span>|  
|<span data-ttu-id="7e3a4-157">name</span><span class="sxs-lookup"><span data-stu-id="7e3a4-157">name</span></span>|<span data-ttu-id="7e3a4-158">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-158">Optional attribute.</span></span> <span data-ttu-id="7e3a4-159">Cadena que especifica el nombre del punto de conexión del servicio.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-159">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="7e3a4-160">El valor predeterminado es la concatenación del nombre de enlace y el nombre de la descripción de contrato.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-160">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="7e3a4-161">Los servicios pueden tener varios puntos de conexión, por lo que el atributo `name` del punto de conexión es distinto del nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-161">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e3a4-162">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7e3a4-162">Child Elements</span></span>  
  
|<span data-ttu-id="7e3a4-163">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e3a4-163">Element</span></span>|<span data-ttu-id="7e3a4-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e3a4-164">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="7e3a4-165">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-165">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="7e3a4-166">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-166">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7e3a4-167">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7e3a4-167">Parent Elements</span></span>  
  
|<span data-ttu-id="7e3a4-168">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e3a4-168">Element</span></span>|<span data-ttu-id="7e3a4-169">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e3a4-169">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="7e3a4-170">Una sección de configuración que define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-170">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7e3a4-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7e3a4-171">Example</span></span>  
 <span data-ttu-id="7e3a4-172">Éste es un ejemplo de una configuración del punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="7e3a4-172">This is an example of a service endpoint configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7e3a4-173">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7e3a4-173">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="7e3a4-174">Puntos de conexión: direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="7e3a4-174">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="7e3a4-175">Procedimiento para crear un punto de conexión de servicio en la configuración</span><span class="sxs-lookup"><span data-stu-id="7e3a4-175">How to: Create a Service Endpoint in Configuration</span></span>](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)

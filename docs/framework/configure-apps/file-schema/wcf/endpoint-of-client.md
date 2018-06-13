---
title: Elemento &lt;endpoint&gt; de &lt;client&gt;
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: f9a69483ab058823fd419edc84868e801b91d2c9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748066"
---
# <a name="ltendpointgt-of-ltclientgt"></a><span data-ttu-id="e650f-102">Elemento &lt;endpoint&gt; de &lt;client&gt;</span><span class="sxs-lookup"><span data-stu-id="e650f-102">&lt;endpoint&gt; of &lt;client&gt;</span></span>
<span data-ttu-id="e650f-103">Especifica el contrato, enlace y propiedades de dirección del punto de conexión del canal, que es utilizado por clientes para conectar a los puntos de conexión de servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="e650f-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
 <span data-ttu-id="e650f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e650f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e650f-105">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="e650f-105">\<client></span></span>  
<span data-ttu-id="e650f-106">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="e650f-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e650f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e650f-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"  
   behaviorConfiguration="String"  
   binding="String"  
   bindingConfiguration="String"  
   contract="String"   endpointConfiguration="String"   kind="String"  
   name="String"  
</endpoint>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e650f-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e650f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e650f-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e650f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e650f-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e650f-110">Attributes</span></span>  
  
|<span data-ttu-id="e650f-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="e650f-111">Attribute</span></span>|<span data-ttu-id="e650f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e650f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e650f-113">address</span><span class="sxs-lookup"><span data-stu-id="e650f-113">address</span></span>|<span data-ttu-id="e650f-114">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="e650f-114">Required string attribute.</span></span><br /><br /> <span data-ttu-id="e650f-115">Especifica la dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="e650f-115">Specifies the address of the endpoint.</span></span> <span data-ttu-id="e650f-116">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="e650f-116">The default is an empty string.</span></span> <span data-ttu-id="e650f-117">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="e650f-117">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="e650f-118">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="e650f-118">behaviorConfiguration</span></span>|<span data-ttu-id="e650f-119">Una cadena que contiene el nombre de comportamiento del comportamiento que se va a usar para crear una instancia del extremo.</span><span class="sxs-lookup"><span data-stu-id="e650f-119">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="e650f-120">El nombre de comportamiento debe estar en el ámbito en el punto definido del servicio.</span><span class="sxs-lookup"><span data-stu-id="e650f-120">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="e650f-121">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="e650f-121">The default is an empty string.</span></span>|  
|<span data-ttu-id="e650f-122">enlace</span><span class="sxs-lookup"><span data-stu-id="e650f-122">binding</span></span>|<span data-ttu-id="e650f-123">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="e650f-123">Required string attribute.</span></span><br /><br /> <span data-ttu-id="e650f-124">Una cadena que indica el tipo de enlace que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="e650f-124">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="e650f-125">El tipo debe tener una sección de configuración registrada para que se haga referencia al mismo.</span><span class="sxs-lookup"><span data-stu-id="e650f-125">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="e650f-126">El tipo está registrado por el nombre de sección, en lugar de por el nombre de tipo del enlace.</span><span class="sxs-lookup"><span data-stu-id="e650f-126">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="e650f-127">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e650f-127">bindingConfiguration</span></span>|<span data-ttu-id="e650f-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e650f-128">Optional.</span></span> <span data-ttu-id="e650f-129">Una cadena que contiene el nombre de la configuración de enlace que se va a utilizar cuando se instancia el extremo.</span><span class="sxs-lookup"><span data-stu-id="e650f-129">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="e650f-130">La configuración del enlace debe estar en el ámbito en el punto definido del extremo.</span><span class="sxs-lookup"><span data-stu-id="e650f-130">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="e650f-131">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="e650f-131">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="e650f-132">Este atributo se utiliza junto con `binding` para hacer referencia a una configuración de enlace concreta en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e650f-132">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="e650f-133">Establezca este atributo si está intentando utilizar un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="e650f-133">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="e650f-134">De lo contrario, puede producirse una excepción.</span><span class="sxs-lookup"><span data-stu-id="e650f-134">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="e650f-135">contrato</span><span class="sxs-lookup"><span data-stu-id="e650f-135">contract</span></span>|<span data-ttu-id="e650f-136">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="e650f-136">Required string attribute.</span></span><br /><br /> <span data-ttu-id="e650f-137">Una cadena que indica qué contrato está exponiendo este extremo.</span><span class="sxs-lookup"><span data-stu-id="e650f-137">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="e650f-138">El ensamblado debe implementar el tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="e650f-138">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="e650f-139">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="e650f-139">endpointConfiguration</span></span>|<span data-ttu-id="e650f-140">Cadena que especifica el nombre del extremo estándar establecido por el atributo `kind`, que hace referencia a la información de configuración adicional de este extremo estándar.</span><span class="sxs-lookup"><span data-stu-id="e650f-140">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="e650f-141">El mismo nombre se debe definir en la sección `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="e650f-141">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="e650f-142">kind</span><span class="sxs-lookup"><span data-stu-id="e650f-142">kind</span></span>|<span data-ttu-id="e650f-143">Cadena que especifica el tipo de extremo estándar aplicado.</span><span class="sxs-lookup"><span data-stu-id="e650f-143">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="e650f-144">El tipo se debe registrar en la sección `<extensions>` o en machine.config. Si no se especifica nada, se crea un extremo de canal común.</span><span class="sxs-lookup"><span data-stu-id="e650f-144">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="e650f-145">name</span><span class="sxs-lookup"><span data-stu-id="e650f-145">name</span></span>|<span data-ttu-id="e650f-146">Atributo de cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="e650f-146">Optional string attribute.</span></span> <span data-ttu-id="e650f-147">Este atributo identifica singularmente un extremo para un contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="e650f-147">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="e650f-148">Puede definir varios clientes para un tipo de contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="e650f-148">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="e650f-149">Cada definición tiene que diferenciarse por un nombre de configuración unívoco.</span><span class="sxs-lookup"><span data-stu-id="e650f-149">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="e650f-150">Si se omite este atributo, el extremo correspondiente se usa como el extremo predeterminado asociado al tipo de contrato especificado.</span><span class="sxs-lookup"><span data-stu-id="e650f-150">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="e650f-151">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="e650f-151">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="e650f-152">El atributo de `name` de un enlace se utiliza para la exportación de la definición a través de WSDL.</span><span class="sxs-lookup"><span data-stu-id="e650f-152">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e650f-153">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e650f-153">Child Elements</span></span>  
  
|<span data-ttu-id="e650f-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="e650f-154">Element</span></span>|<span data-ttu-id="e650f-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="e650f-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e650f-156">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="e650f-156">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="e650f-157">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="e650f-157">A collection of address headers.</span></span>|  
|[<span data-ttu-id="e650f-158">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="e650f-158">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="e650f-159">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="e650f-159">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e650f-160">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e650f-160">Parent Elements</span></span>  
  
|<span data-ttu-id="e650f-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="e650f-161">Element</span></span>|<span data-ttu-id="e650f-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="e650f-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e650f-163">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="e650f-163">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="e650f-164">Una sección de configuración que define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="e650f-164">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e650f-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e650f-165">Example</span></span>  
 <span data-ttu-id="e650f-166">Éste es un ejemplo de una configuración del punto de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="e650f-166">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"  
    bindingConfiguration="usingDefaults"  
    name="MyBinding"  
    binding="customBinding"  
    contract="HelloWorld">  
</endpoint>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e650f-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="e650f-167">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>  
 <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>  
 [<span data-ttu-id="e650f-168">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="e650f-168">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="e650f-169">Clientes</span><span class="sxs-lookup"><span data-stu-id="e650f-169">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)

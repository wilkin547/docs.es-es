---
description: 'Más información sobre: <endpoint> de <client>'
title: <endpoint> de <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: 4ace6d49ba18524729925b20cf08e5d57bcc40c5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725786"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="ed800-103">\<endpoint> de \<client></span><span class="sxs-lookup"><span data-stu-id="ed800-103">\<endpoint> of \<client></span></span>

<span data-ttu-id="ed800-104">Especifica el contrato, enlace y propiedades de dirección del extremo del canal, que es utilizado por clientes para conectar a los extremos de servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ed800-104">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="ed800-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed800-105">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          contract="String"
          endpointConfiguration="String"
          kind="String"
          name="String">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed800-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ed800-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ed800-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ed800-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed800-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="ed800-108">Attributes</span></span>  
  
|<span data-ttu-id="ed800-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="ed800-109">Attribute</span></span>|<span data-ttu-id="ed800-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed800-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ed800-111">address</span><span class="sxs-lookup"><span data-stu-id="ed800-111">address</span></span>|<span data-ttu-id="ed800-112">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="ed800-112">Required string attribute.</span></span><br /><br /> <span data-ttu-id="ed800-113">Especifica la dirección del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ed800-113">Specifies the address of the endpoint.</span></span> <span data-ttu-id="ed800-114">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="ed800-114">The default is an empty string.</span></span> <span data-ttu-id="ed800-115">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="ed800-115">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="ed800-116">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed800-116">behaviorConfiguration</span></span>|<span data-ttu-id="ed800-117">Una cadena que contiene el nombre de comportamiento del comportamiento que se va a usar para crear una instancia del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ed800-117">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="ed800-118">El nombre de comportamiento debe estar en el ámbito en el punto definido del servicio.</span><span class="sxs-lookup"><span data-stu-id="ed800-118">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="ed800-119">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="ed800-119">The default is an empty string.</span></span>|  
|<span data-ttu-id="ed800-120">binding</span><span class="sxs-lookup"><span data-stu-id="ed800-120">binding</span></span>|<span data-ttu-id="ed800-121">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="ed800-121">Required string attribute.</span></span><br /><br /> <span data-ttu-id="ed800-122">Una cadena que indica el tipo de enlace que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="ed800-122">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="ed800-123">El tipo debe tener una sección de configuración registrada para que se haga referencia al mismo.</span><span class="sxs-lookup"><span data-stu-id="ed800-123">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="ed800-124">El tipo está registrado por el nombre de sección, en lugar de por el nombre de tipo del enlace.</span><span class="sxs-lookup"><span data-stu-id="ed800-124">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="ed800-125">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed800-125">bindingConfiguration</span></span>|<span data-ttu-id="ed800-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ed800-126">Optional.</span></span> <span data-ttu-id="ed800-127">Una cadena que contiene el nombre de la configuración de enlace que se va a utilizar cuando se instancia el extremo.</span><span class="sxs-lookup"><span data-stu-id="ed800-127">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="ed800-128">La configuración del enlace debe estar en el ámbito en el punto definido del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ed800-128">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="ed800-129">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="ed800-129">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="ed800-130">Este atributo se utiliza junto con `binding` para hacer referencia a una configuración de enlace concreta en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ed800-130">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="ed800-131">Establezca este atributo si está intentando utilizar un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="ed800-131">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="ed800-132">De lo contrario, puede producirse una excepción.</span><span class="sxs-lookup"><span data-stu-id="ed800-132">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="ed800-133">contrato</span><span class="sxs-lookup"><span data-stu-id="ed800-133">contract</span></span>|<span data-ttu-id="ed800-134">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="ed800-134">Required string attribute.</span></span><br /><br /> <span data-ttu-id="ed800-135">Una cadena que indica qué contrato está exponiendo este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ed800-135">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="ed800-136">El ensamblado debe implementar el tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="ed800-136">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="ed800-137">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed800-137">endpointConfiguration</span></span>|<span data-ttu-id="ed800-138">Cadena que especifica el nombre del punto de conexión estándar establecido por el atributo `kind`, que hace referencia a la información de configuración adicional de este punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="ed800-138">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="ed800-139">El mismo nombre se debe definir en la sección `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="ed800-139">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="ed800-140">kind</span><span class="sxs-lookup"><span data-stu-id="ed800-140">kind</span></span>|<span data-ttu-id="ed800-141">Cadena que especifica el tipo de extremo estándar aplicado.</span><span class="sxs-lookup"><span data-stu-id="ed800-141">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="ed800-142">El tipo se debe registrar en la sección `<extensions>` o en machine.config. Si no se especifica nada, se crea un punto de conexión de canal común.</span><span class="sxs-lookup"><span data-stu-id="ed800-142">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="ed800-143">name</span><span class="sxs-lookup"><span data-stu-id="ed800-143">name</span></span>|<span data-ttu-id="ed800-144">Atributo de cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="ed800-144">Optional string attribute.</span></span> <span data-ttu-id="ed800-145">Este atributo identifica singularmente un extremo para un contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="ed800-145">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="ed800-146">Puede definir varios clientes para un tipo de contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="ed800-146">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="ed800-147">Cada definición tiene que diferenciarse por un nombre de configuración unívoco.</span><span class="sxs-lookup"><span data-stu-id="ed800-147">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="ed800-148">Si se omite este atributo, el punto de conexión correspondiente se usa como el punto de conexión predeterminado asociado al tipo de contrato especificado.</span><span class="sxs-lookup"><span data-stu-id="ed800-148">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="ed800-149">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="ed800-149">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="ed800-150">El atributo de `name` de un enlace se utiliza para la exportación de la definición a través de WSDL.</span><span class="sxs-lookup"><span data-stu-id="ed800-150">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ed800-151">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ed800-151">Child Elements</span></span>  
  
|<span data-ttu-id="ed800-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="ed800-152">Element</span></span>|<span data-ttu-id="ed800-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed800-153">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="ed800-154">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="ed800-154">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="ed800-155">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="ed800-155">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ed800-156">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ed800-156">Parent Elements</span></span>  
  
|<span data-ttu-id="ed800-157">Elemento</span><span class="sxs-lookup"><span data-stu-id="ed800-157">Element</span></span>|<span data-ttu-id="ed800-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed800-158">Description</span></span>|  
|-------------|-----------------|  
|[\<client>](client.md)|<span data-ttu-id="ed800-159">Una sección de configuración que define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="ed800-159">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ed800-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ed800-160">Example</span></span>  

 <span data-ttu-id="ed800-161">Éste es un ejemplo de una configuración del extremo del canal.</span><span class="sxs-lookup"><span data-stu-id="ed800-161">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="ed800-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed800-162">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="ed800-163">Configuración de cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="ed800-163">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="ed800-164">Clientes</span><span class="sxs-lookup"><span data-stu-id="ed800-164">Clients</span></span>](../../../wcf/feature-details/clients.md)

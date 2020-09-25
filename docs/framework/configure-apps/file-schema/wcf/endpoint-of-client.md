---
title: <endpoint> de <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: 79d827691ec3898ad94af9835077c61ea35990ab
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185852"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="eef3e-102">\<endpoint> de \<client></span><span class="sxs-lookup"><span data-stu-id="eef3e-102">\<endpoint> of \<client></span></span>

<span data-ttu-id="eef3e-103">Especifica el contrato, enlace y propiedades de dirección del extremo del canal, que es utilizado por clientes para conectar a los extremos de servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="eef3e-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="eef3e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eef3e-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eef3e-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="eef3e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="eef3e-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="eef3e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eef3e-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="eef3e-107">Attributes</span></span>  
  
|<span data-ttu-id="eef3e-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="eef3e-108">Attribute</span></span>|<span data-ttu-id="eef3e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="eef3e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eef3e-110">address</span><span class="sxs-lookup"><span data-stu-id="eef3e-110">address</span></span>|<span data-ttu-id="eef3e-111">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="eef3e-111">Required string attribute.</span></span><br /><br /> <span data-ttu-id="eef3e-112">Especifica la dirección del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="eef3e-112">Specifies the address of the endpoint.</span></span> <span data-ttu-id="eef3e-113">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="eef3e-113">The default is an empty string.</span></span> <span data-ttu-id="eef3e-114">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="eef3e-114">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="eef3e-115">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="eef3e-115">behaviorConfiguration</span></span>|<span data-ttu-id="eef3e-116">Una cadena que contiene el nombre de comportamiento del comportamiento que se va a usar para crear una instancia del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="eef3e-116">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="eef3e-117">El nombre de comportamiento debe estar en el ámbito en el punto definido del servicio.</span><span class="sxs-lookup"><span data-stu-id="eef3e-117">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="eef3e-118">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="eef3e-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="eef3e-119">binding</span><span class="sxs-lookup"><span data-stu-id="eef3e-119">binding</span></span>|<span data-ttu-id="eef3e-120">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="eef3e-120">Required string attribute.</span></span><br /><br /> <span data-ttu-id="eef3e-121">Una cadena que indica el tipo de enlace que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="eef3e-121">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="eef3e-122">El tipo debe tener una sección de configuración registrada para que se haga referencia al mismo.</span><span class="sxs-lookup"><span data-stu-id="eef3e-122">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="eef3e-123">El tipo está registrado por el nombre de sección, en lugar de por el nombre de tipo del enlace.</span><span class="sxs-lookup"><span data-stu-id="eef3e-123">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="eef3e-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="eef3e-124">bindingConfiguration</span></span>|<span data-ttu-id="eef3e-125">Opcional.</span><span class="sxs-lookup"><span data-stu-id="eef3e-125">Optional.</span></span> <span data-ttu-id="eef3e-126">Una cadena que contiene el nombre de la configuración de enlace que se va a utilizar cuando se instancia el extremo.</span><span class="sxs-lookup"><span data-stu-id="eef3e-126">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="eef3e-127">La configuración del enlace debe estar en el ámbito en el punto definido del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="eef3e-127">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="eef3e-128">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="eef3e-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="eef3e-129">Este atributo se utiliza junto con `binding` para hacer referencia a una configuración de enlace concreta en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="eef3e-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="eef3e-130">Establezca este atributo si está intentando utilizar un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="eef3e-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="eef3e-131">De lo contrario, puede producirse una excepción.</span><span class="sxs-lookup"><span data-stu-id="eef3e-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="eef3e-132">contrato</span><span class="sxs-lookup"><span data-stu-id="eef3e-132">contract</span></span>|<span data-ttu-id="eef3e-133">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="eef3e-133">Required string attribute.</span></span><br /><br /> <span data-ttu-id="eef3e-134">Una cadena que indica qué contrato está exponiendo este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="eef3e-134">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="eef3e-135">El ensamblado debe implementar el tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="eef3e-135">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="eef3e-136">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="eef3e-136">endpointConfiguration</span></span>|<span data-ttu-id="eef3e-137">Cadena que especifica el nombre del punto de conexión estándar establecido por el atributo `kind`, que hace referencia a la información de configuración adicional de este punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="eef3e-137">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="eef3e-138">El mismo nombre se debe definir en la sección `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="eef3e-138">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="eef3e-139">kind</span><span class="sxs-lookup"><span data-stu-id="eef3e-139">kind</span></span>|<span data-ttu-id="eef3e-140">Cadena que especifica el tipo de extremo estándar aplicado.</span><span class="sxs-lookup"><span data-stu-id="eef3e-140">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="eef3e-141">El tipo se debe registrar en la sección `<extensions>` o en machine.config. Si no se especifica nada, se crea un punto de conexión de canal común.</span><span class="sxs-lookup"><span data-stu-id="eef3e-141">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="eef3e-142">name</span><span class="sxs-lookup"><span data-stu-id="eef3e-142">name</span></span>|<span data-ttu-id="eef3e-143">Atributo de cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="eef3e-143">Optional string attribute.</span></span> <span data-ttu-id="eef3e-144">Este atributo identifica singularmente un extremo para un contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="eef3e-144">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="eef3e-145">Puede definir varios clientes para un tipo de contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="eef3e-145">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="eef3e-146">Cada definición tiene que diferenciarse por un nombre de configuración unívoco.</span><span class="sxs-lookup"><span data-stu-id="eef3e-146">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="eef3e-147">Si se omite este atributo, el punto de conexión correspondiente se usa como el punto de conexión predeterminado asociado al tipo de contrato especificado.</span><span class="sxs-lookup"><span data-stu-id="eef3e-147">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="eef3e-148">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="eef3e-148">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="eef3e-149">El atributo de `name` de un enlace se utiliza para la exportación de la definición a través de WSDL.</span><span class="sxs-lookup"><span data-stu-id="eef3e-149">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eef3e-150">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eef3e-150">Child Elements</span></span>  
  
|<span data-ttu-id="eef3e-151">Elemento</span><span class="sxs-lookup"><span data-stu-id="eef3e-151">Element</span></span>|<span data-ttu-id="eef3e-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="eef3e-152">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="eef3e-153">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="eef3e-153">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="eef3e-154">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="eef3e-154">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eef3e-155">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="eef3e-155">Parent Elements</span></span>  
  
|<span data-ttu-id="eef3e-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="eef3e-156">Element</span></span>|<span data-ttu-id="eef3e-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="eef3e-157">Description</span></span>|  
|-------------|-----------------|  
|[\<client>](client.md)|<span data-ttu-id="eef3e-158">Una sección de configuración que define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="eef3e-158">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eef3e-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eef3e-159">Example</span></span>  

 <span data-ttu-id="eef3e-160">Éste es un ejemplo de una configuración del extremo del canal.</span><span class="sxs-lookup"><span data-stu-id="eef3e-160">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="eef3e-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eef3e-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="eef3e-162">Configuración de cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="eef3e-162">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="eef3e-163">Clientes</span><span class="sxs-lookup"><span data-stu-id="eef3e-163">Clients</span></span>](../../../wcf/feature-details/clients.md)

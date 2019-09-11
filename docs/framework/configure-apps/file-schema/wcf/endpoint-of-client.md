---
title: <endpoint> de <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: f1ffbc1e8efac70523d7f631c8cf9ba9a1622bfc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855324"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="7da5a-102">\<extremo > de \<> de cliente</span><span class="sxs-lookup"><span data-stu-id="7da5a-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="7da5a-103">Especifica el contrato, enlace y propiedades de dirección del extremo del canal, que es utilizado por clientes para conectar a los extremos de servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="7da5a-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
<span data-ttu-id="7da5a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7da5a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7da5a-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7da5a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7da5a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de cliente**](client.md)</span><span class="sxs-lookup"><span data-stu-id="7da5a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="7da5a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de extremo**</span><span class="sxs-lookup"><span data-stu-id="7da5a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7da5a-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7da5a-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7da5a-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7da5a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7da5a-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7da5a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7da5a-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="7da5a-111">Attributes</span></span>  
  
|<span data-ttu-id="7da5a-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="7da5a-112">Attribute</span></span>|<span data-ttu-id="7da5a-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7da5a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7da5a-114">dirección</span><span class="sxs-lookup"><span data-stu-id="7da5a-114">address</span></span>|<span data-ttu-id="7da5a-115">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="7da5a-115">Required string attribute.</span></span><br /><br /> <span data-ttu-id="7da5a-116">Especifica la dirección del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7da5a-116">Specifies the address of the endpoint.</span></span> <span data-ttu-id="7da5a-117">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="7da5a-117">The default is an empty string.</span></span> <span data-ttu-id="7da5a-118">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="7da5a-118">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="7da5a-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="7da5a-119">behaviorConfiguration</span></span>|<span data-ttu-id="7da5a-120">Una cadena que contiene el nombre de comportamiento del comportamiento que se va a usar para crear una instancia del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7da5a-120">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="7da5a-121">El nombre de comportamiento debe estar en el ámbito en el punto definido del servicio.</span><span class="sxs-lookup"><span data-stu-id="7da5a-121">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="7da5a-122">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="7da5a-122">The default is an empty string.</span></span>|  
|<span data-ttu-id="7da5a-123">enlace</span><span class="sxs-lookup"><span data-stu-id="7da5a-123">binding</span></span>|<span data-ttu-id="7da5a-124">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="7da5a-124">Required string attribute.</span></span><br /><br /> <span data-ttu-id="7da5a-125">Una cadena que indica el tipo de enlace que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="7da5a-125">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="7da5a-126">El tipo debe tener una sección de configuración registrada para que se haga referencia al mismo.</span><span class="sxs-lookup"><span data-stu-id="7da5a-126">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="7da5a-127">El tipo está registrado por el nombre de sección, en lugar de por el nombre de tipo del enlace.</span><span class="sxs-lookup"><span data-stu-id="7da5a-127">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="7da5a-128">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7da5a-128">bindingConfiguration</span></span>|<span data-ttu-id="7da5a-129">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7da5a-129">Optional.</span></span> <span data-ttu-id="7da5a-130">Una cadena que contiene el nombre de la configuración de enlace que se va a utilizar cuando se instancia el extremo.</span><span class="sxs-lookup"><span data-stu-id="7da5a-130">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="7da5a-131">La configuración del enlace debe estar en el ámbito en el punto definido del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7da5a-131">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="7da5a-132">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="7da5a-132">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="7da5a-133">Este atributo se utiliza junto con `binding` para hacer referencia a una configuración de enlace concreta en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="7da5a-133">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="7da5a-134">Establezca este atributo si está intentando utilizar un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="7da5a-134">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="7da5a-135">De lo contrario, puede producirse una excepción.</span><span class="sxs-lookup"><span data-stu-id="7da5a-135">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="7da5a-136">contrato</span><span class="sxs-lookup"><span data-stu-id="7da5a-136">contract</span></span>|<span data-ttu-id="7da5a-137">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="7da5a-137">Required string attribute.</span></span><br /><br /> <span data-ttu-id="7da5a-138">Una cadena que indica qué contrato está exponiendo este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7da5a-138">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="7da5a-139">El ensamblado debe implementar el tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="7da5a-139">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="7da5a-140">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="7da5a-140">endpointConfiguration</span></span>|<span data-ttu-id="7da5a-141">Cadena que especifica el nombre del punto de conexión estándar establecido por el atributo `kind`, que hace referencia a la información de configuración adicional de este punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="7da5a-141">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="7da5a-142">El mismo nombre se debe definir en la sección `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="7da5a-142">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="7da5a-143">kind</span><span class="sxs-lookup"><span data-stu-id="7da5a-143">kind</span></span>|<span data-ttu-id="7da5a-144">Cadena que especifica el tipo de extremo estándar aplicado.</span><span class="sxs-lookup"><span data-stu-id="7da5a-144">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="7da5a-145">El tipo se debe registrar en la sección `<extensions>` o en machine.config. Si no se especifica nada, se crea un extremo de canal común.</span><span class="sxs-lookup"><span data-stu-id="7da5a-145">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="7da5a-146">Nombre</span><span class="sxs-lookup"><span data-stu-id="7da5a-146">name</span></span>|<span data-ttu-id="7da5a-147">Atributo de cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="7da5a-147">Optional string attribute.</span></span> <span data-ttu-id="7da5a-148">Este atributo identifica singularmente un extremo para un contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="7da5a-148">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="7da5a-149">Puede definir varios clientes para un tipo de contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="7da5a-149">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="7da5a-150">Cada definición tiene que diferenciarse por un nombre de configuración unívoco.</span><span class="sxs-lookup"><span data-stu-id="7da5a-150">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="7da5a-151">Si se omite este atributo, el punto de conexión correspondiente se usa como el punto de conexión predeterminado asociado al tipo de contrato especificado.</span><span class="sxs-lookup"><span data-stu-id="7da5a-151">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="7da5a-152">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="7da5a-152">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="7da5a-153">El atributo de `name` de un enlace se utiliza para la exportación de la definición a través de WSDL.</span><span class="sxs-lookup"><span data-stu-id="7da5a-153">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7da5a-154">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7da5a-154">Child Elements</span></span>  
  
|<span data-ttu-id="7da5a-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="7da5a-155">Element</span></span>|<span data-ttu-id="7da5a-156">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7da5a-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7da5a-157">\<headers></span><span class="sxs-lookup"><span data-stu-id="7da5a-157">\<headers></span></span>](headers.md)|<span data-ttu-id="7da5a-158">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="7da5a-158">A collection of address headers.</span></span>|  
|[<span data-ttu-id="7da5a-159">\<identity></span><span class="sxs-lookup"><span data-stu-id="7da5a-159">\<identity></span></span>](identity.md)|<span data-ttu-id="7da5a-160">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="7da5a-160">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7da5a-161">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7da5a-161">Parent Elements</span></span>  
  
|<span data-ttu-id="7da5a-162">Elemento</span><span class="sxs-lookup"><span data-stu-id="7da5a-162">Element</span></span>|<span data-ttu-id="7da5a-163">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7da5a-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7da5a-164">\<client></span><span class="sxs-lookup"><span data-stu-id="7da5a-164">\<client></span></span>](client.md)|<span data-ttu-id="7da5a-165">Una sección de configuración que define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="7da5a-165">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7da5a-166">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7da5a-166">Example</span></span>  
 <span data-ttu-id="7da5a-167">Éste es un ejemplo de una configuración del extremo del canal.</span><span class="sxs-lookup"><span data-stu-id="7da5a-167">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="7da5a-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="7da5a-168">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="7da5a-169">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="7da5a-169">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="7da5a-170">Clientes</span><span class="sxs-lookup"><span data-stu-id="7da5a-170">Clients</span></span>](../../../wcf/feature-details/clients.md)

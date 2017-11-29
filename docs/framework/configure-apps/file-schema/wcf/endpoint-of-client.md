---
title: Elemento &lt;endpoint&gt; de &lt;client&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
caps.latest.revision: "22"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 87c83826d45942deb682087ad717070bd1ea4471
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltendpointgt-of-ltclientgt"></a><span data-ttu-id="0573e-102">Elemento &lt;endpoint&gt; de &lt;client&gt;</span><span class="sxs-lookup"><span data-stu-id="0573e-102">&lt;endpoint&gt; of &lt;client&gt;</span></span>
<span data-ttu-id="0573e-103">Especifica el contrato, enlace y propiedades de dirección del punto de conexión del canal, que es utilizado por clientes para conectar a los puntos de conexión de servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="0573e-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
 <span data-ttu-id="0573e-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0573e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0573e-105">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="0573e-105">\<client></span></span>  
<span data-ttu-id="0573e-106">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="0573e-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0573e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0573e-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"  
   behaviorConfiguration="String"  
   binding="String"  
   bindingConfiguration="String"  
   contract="String"   endpointConfiguration="String"   kind="String"  
   name="String"  
</endpoint>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0573e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0573e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0573e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0573e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0573e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0573e-110">Attributes</span></span>  
  
|<span data-ttu-id="0573e-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="0573e-111">Attribute</span></span>|<span data-ttu-id="0573e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0573e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0573e-113">address</span><span class="sxs-lookup"><span data-stu-id="0573e-113">address</span></span>|<span data-ttu-id="0573e-114">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="0573e-114">Required string attribute.</span></span><br /><br /> <span data-ttu-id="0573e-115">Especifica la dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="0573e-115">Specifies the address of the endpoint.</span></span> <span data-ttu-id="0573e-116">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="0573e-116">The default is an empty string.</span></span> <span data-ttu-id="0573e-117">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="0573e-117">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="0573e-118">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="0573e-118">behaviorConfiguration</span></span>|<span data-ttu-id="0573e-119">Una cadena que contiene el nombre de comportamiento del comportamiento que se va a usar para crear una instancia del extremo.</span><span class="sxs-lookup"><span data-stu-id="0573e-119">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="0573e-120">El nombre de comportamiento debe estar en el ámbito en el punto definido del servicio.</span><span class="sxs-lookup"><span data-stu-id="0573e-120">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="0573e-121">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="0573e-121">The default is an empty string.</span></span>|  
|<span data-ttu-id="0573e-122">enlace</span><span class="sxs-lookup"><span data-stu-id="0573e-122">binding</span></span>|<span data-ttu-id="0573e-123">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="0573e-123">Required string attribute.</span></span><br /><br /> <span data-ttu-id="0573e-124">Una cadena que indica el tipo de enlace que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="0573e-124">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="0573e-125">El tipo debe tener una sección de configuración registrada para que se haga referencia al mismo.</span><span class="sxs-lookup"><span data-stu-id="0573e-125">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="0573e-126">El tipo está registrado por el nombre de sección, en lugar de por el nombre de tipo del enlace.</span><span class="sxs-lookup"><span data-stu-id="0573e-126">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="0573e-127">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0573e-127">bindingConfiguration</span></span>|<span data-ttu-id="0573e-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="0573e-128">Optional.</span></span> <span data-ttu-id="0573e-129">Una cadena que contiene el nombre de la configuración de enlace que se va a utilizar cuando se instancia el extremo.</span><span class="sxs-lookup"><span data-stu-id="0573e-129">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="0573e-130">La configuración del enlace debe estar en el ámbito en el punto definido del extremo.</span><span class="sxs-lookup"><span data-stu-id="0573e-130">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="0573e-131">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="0573e-131">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="0573e-132">Este atributo se utiliza junto con `binding` para hacer referencia a una configuración de enlace concreta en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="0573e-132">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="0573e-133">Establezca este atributo si está intentando utilizar un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="0573e-133">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="0573e-134">De lo contrario, puede producirse una excepción.</span><span class="sxs-lookup"><span data-stu-id="0573e-134">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="0573e-135">contrato</span><span class="sxs-lookup"><span data-stu-id="0573e-135">contract</span></span>|<span data-ttu-id="0573e-136">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="0573e-136">Required string attribute.</span></span><br /><br /> <span data-ttu-id="0573e-137">Una cadena que indica qué contrato está exponiendo este extremo.</span><span class="sxs-lookup"><span data-stu-id="0573e-137">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="0573e-138">El ensamblado debe implementar el tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="0573e-138">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="0573e-139">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="0573e-139">endpointConfiguration</span></span>|<span data-ttu-id="0573e-140">Cadena que especifica el nombre del extremo estándar establecido por el atributo `kind`, que hace referencia a la información de configuración adicional de este extremo estándar.</span><span class="sxs-lookup"><span data-stu-id="0573e-140">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="0573e-141">El mismo nombre se debe definir en la sección `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="0573e-141">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="0573e-142">kind</span><span class="sxs-lookup"><span data-stu-id="0573e-142">kind</span></span>|<span data-ttu-id="0573e-143">Cadena que especifica el tipo de extremo estándar aplicado.</span><span class="sxs-lookup"><span data-stu-id="0573e-143">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="0573e-144">El tipo se debe registrar en la sección `<extensions>` o en machine.config. Si no se especifica nada, se crea un extremo de canal común.</span><span class="sxs-lookup"><span data-stu-id="0573e-144">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="0573e-145">name</span><span class="sxs-lookup"><span data-stu-id="0573e-145">name</span></span>|<span data-ttu-id="0573e-146">Atributo de cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="0573e-146">Optional string attribute.</span></span> <span data-ttu-id="0573e-147">Este atributo identifica singularmente un extremo para un contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="0573e-147">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="0573e-148">Puede definir varios clientes para un tipo de contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="0573e-148">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="0573e-149">Cada definición tiene que diferenciarse por un nombre de configuración unívoco.</span><span class="sxs-lookup"><span data-stu-id="0573e-149">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="0573e-150">Si se omite este atributo, el extremo correspondiente se usa como el extremo predeterminado asociado al tipo de contrato especificado.</span><span class="sxs-lookup"><span data-stu-id="0573e-150">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="0573e-151">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="0573e-151">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="0573e-152">El atributo de `name` de un enlace se utiliza para la exportación de la definición a través de WSDL.</span><span class="sxs-lookup"><span data-stu-id="0573e-152">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0573e-153">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0573e-153">Child Elements</span></span>  
  
|<span data-ttu-id="0573e-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="0573e-154">Element</span></span>|<span data-ttu-id="0573e-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="0573e-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0573e-156">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="0573e-156">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="0573e-157">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="0573e-157">A collection of address headers.</span></span>|  
|[<span data-ttu-id="0573e-158">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="0573e-158">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="0573e-159">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="0573e-159">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0573e-160">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0573e-160">Parent Elements</span></span>  
  
|<span data-ttu-id="0573e-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="0573e-161">Element</span></span>|<span data-ttu-id="0573e-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="0573e-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0573e-163">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="0573e-163">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="0573e-164">Una sección de configuración que define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="0573e-164">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0573e-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0573e-165">Example</span></span>  
 <span data-ttu-id="0573e-166">Éste es un ejemplo de una configuración del punto de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="0573e-166">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"  
    bindingConfiguration="usingDefaults"  
    name="MyBinding"  
    binding="customBinding"  
    contract="HelloWorld">  
</endpoint>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0573e-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="0573e-167">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>  
 <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>  
 [<span data-ttu-id="0573e-168">Configuración de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="0573e-168">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="0573e-169">Clientes</span><span class="sxs-lookup"><span data-stu-id="0573e-169">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)

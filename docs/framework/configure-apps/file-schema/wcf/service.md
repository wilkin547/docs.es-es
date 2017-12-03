---
title: '&lt;servicio&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 61c8d8451e271e756fce6f83a4f8b8fd4c8b9f77
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicegt"></a><span data-ttu-id="e713c-102">&lt;servicio&gt;</span><span class="sxs-lookup"><span data-stu-id="e713c-102">&lt;service&gt;</span></span>
<span data-ttu-id="e713c-103">El elemento `service` contiene los valores para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e713c-103">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="e713c-104">También contiene puntos de conexión que exponen el servicio.</span><span class="sxs-lookup"><span data-stu-id="e713c-104">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="e713c-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e713c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e713c-106">\<Servicios ></span><span class="sxs-lookup"><span data-stu-id="e713c-106">\<services></span></span>  
<span data-ttu-id="e713c-107">\<servicio ></span><span class="sxs-lookup"><span data-stu-id="e713c-107">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e713c-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e713c-108">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration=String"  
        name="String"  
</service>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e713c-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e713c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e713c-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e713c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e713c-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e713c-111">Attributes</span></span>  
  
|<span data-ttu-id="e713c-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="e713c-112">Attribute</span></span>|<span data-ttu-id="e713c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e713c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e713c-114">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="e713c-114">behaviorConfiguration</span></span>|<span data-ttu-id="e713c-115">Una cadena que contiene el nombre de comportamiento que se va a usar para instanciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="e713c-115">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="e713c-116">El nombre de comportamiento debe estar en el ámbito en el punto definido del servicio.</span><span class="sxs-lookup"><span data-stu-id="e713c-116">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="e713c-117">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="e713c-117">The default value is an empty string.</span></span>|  
|<span data-ttu-id="e713c-118">name</span><span class="sxs-lookup"><span data-stu-id="e713c-118">name</span></span>|<span data-ttu-id="e713c-119">Atributo String necesario que especifica el tipo del servicio del que se van a crear instancias.</span><span class="sxs-lookup"><span data-stu-id="e713c-119">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="e713c-120">Este valor debe equivaler a un tipo válido.</span><span class="sxs-lookup"><span data-stu-id="e713c-120">This setting must equate to a valid type.</span></span> <span data-ttu-id="e713c-121">El formato debería ser `Namespace.Class.`.</span><span class="sxs-lookup"><span data-stu-id="e713c-121">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e713c-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e713c-122">Child Elements</span></span>  
  
|<span data-ttu-id="e713c-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e713c-123">Element</span></span>|<span data-ttu-id="e713c-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="e713c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e713c-125">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="e713c-125">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|<span data-ttu-id="e713c-126">Una colección de elementos `endpoint` que exponen este servicio.</span><span class="sxs-lookup"><span data-stu-id="e713c-126">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="e713c-127">\<host ></span><span class="sxs-lookup"><span data-stu-id="e713c-127">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="e713c-128">Especifica el host de esta instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="e713c-128">Specifies the host of this service instance.</span></span> <span data-ttu-id="e713c-129">Este elemento es del tipo <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="e713c-129">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e713c-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e713c-130">Parent Elements</span></span>  
  
|<span data-ttu-id="e713c-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="e713c-131">Element</span></span>|<span data-ttu-id="e713c-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="e713c-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e713c-133">\<Servicios ></span><span class="sxs-lookup"><span data-stu-id="e713c-133">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="e713c-134">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="e713c-134">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e713c-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e713c-135">Remarks</span></span>  
 <span data-ttu-id="e713c-136">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e713c-136">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="e713c-137">Un ensamblado puede contener cualquier número de servicios.</span><span class="sxs-lookup"><span data-stu-id="e713c-137">An assembly can contain any number of services.</span></span> <span data-ttu-id="e713c-138">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="e713c-138">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="e713c-139">Esta sección y su contenido definen el contrato de servicios, comportamiento y extremos del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="e713c-139">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="e713c-140">El elemento `behaviorConfiguration` también es opcional.</span><span class="sxs-lookup"><span data-stu-id="e713c-140">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="e713c-141">Identifica el comportamiento que el servicio utiliza.</span><span class="sxs-lookup"><span data-stu-id="e713c-141">It identifies the behavior the service uses.</span></span> <span data-ttu-id="e713c-142">El comportamiento especificado en este atributo debe vincular a un comportamiento en ámbito en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e713c-142">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="e713c-143">Cada servicio expone uno o más extremos, que tienen su propia dirección y enlace.</span><span class="sxs-lookup"><span data-stu-id="e713c-143">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="e713c-144">Todos los enlaces usados dentro del archivo de configuración se deben definir en el ámbito del archivo.</span><span class="sxs-lookup"><span data-stu-id="e713c-144">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="e713c-145">Los enlaces se vinculan a los extremos a través de la combinación de los atributos `name` y `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="e713c-145">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="e713c-146">El atributo `name` describe la sección en la que está definido el enlace.</span><span class="sxs-lookup"><span data-stu-id="e713c-146">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="e713c-147">El atributo `bindingConfiguration` define qué configuración se usa dentro de la sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="e713c-147">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="e713c-148">Una sección de enlace puede definir varias configuraciones.</span><span class="sxs-lookup"><span data-stu-id="e713c-148">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e713c-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e713c-149">Example</span></span>  
 <span data-ttu-id="e713c-150">Éste es un ejemplo de una configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="e713c-150">This is an example of a service configuration.</span></span>  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"   
     name="HelloWorld">  
     <endpoint   
        address="/HelloWorld2/"  
        name="test"  
        bindingNamespace="http://www.cohowinery.com/"  
        binding="basicHttpBinding"  
        contract="IHelloWorld" />  
</service>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e713c-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="e713c-151">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceElement>  
 [<span data-ttu-id="e713c-152">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="e713c-152">Configuring Services</span></span>](../../../../../docs/framework/wcf/configuring-services.md)

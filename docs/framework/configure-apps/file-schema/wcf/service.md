---
title: '&lt;Servicio&gt;'
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 6e83e988920d24c6fe7615e40334919caf21652e
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2018
---
# <a name="ltservicegt"></a><span data-ttu-id="11b6a-102">&lt;Servicio&gt;</span><span class="sxs-lookup"><span data-stu-id="11b6a-102">&lt;service&gt;</span></span>
<span data-ttu-id="11b6a-103">El elemento `service` contiene los valores para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="11b6a-103">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="11b6a-104">También contiene puntos de conexión que exponen el servicio.</span><span class="sxs-lookup"><span data-stu-id="11b6a-104">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="11b6a-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="11b6a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="11b6a-106">\<Servicios ></span><span class="sxs-lookup"><span data-stu-id="11b6a-106">\<services></span></span>  
<span data-ttu-id="11b6a-107">\<servicio ></span><span class="sxs-lookup"><span data-stu-id="11b6a-107">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11b6a-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11b6a-108">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration=String"  
        name="String">  
</service>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11b6a-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="11b6a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="11b6a-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="11b6a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11b6a-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="11b6a-111">Attributes</span></span>  
  
|<span data-ttu-id="11b6a-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="11b6a-112">Attribute</span></span>|<span data-ttu-id="11b6a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="11b6a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="11b6a-114">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="11b6a-114">behaviorConfiguration</span></span>|<span data-ttu-id="11b6a-115">Una cadena que contiene el nombre de comportamiento que se va a usar para instanciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="11b6a-115">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="11b6a-116">El nombre de comportamiento debe estar en el ámbito en el punto definido del servicio.</span><span class="sxs-lookup"><span data-stu-id="11b6a-116">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="11b6a-117">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="11b6a-117">The default value is an empty string.</span></span>|  
|<span data-ttu-id="11b6a-118">name</span><span class="sxs-lookup"><span data-stu-id="11b6a-118">name</span></span>|<span data-ttu-id="11b6a-119">Atributo String necesario que especifica el tipo del servicio del que se van a crear instancias.</span><span class="sxs-lookup"><span data-stu-id="11b6a-119">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="11b6a-120">Este valor debe equivaler a un tipo válido.</span><span class="sxs-lookup"><span data-stu-id="11b6a-120">This setting must equate to a valid type.</span></span> <span data-ttu-id="11b6a-121">El formato debería ser `Namespace.Class.`.</span><span class="sxs-lookup"><span data-stu-id="11b6a-121">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11b6a-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="11b6a-122">Child Elements</span></span>  
  
|<span data-ttu-id="11b6a-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="11b6a-123">Element</span></span>|<span data-ttu-id="11b6a-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="11b6a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11b6a-125">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="11b6a-125">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|<span data-ttu-id="11b6a-126">Una colección de elementos `endpoint` que exponen este servicio.</span><span class="sxs-lookup"><span data-stu-id="11b6a-126">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="11b6a-127">\<host ></span><span class="sxs-lookup"><span data-stu-id="11b6a-127">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="11b6a-128">Especifica el host de esta instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="11b6a-128">Specifies the host of this service instance.</span></span> <span data-ttu-id="11b6a-129">Este elemento es del tipo <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="11b6a-129">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="11b6a-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="11b6a-130">Parent Elements</span></span>  
  
|<span data-ttu-id="11b6a-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="11b6a-131">Element</span></span>|<span data-ttu-id="11b6a-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="11b6a-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11b6a-133">\<Servicios ></span><span class="sxs-lookup"><span data-stu-id="11b6a-133">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="11b6a-134">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="11b6a-134">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11b6a-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="11b6a-135">Remarks</span></span>  
 <span data-ttu-id="11b6a-136">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="11b6a-136">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="11b6a-137">Un ensamblado puede contener cualquier número de servicios.</span><span class="sxs-lookup"><span data-stu-id="11b6a-137">An assembly can contain any number of services.</span></span> <span data-ttu-id="11b6a-138">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="11b6a-138">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="11b6a-139">Esta sección y su contenido definen el contrato de servicios, comportamiento y extremos del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="11b6a-139">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="11b6a-140">El elemento `behaviorConfiguration` también es opcional.</span><span class="sxs-lookup"><span data-stu-id="11b6a-140">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="11b6a-141">Identifica el comportamiento que el servicio utiliza.</span><span class="sxs-lookup"><span data-stu-id="11b6a-141">It identifies the behavior the service uses.</span></span> <span data-ttu-id="11b6a-142">El comportamiento especificado en este atributo debe vincular a un comportamiento en ámbito en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="11b6a-142">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="11b6a-143">Cada servicio expone uno o más extremos, que tienen su propia dirección y enlace.</span><span class="sxs-lookup"><span data-stu-id="11b6a-143">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="11b6a-144">Todos los enlaces usados dentro del archivo de configuración se deben definir en el ámbito del archivo.</span><span class="sxs-lookup"><span data-stu-id="11b6a-144">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="11b6a-145">Los enlaces se vinculan a los extremos a través de la combinación de los atributos `name` y `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="11b6a-145">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="11b6a-146">El atributo `name` describe la sección en la que está definido el enlace.</span><span class="sxs-lookup"><span data-stu-id="11b6a-146">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="11b6a-147">El atributo `bindingConfiguration` define qué configuración se usa dentro de la sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="11b6a-147">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="11b6a-148">Una sección de enlace puede definir varias configuraciones.</span><span class="sxs-lookup"><span data-stu-id="11b6a-148">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11b6a-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11b6a-149">Example</span></span>  
 <span data-ttu-id="11b6a-150">Éste es un ejemplo de una configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="11b6a-150">This is an example of a service configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="11b6a-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="11b6a-151">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceElement>  
 [<span data-ttu-id="11b6a-152">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="11b6a-152">Configuring Services</span></span>](../../../../../docs/framework/wcf/configuring-services.md)

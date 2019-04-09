---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 68bddc01b02d9885b3f0fc4c2cbc5c3249de03f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197963"
---
# <a name="service"></a><span data-ttu-id="f45d9-101">\<service></span><span class="sxs-lookup"><span data-stu-id="f45d9-101">\<service></span></span>
<span data-ttu-id="f45d9-102">El elemento `service` contiene los valores para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f45d9-102">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="f45d9-103">También contiene puntos de conexión que exponen el servicio.</span><span class="sxs-lookup"><span data-stu-id="f45d9-103">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="f45d9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f45d9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f45d9-105">\<services></span><span class="sxs-lookup"><span data-stu-id="f45d9-105">\<services></span></span>  
<span data-ttu-id="f45d9-106">\<service></span><span class="sxs-lookup"><span data-stu-id="f45d9-106">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f45d9-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f45d9-107">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f45d9-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f45d9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f45d9-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f45d9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f45d9-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f45d9-110">Attributes</span></span>  
  
|<span data-ttu-id="f45d9-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="f45d9-111">Attribute</span></span>|<span data-ttu-id="f45d9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f45d9-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f45d9-113">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="f45d9-113">behaviorConfiguration</span></span>|<span data-ttu-id="f45d9-114">Una cadena que contiene el nombre de comportamiento que se va a usar para instanciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="f45d9-114">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="f45d9-115">El nombre de comportamiento debe estar en el ámbito en el punto definido del servicio.</span><span class="sxs-lookup"><span data-stu-id="f45d9-115">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="f45d9-116">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="f45d9-116">The default value is an empty string.</span></span>|  
|<span data-ttu-id="f45d9-117">name</span><span class="sxs-lookup"><span data-stu-id="f45d9-117">name</span></span>|<span data-ttu-id="f45d9-118">Atributo String necesario que especifica el tipo del servicio del que se van a crear instancias.</span><span class="sxs-lookup"><span data-stu-id="f45d9-118">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="f45d9-119">Este valor debe equivaler a un tipo válido.</span><span class="sxs-lookup"><span data-stu-id="f45d9-119">This setting must equate to a valid type.</span></span> <span data-ttu-id="f45d9-120">El formato debe ser</span><span class="sxs-lookup"><span data-stu-id="f45d9-120">The format should be</span></span> `Namespace.Class.`|  
  
### <a name="child-elements"></a><span data-ttu-id="f45d9-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f45d9-121">Child Elements</span></span>  
  
|<span data-ttu-id="f45d9-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="f45d9-122">Element</span></span>|<span data-ttu-id="f45d9-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="f45d9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f45d9-124">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="f45d9-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|<span data-ttu-id="f45d9-125">Una colección de elementos `endpoint` que exponen este servicio.</span><span class="sxs-lookup"><span data-stu-id="f45d9-125">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="f45d9-126">\<host ></span><span class="sxs-lookup"><span data-stu-id="f45d9-126">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="f45d9-127">Especifica el host de esta instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="f45d9-127">Specifies the host of this service instance.</span></span> <span data-ttu-id="f45d9-128">Este elemento es del tipo <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="f45d9-128">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f45d9-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f45d9-129">Parent Elements</span></span>  
  
|<span data-ttu-id="f45d9-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="f45d9-130">Element</span></span>|<span data-ttu-id="f45d9-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="f45d9-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f45d9-132">\<services></span><span class="sxs-lookup"><span data-stu-id="f45d9-132">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="f45d9-133">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="f45d9-133">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f45d9-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f45d9-134">Remarks</span></span>  
 <span data-ttu-id="f45d9-135">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f45d9-135">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="f45d9-136">Un ensamblado puede contener cualquier número de servicios.</span><span class="sxs-lookup"><span data-stu-id="f45d9-136">An assembly can contain any number of services.</span></span> <span data-ttu-id="f45d9-137">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="f45d9-137">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="f45d9-138">Esta sección y su contenido definen el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="f45d9-138">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="f45d9-139">El elemento `behaviorConfiguration` también es opcional.</span><span class="sxs-lookup"><span data-stu-id="f45d9-139">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="f45d9-140">Identifica el comportamiento que el servicio utiliza.</span><span class="sxs-lookup"><span data-stu-id="f45d9-140">It identifies the behavior the service uses.</span></span> <span data-ttu-id="f45d9-141">El comportamiento especificado en este atributo debe vincular a un comportamiento en ámbito en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f45d9-141">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="f45d9-142">Cada servicio expone uno o más extremos, que tienen su propia dirección y enlace.</span><span class="sxs-lookup"><span data-stu-id="f45d9-142">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="f45d9-143">Todos los enlaces usados dentro del archivo de configuración se deben definir en el ámbito del archivo.</span><span class="sxs-lookup"><span data-stu-id="f45d9-143">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="f45d9-144">Los enlaces se vinculan a los puntos de conexión a través de la combinación de los atributos `name` y `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="f45d9-144">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="f45d9-145">El atributo `name` describe la sección en la que está definido el enlace.</span><span class="sxs-lookup"><span data-stu-id="f45d9-145">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="f45d9-146">El atributo `bindingConfiguration` define qué configuración se usa dentro de la sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="f45d9-146">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="f45d9-147">Una sección de enlace puede definir varias configuraciones.</span><span class="sxs-lookup"><span data-stu-id="f45d9-147">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f45d9-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f45d9-148">Example</span></span>  
 <span data-ttu-id="f45d9-149">Éste es un ejemplo de una configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="f45d9-149">This is an example of a service configuration.</span></span>  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"
         name="HelloWorld">
  <endpoint address="/HelloWorld2/"
            name="test"
            bindingNamespace="http://www.cohowinery.com/"
            binding="basicHttpBinding"
            contract="IHelloWorld" />
</service>
```  
  
## <a name="see-also"></a><span data-ttu-id="f45d9-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="f45d9-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="f45d9-151">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="f45d9-151">Configuring Services</span></span>](../../../../../docs/framework/wcf/configuring-services.md)

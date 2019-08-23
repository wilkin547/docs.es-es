---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 69f3c70514fc2bcab1b4ef6a45036de98d1af7b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936526"
---
# <a name="service"></a><span data-ttu-id="a24ea-101">\<service></span><span class="sxs-lookup"><span data-stu-id="a24ea-101">\<service></span></span>
<span data-ttu-id="a24ea-102">El elemento `service` contiene los valores para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a24ea-102">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="a24ea-103">También contiene puntos de conexión que exponen el servicio.</span><span class="sxs-lookup"><span data-stu-id="a24ea-103">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="a24ea-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a24ea-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a24ea-105">\<> de servicios</span><span class="sxs-lookup"><span data-stu-id="a24ea-105">\<services></span></span>  
<span data-ttu-id="a24ea-106">\<service></span><span class="sxs-lookup"><span data-stu-id="a24ea-106">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a24ea-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a24ea-107">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a24ea-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a24ea-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a24ea-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a24ea-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a24ea-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a24ea-110">Attributes</span></span>  
  
|<span data-ttu-id="a24ea-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="a24ea-111">Attribute</span></span>|<span data-ttu-id="a24ea-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a24ea-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a24ea-113">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="a24ea-113">behaviorConfiguration</span></span>|<span data-ttu-id="a24ea-114">Una cadena que contiene el nombre de comportamiento que se va a usar para instanciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="a24ea-114">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="a24ea-115">El nombre de comportamiento debe estar en el ámbito en el punto definido del servicio.</span><span class="sxs-lookup"><span data-stu-id="a24ea-115">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="a24ea-116">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="a24ea-116">The default value is an empty string.</span></span>|  
|<span data-ttu-id="a24ea-117">Nombre</span><span class="sxs-lookup"><span data-stu-id="a24ea-117">name</span></span>|<span data-ttu-id="a24ea-118">Atributo String necesario que especifica el tipo del servicio del que se van a crear instancias.</span><span class="sxs-lookup"><span data-stu-id="a24ea-118">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="a24ea-119">Este valor debe equivaler a un tipo válido.</span><span class="sxs-lookup"><span data-stu-id="a24ea-119">This setting must equate to a valid type.</span></span> <span data-ttu-id="a24ea-120">El formato debería ser `Namespace.Class.`.</span><span class="sxs-lookup"><span data-stu-id="a24ea-120">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a24ea-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a24ea-121">Child Elements</span></span>  
  
|<span data-ttu-id="a24ea-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="a24ea-122">Element</span></span>|<span data-ttu-id="a24ea-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a24ea-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a24ea-124">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="a24ea-124">\<endpoint></span></span>](endpoint-element.md)|<span data-ttu-id="a24ea-125">Una colección de elementos `endpoint` que exponen este servicio.</span><span class="sxs-lookup"><span data-stu-id="a24ea-125">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="a24ea-126">\<> host</span><span class="sxs-lookup"><span data-stu-id="a24ea-126">\<host></span></span>](host.md)|<span data-ttu-id="a24ea-127">Especifica el host de esta instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="a24ea-127">Specifies the host of this service instance.</span></span> <span data-ttu-id="a24ea-128">Este elemento es del tipo <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="a24ea-128">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a24ea-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a24ea-129">Parent Elements</span></span>  
  
|<span data-ttu-id="a24ea-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="a24ea-130">Element</span></span>|<span data-ttu-id="a24ea-131">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a24ea-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a24ea-132">\<services></span><span class="sxs-lookup"><span data-stu-id="a24ea-132">\<services></span></span>](services.md)|<span data-ttu-id="a24ea-133">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="a24ea-133">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a24ea-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a24ea-134">Remarks</span></span>  
 <span data-ttu-id="a24ea-135">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a24ea-135">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="a24ea-136">Un ensamblado puede contener cualquier número de servicios.</span><span class="sxs-lookup"><span data-stu-id="a24ea-136">An assembly can contain any number of services.</span></span> <span data-ttu-id="a24ea-137">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="a24ea-137">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="a24ea-138">Esta sección y su contenido definen el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="a24ea-138">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="a24ea-139">El elemento `behaviorConfiguration` también es opcional.</span><span class="sxs-lookup"><span data-stu-id="a24ea-139">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="a24ea-140">Identifica el comportamiento que el servicio utiliza.</span><span class="sxs-lookup"><span data-stu-id="a24ea-140">It identifies the behavior the service uses.</span></span> <span data-ttu-id="a24ea-141">El comportamiento especificado en este atributo debe vincular a un comportamiento en ámbito en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a24ea-141">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="a24ea-142">Cada servicio expone uno o más extremos, que tienen su propia dirección y enlace.</span><span class="sxs-lookup"><span data-stu-id="a24ea-142">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="a24ea-143">Todos los enlaces usados dentro del archivo de configuración se deben definir en el ámbito del archivo.</span><span class="sxs-lookup"><span data-stu-id="a24ea-143">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="a24ea-144">Los enlaces se vinculan a los puntos de conexión a través de la combinación de los atributos `name` y `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="a24ea-144">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="a24ea-145">El atributo `name` describe la sección en la que está definido el enlace.</span><span class="sxs-lookup"><span data-stu-id="a24ea-145">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="a24ea-146">El atributo `bindingConfiguration` define qué configuración se usa dentro de la sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="a24ea-146">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="a24ea-147">Una sección de enlace puede definir varias configuraciones.</span><span class="sxs-lookup"><span data-stu-id="a24ea-147">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a24ea-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a24ea-148">Example</span></span>  
 <span data-ttu-id="a24ea-149">Éste es un ejemplo de una configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="a24ea-149">This is an example of a service configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a24ea-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="a24ea-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="a24ea-151">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="a24ea-151">Configuring Services</span></span>](../../../wcf/configuring-services.md)

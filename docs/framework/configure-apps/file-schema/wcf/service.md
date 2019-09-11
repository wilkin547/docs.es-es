---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: c12f57d68de870123d92c8a101e2999c24bb988f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855023"
---
# <a name="service"></a><span data-ttu-id="ee91d-101">\<service></span><span class="sxs-lookup"><span data-stu-id="ee91d-101">\<service></span></span>
<span data-ttu-id="ee91d-102">El elemento `service` contiene los valores para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ee91d-102">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="ee91d-103">También contiene puntos de conexión que exponen el servicio.</span><span class="sxs-lookup"><span data-stu-id="ee91d-103">It also contains endpoints that expose the service.</span></span>  
  
<span data-ttu-id="ee91d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ee91d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ee91d-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ee91d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ee91d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de servicios**](services.md)</span><span class="sxs-lookup"><span data-stu-id="ee91d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="ee91d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de servicio**</span><span class="sxs-lookup"><span data-stu-id="ee91d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<service>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee91d-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee91d-108">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee91d-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ee91d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ee91d-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ee91d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee91d-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="ee91d-111">Attributes</span></span>  
  
|<span data-ttu-id="ee91d-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="ee91d-112">Attribute</span></span>|<span data-ttu-id="ee91d-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ee91d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ee91d-114">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="ee91d-114">behaviorConfiguration</span></span>|<span data-ttu-id="ee91d-115">Una cadena que contiene el nombre de comportamiento que se va a usar para instanciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="ee91d-115">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="ee91d-116">El nombre de comportamiento debe estar en el ámbito en el punto definido del servicio.</span><span class="sxs-lookup"><span data-stu-id="ee91d-116">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="ee91d-117">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="ee91d-117">The default value is an empty string.</span></span>|  
|<span data-ttu-id="ee91d-118">Nombre</span><span class="sxs-lookup"><span data-stu-id="ee91d-118">name</span></span>|<span data-ttu-id="ee91d-119">Atributo String necesario que especifica el tipo del servicio del que se van a crear instancias.</span><span class="sxs-lookup"><span data-stu-id="ee91d-119">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="ee91d-120">Este valor debe equivaler a un tipo válido.</span><span class="sxs-lookup"><span data-stu-id="ee91d-120">This setting must equate to a valid type.</span></span> <span data-ttu-id="ee91d-121">El formato debería ser `Namespace.Class.`.</span><span class="sxs-lookup"><span data-stu-id="ee91d-121">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee91d-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ee91d-122">Child Elements</span></span>  
  
|<span data-ttu-id="ee91d-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee91d-123">Element</span></span>|<span data-ttu-id="ee91d-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ee91d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee91d-125">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="ee91d-125">\<endpoint></span></span>](endpoint-element.md)|<span data-ttu-id="ee91d-126">Una colección de elementos `endpoint` que exponen este servicio.</span><span class="sxs-lookup"><span data-stu-id="ee91d-126">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="ee91d-127">\<> host</span><span class="sxs-lookup"><span data-stu-id="ee91d-127">\<host></span></span>](host.md)|<span data-ttu-id="ee91d-128">Especifica el host de esta instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="ee91d-128">Specifies the host of this service instance.</span></span> <span data-ttu-id="ee91d-129">Este elemento es del tipo <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="ee91d-129">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ee91d-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ee91d-130">Parent Elements</span></span>  
  
|<span data-ttu-id="ee91d-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee91d-131">Element</span></span>|<span data-ttu-id="ee91d-132">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ee91d-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee91d-133">\<services></span><span class="sxs-lookup"><span data-stu-id="ee91d-133">\<services></span></span>](services.md)|<span data-ttu-id="ee91d-134">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="ee91d-134">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee91d-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ee91d-135">Remarks</span></span>  
 <span data-ttu-id="ee91d-136">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ee91d-136">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="ee91d-137">Un ensamblado puede contener cualquier número de servicios.</span><span class="sxs-lookup"><span data-stu-id="ee91d-137">An assembly can contain any number of services.</span></span> <span data-ttu-id="ee91d-138">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="ee91d-138">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="ee91d-139">Esta sección y su contenido definen el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="ee91d-139">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="ee91d-140">El elemento `behaviorConfiguration` también es opcional.</span><span class="sxs-lookup"><span data-stu-id="ee91d-140">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="ee91d-141">Identifica el comportamiento que el servicio utiliza.</span><span class="sxs-lookup"><span data-stu-id="ee91d-141">It identifies the behavior the service uses.</span></span> <span data-ttu-id="ee91d-142">El comportamiento especificado en este atributo debe vincular a un comportamiento en ámbito en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ee91d-142">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="ee91d-143">Cada servicio expone uno o más extremos, que tienen su propia dirección y enlace.</span><span class="sxs-lookup"><span data-stu-id="ee91d-143">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="ee91d-144">Todos los enlaces usados dentro del archivo de configuración se deben definir en el ámbito del archivo.</span><span class="sxs-lookup"><span data-stu-id="ee91d-144">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="ee91d-145">Los enlaces se vinculan a los puntos de conexión a través de la combinación de los atributos `name` y `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="ee91d-145">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="ee91d-146">El atributo `name` describe la sección en la que está definido el enlace.</span><span class="sxs-lookup"><span data-stu-id="ee91d-146">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="ee91d-147">El atributo `bindingConfiguration` define qué configuración se usa dentro de la sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="ee91d-147">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="ee91d-148">Una sección de enlace puede definir varias configuraciones.</span><span class="sxs-lookup"><span data-stu-id="ee91d-148">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee91d-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ee91d-149">Example</span></span>  
 <span data-ttu-id="ee91d-150">Éste es un ejemplo de una configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="ee91d-150">This is an example of a service configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ee91d-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee91d-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="ee91d-152">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="ee91d-152">Configuring Services</span></span>](../../../wcf/configuring-services.md)

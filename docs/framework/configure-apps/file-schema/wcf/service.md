---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: dcc32f5aa055942408a3f01d37b5aa27ac0f51ee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173775"
---
# \<service>

<span data-ttu-id="7ec6e-101">El elemento `service` contiene los valores para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="7ec6e-101">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="7ec6e-102">También contiene puntos de conexión que exponen el servicio.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-102">It also contains endpoints that expose the service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<service>**  
  
## <a name="syntax"></a><span data-ttu-id="7ec6e-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ec6e-103">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ec6e-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7ec6e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="7ec6e-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ec6e-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="7ec6e-106">Attributes</span></span>  
  
|<span data-ttu-id="7ec6e-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="7ec6e-107">Attribute</span></span>|<span data-ttu-id="7ec6e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ec6e-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7ec6e-109">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="7ec6e-109">behaviorConfiguration</span></span>|<span data-ttu-id="7ec6e-110">Una cadena que contiene el nombre de comportamiento que se va a usar para instanciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-110">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="7ec6e-111">El nombre de comportamiento debe estar en el ámbito en el punto definido del servicio.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-111">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="7ec6e-112">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-112">The default value is an empty string.</span></span>|  
|<span data-ttu-id="7ec6e-113">name</span><span class="sxs-lookup"><span data-stu-id="7ec6e-113">name</span></span>|<span data-ttu-id="7ec6e-114">Atributo String necesario que especifica el tipo del servicio del que se van a crear instancias.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-114">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="7ec6e-115">Este valor debe equivaler a un tipo válido.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-115">This setting must equate to a valid type.</span></span> <span data-ttu-id="7ec6e-116">El formato debería ser `Namespace.Class.`.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-116">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ec6e-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7ec6e-117">Child Elements</span></span>  
  
|<span data-ttu-id="7ec6e-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ec6e-118">Element</span></span>|<span data-ttu-id="7ec6e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ec6e-119">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="7ec6e-120">Una colección de elementos `endpoint` que exponen este servicio.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-120">A collection of `endpoint` elements that expose this service.</span></span>|  
|[\<host>](host.md)|<span data-ttu-id="7ec6e-121">Especifica el host de esta instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-121">Specifies the host of this service instance.</span></span> <span data-ttu-id="7ec6e-122">Este elemento es del tipo <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-122">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7ec6e-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7ec6e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7ec6e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ec6e-124">Element</span></span>|<span data-ttu-id="7ec6e-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ec6e-125">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services.md)|<span data-ttu-id="7ec6e-126">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-126">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ec6e-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7ec6e-127">Remarks</span></span>  

 <span data-ttu-id="7ec6e-128">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-128">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="7ec6e-129">Un ensamblado puede contener cualquier número de servicios.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-129">An assembly can contain any number of services.</span></span> <span data-ttu-id="7ec6e-130">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-130">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="7ec6e-131">Esta sección y su contenido definen el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-131">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="7ec6e-132">El elemento `behaviorConfiguration` también es opcional.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-132">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="7ec6e-133">Identifica el comportamiento que el servicio utiliza.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-133">It identifies the behavior the service uses.</span></span> <span data-ttu-id="7ec6e-134">El comportamiento especificado en este atributo debe vincular a un comportamiento en ámbito en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-134">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="7ec6e-135">Cada servicio expone uno o más extremos, que tienen su propia dirección y enlace.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-135">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="7ec6e-136">Todos los enlaces usados dentro del archivo de configuración se deben definir en el ámbito del archivo.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-136">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="7ec6e-137">Los enlaces se vinculan a los puntos de conexión a través de la combinación de los atributos `name` y `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-137">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="7ec6e-138">El atributo `name` describe la sección en la que está definido el enlace.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-138">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="7ec6e-139">El atributo `bindingConfiguration` define qué configuración se usa dentro de la sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-139">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="7ec6e-140">Una sección de enlace puede definir varias configuraciones.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-140">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ec6e-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7ec6e-141">Example</span></span>  

 <span data-ttu-id="7ec6e-142">Éste es un ejemplo de una configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="7ec6e-142">This is an example of a service configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7ec6e-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ec6e-143">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="7ec6e-144">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="7ec6e-144">Configuring Services</span></span>](../../../wcf/configuring-services.md)

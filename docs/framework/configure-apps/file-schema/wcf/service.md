---
description: 'Más información acerca de: <service>'
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: c3870a170847d773996625235c75591ced75e315
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786790"
---
# \<service>

<span data-ttu-id="03f1a-102">El elemento `service` contiene los valores para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="03f1a-102">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="03f1a-103">También contiene puntos de conexión que exponen el servicio.</span><span class="sxs-lookup"><span data-stu-id="03f1a-103">It also contains endpoints that expose the service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<service>**  
  
## <a name="syntax"></a><span data-ttu-id="03f1a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03f1a-104">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03f1a-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="03f1a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="03f1a-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="03f1a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03f1a-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="03f1a-107">Attributes</span></span>  
  
|<span data-ttu-id="03f1a-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="03f1a-108">Attribute</span></span>|<span data-ttu-id="03f1a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="03f1a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03f1a-110">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="03f1a-110">behaviorConfiguration</span></span>|<span data-ttu-id="03f1a-111">Una cadena que contiene el nombre de comportamiento que se va a usar para instanciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="03f1a-111">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="03f1a-112">El nombre de comportamiento debe estar en el ámbito en el punto definido del servicio.</span><span class="sxs-lookup"><span data-stu-id="03f1a-112">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="03f1a-113">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="03f1a-113">The default value is an empty string.</span></span>|  
|<span data-ttu-id="03f1a-114">name</span><span class="sxs-lookup"><span data-stu-id="03f1a-114">name</span></span>|<span data-ttu-id="03f1a-115">Atributo String necesario que especifica el tipo del servicio del que se van a crear instancias.</span><span class="sxs-lookup"><span data-stu-id="03f1a-115">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="03f1a-116">Este valor debe equivaler a un tipo válido.</span><span class="sxs-lookup"><span data-stu-id="03f1a-116">This setting must equate to a valid type.</span></span> <span data-ttu-id="03f1a-117">El formato debería ser `Namespace.Class.`.</span><span class="sxs-lookup"><span data-stu-id="03f1a-117">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03f1a-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="03f1a-118">Child Elements</span></span>  
  
|<span data-ttu-id="03f1a-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="03f1a-119">Element</span></span>|<span data-ttu-id="03f1a-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="03f1a-120">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="03f1a-121">Una colección de elementos `endpoint` que exponen este servicio.</span><span class="sxs-lookup"><span data-stu-id="03f1a-121">A collection of `endpoint` elements that expose this service.</span></span>|  
|[\<host>](host.md)|<span data-ttu-id="03f1a-122">Especifica el host de esta instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="03f1a-122">Specifies the host of this service instance.</span></span> <span data-ttu-id="03f1a-123">Este elemento es del tipo <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="03f1a-123">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03f1a-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="03f1a-124">Parent Elements</span></span>  
  
|<span data-ttu-id="03f1a-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="03f1a-125">Element</span></span>|<span data-ttu-id="03f1a-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="03f1a-126">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services.md)|<span data-ttu-id="03f1a-127">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="03f1a-127">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03f1a-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="03f1a-128">Remarks</span></span>  

 <span data-ttu-id="03f1a-129">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="03f1a-129">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="03f1a-130">Un ensamblado puede contener cualquier número de servicios.</span><span class="sxs-lookup"><span data-stu-id="03f1a-130">An assembly can contain any number of services.</span></span> <span data-ttu-id="03f1a-131">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="03f1a-131">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="03f1a-132">Esta sección y su contenido definen el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="03f1a-132">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="03f1a-133">El elemento `behaviorConfiguration` también es opcional.</span><span class="sxs-lookup"><span data-stu-id="03f1a-133">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="03f1a-134">Identifica el comportamiento que el servicio utiliza.</span><span class="sxs-lookup"><span data-stu-id="03f1a-134">It identifies the behavior the service uses.</span></span> <span data-ttu-id="03f1a-135">El comportamiento especificado en este atributo debe vincular a un comportamiento en ámbito en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="03f1a-135">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="03f1a-136">Cada servicio expone uno o más extremos, que tienen su propia dirección y enlace.</span><span class="sxs-lookup"><span data-stu-id="03f1a-136">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="03f1a-137">Todos los enlaces usados dentro del archivo de configuración se deben definir en el ámbito del archivo.</span><span class="sxs-lookup"><span data-stu-id="03f1a-137">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="03f1a-138">Los enlaces se vinculan a los puntos de conexión a través de la combinación de los atributos `name` y `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="03f1a-138">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="03f1a-139">El atributo `name` describe la sección en la que está definido el enlace.</span><span class="sxs-lookup"><span data-stu-id="03f1a-139">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="03f1a-140">El atributo `bindingConfiguration` define qué configuración se usa dentro de la sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="03f1a-140">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="03f1a-141">Una sección de enlace puede definir varias configuraciones.</span><span class="sxs-lookup"><span data-stu-id="03f1a-141">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03f1a-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03f1a-142">Example</span></span>  

 <span data-ttu-id="03f1a-143">Éste es un ejemplo de una configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="03f1a-143">This is an example of a service configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="03f1a-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="03f1a-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="03f1a-145">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="03f1a-145">Configuring Services</span></span>](../../../wcf/configuring-services.md)

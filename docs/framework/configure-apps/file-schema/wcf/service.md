---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: c12f57d68de870123d92c8a101e2999c24bb988f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855023"
---
# \<service>
<span data-ttu-id="71a6f-101">El elemento `service` contiene los valores para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="71a6f-101">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="71a6f-102">También contiene puntos de conexión que exponen el servicio.</span><span class="sxs-lookup"><span data-stu-id="71a6f-102">It also contains endpoints that expose the service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<service>**  
  
## <a name="syntax"></a><span data-ttu-id="71a6f-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71a6f-103">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71a6f-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="71a6f-104">Attributes and Elements</span></span>  
 <span data-ttu-id="71a6f-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="71a6f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71a6f-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="71a6f-106">Attributes</span></span>  
  
|<span data-ttu-id="71a6f-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="71a6f-107">Attribute</span></span>|<span data-ttu-id="71a6f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="71a6f-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71a6f-109">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="71a6f-109">behaviorConfiguration</span></span>|<span data-ttu-id="71a6f-110">Una cadena que contiene el nombre de comportamiento que se va a usar para instanciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="71a6f-110">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="71a6f-111">El nombre de comportamiento debe estar en el ámbito en el punto definido del servicio.</span><span class="sxs-lookup"><span data-stu-id="71a6f-111">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="71a6f-112">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="71a6f-112">The default value is an empty string.</span></span>|  
|<span data-ttu-id="71a6f-113">name</span><span class="sxs-lookup"><span data-stu-id="71a6f-113">name</span></span>|<span data-ttu-id="71a6f-114">Atributo String necesario que especifica el tipo del servicio del que se van a crear instancias.</span><span class="sxs-lookup"><span data-stu-id="71a6f-114">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="71a6f-115">Este valor debe equivaler a un tipo válido.</span><span class="sxs-lookup"><span data-stu-id="71a6f-115">This setting must equate to a valid type.</span></span> <span data-ttu-id="71a6f-116">El formato debería ser `Namespace.Class.`.</span><span class="sxs-lookup"><span data-stu-id="71a6f-116">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71a6f-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="71a6f-117">Child Elements</span></span>  
  
|<span data-ttu-id="71a6f-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="71a6f-118">Element</span></span>|<span data-ttu-id="71a6f-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="71a6f-119">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="71a6f-120">Una colección de elementos `endpoint` que exponen este servicio.</span><span class="sxs-lookup"><span data-stu-id="71a6f-120">A collection of `endpoint` elements that expose this service.</span></span>|  
|[\<host>](host.md)|<span data-ttu-id="71a6f-121">Especifica el host de esta instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="71a6f-121">Specifies the host of this service instance.</span></span> <span data-ttu-id="71a6f-122">Este elemento es del tipo <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="71a6f-122">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="71a6f-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="71a6f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="71a6f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="71a6f-124">Element</span></span>|<span data-ttu-id="71a6f-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="71a6f-125">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services.md)|<span data-ttu-id="71a6f-126">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="71a6f-126">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71a6f-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71a6f-127">Remarks</span></span>  
 <span data-ttu-id="71a6f-128">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="71a6f-128">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="71a6f-129">Un ensamblado puede contener cualquier número de servicios.</span><span class="sxs-lookup"><span data-stu-id="71a6f-129">An assembly can contain any number of services.</span></span> <span data-ttu-id="71a6f-130">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="71a6f-130">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="71a6f-131">Esta sección y su contenido definen el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="71a6f-131">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="71a6f-132">El elemento `behaviorConfiguration` también es opcional.</span><span class="sxs-lookup"><span data-stu-id="71a6f-132">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="71a6f-133">Identifica el comportamiento que el servicio utiliza.</span><span class="sxs-lookup"><span data-stu-id="71a6f-133">It identifies the behavior the service uses.</span></span> <span data-ttu-id="71a6f-134">El comportamiento especificado en este atributo debe vincular a un comportamiento en ámbito en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="71a6f-134">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="71a6f-135">Cada servicio expone uno o más extremos, que tienen su propia dirección y enlace.</span><span class="sxs-lookup"><span data-stu-id="71a6f-135">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="71a6f-136">Todos los enlaces usados dentro del archivo de configuración se deben definir en el ámbito del archivo.</span><span class="sxs-lookup"><span data-stu-id="71a6f-136">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="71a6f-137">Los enlaces se vinculan a los puntos de conexión a través de la combinación de los atributos `name` y `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="71a6f-137">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="71a6f-138">El atributo `name` describe la sección en la que está definido el enlace.</span><span class="sxs-lookup"><span data-stu-id="71a6f-138">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="71a6f-139">El atributo `bindingConfiguration` define qué configuración se usa dentro de la sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="71a6f-139">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="71a6f-140">Una sección de enlace puede definir varias configuraciones.</span><span class="sxs-lookup"><span data-stu-id="71a6f-140">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71a6f-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="71a6f-141">Example</span></span>  
 <span data-ttu-id="71a6f-142">Éste es un ejemplo de una configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="71a6f-142">This is an example of a service configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="71a6f-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71a6f-143">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="71a6f-144">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="71a6f-144">Configuring Services</span></span>](../../../wcf/configuring-services.md)

---
description: 'Más información acerca de: <bindings>'
title: <bindings>
ms.date: 01/22/2018
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
ms.openlocfilehash: 2cf5b42b8478e34a528cd36435023cac62bf0c1e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639385"
---
# \<bindings>

<span data-ttu-id="a2ea1-102">Puede usar el `bindings` elemento para configurar una colección de enlaces estándar y personalizados para Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a2ea1-102">You can use the `bindings` element to configure a collection of standard and custom bindings for Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="a2ea1-103">Cada entrada es un elemento `binding` que se puede identificar por su `name` único.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-103">Each entry is a `binding` element that can be identified by its unique `name`.</span></span> <span data-ttu-id="a2ea1-104">Los servicios usan los enlaces vinculándose a ellos mediante `name`.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-104">Services use bindings by linking them using the `name`.</span></span> <span data-ttu-id="a2ea1-105">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-105">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="a2ea1-106">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="a2ea1-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>

## <a name="system-provided-bindings"></a><span data-ttu-id="a2ea1-107">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="a2ea1-107">System-provided bindings</span></span>

<span data-ttu-id="a2ea1-108">Los enlaces proporcionados por el sistema ocultan la complejidad de la pila de mensajería de WCF.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-108">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="a2ea1-109">Las aplicaciones que utilizan los enlaces proporcionados por el sistema no requieren el control completo sobre la pila.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-109">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="a2ea1-110">Los atributos expuestos en cada enlace proporcionado por el sistema son los más apropiados para el escenario de uso de las direcciones de enlace.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-110">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>

<span data-ttu-id="a2ea1-111">La sección de configuración para cada enlace proporcionado por el sistema puede definir varias configuraciones utilizadas para configurar el enlace.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-111">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="a2ea1-112">Un nombre único identifica a cada configuración.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-112">Each configuration is identified by a unique name.</span></span>

<span data-ttu-id="a2ea1-113">No es posible agregar elementos o atributos a un enlace proporcionado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-113">It isn't possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="a2ea1-114">Para ello, debe implementar un enlace personalizado como se describe en la sección de [enlaces personalizados](#custom-bindings) .</span><span class="sxs-lookup"><span data-stu-id="a2ea1-114">To do so, you should implement a custom binding as described in the [Custom bindings](#custom-bindings) section.</span></span> <span data-ttu-id="a2ea1-115">Es posible definir un enlace personalizado que imite perfectamente un enlace proporcionado por el sistema y agrega algunos valores en los que la aplicación de usuario desea tener el control.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-115">It's possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  

<span data-ttu-id="a2ea1-116">Para obtener una lista de los enlaces proporcionados por el sistema, consulte [enlaces proporcionados por el sistema](../../../wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="a2ea1-116">For a list of system-provided bindings, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>

## <a name="custom-bindings"></a><span data-ttu-id="a2ea1-117">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="a2ea1-117">Custom bindings</span></span>

<span data-ttu-id="a2ea1-118">Los enlaces personalizados proporcionan el control completo sobre la pila de mensajería WCF.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-118">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="a2ea1-119">Un enlace individual define la pila de mensajes mediante la especificación de los elementos de configuración para los elementos de la pila en el orden que aparecen en la pila.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-119">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="a2ea1-120">Cada elemento define y configura un elemento de la pila.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-120">Each element defines and configures one element of the stack.</span></span> <span data-ttu-id="a2ea1-121">Debe haber un único elemento de `transport` en cada enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-121">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="a2ea1-122">Sin este elemento, la pila de la mensajería está incompleta.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-122">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="a2ea1-123">El orden de aparición de los elementos en la pila es importante, porque es el orden en el que las operaciones se aplican al mensaje.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-123">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="a2ea1-124">El orden requerido de elementos de pila es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="a2ea1-124">The required order of stack elements is the following:</span></span>  

1. <span data-ttu-id="a2ea1-125">Transacciones (opcional)</span><span class="sxs-lookup"><span data-stu-id="a2ea1-125">Transactions (optional)</span></span>  

2. <span data-ttu-id="a2ea1-126">Mensajería de confianza (opcional)</span><span class="sxs-lookup"><span data-stu-id="a2ea1-126">Reliable messaging (optional)</span></span>  

3. <span data-ttu-id="a2ea1-127">Seguridad (opcional)</span><span class="sxs-lookup"><span data-stu-id="a2ea1-127">Security (optional)</span></span>  

4. <span data-ttu-id="a2ea1-128">Codificador</span><span class="sxs-lookup"><span data-stu-id="a2ea1-128">Encoder</span></span>  

5. <span data-ttu-id="a2ea1-129">Transporte</span><span class="sxs-lookup"><span data-stu-id="a2ea1-129">Transport</span></span>  

 <span data-ttu-id="a2ea1-130">Los enlaces personalizados se identifican mediante su atributo `name`.</span><span class="sxs-lookup"><span data-stu-id="a2ea1-130">Custom bindings are identified by their `name` attribute.</span></span> <span data-ttu-id="a2ea1-131">Para obtener más información sobre los enlaces personalizados, vea [enlaces personalizados](../../../wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="a2ea1-131">For more information on custom bindings, see [Custom Bindings](../../../wcf/extending/custom-bindings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a2ea1-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2ea1-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.BindingsSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>
- [<span data-ttu-id="a2ea1-133">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a2ea1-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a2ea1-134">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="a2ea1-134">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)

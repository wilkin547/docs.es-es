---
title: '&lt;enlaces&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ed672ee918ad969feb8be6d20c9206e6b5d12278
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltbindingsgt"></a><span data-ttu-id="b77b0-102">&lt;enlaces&gt;</span><span class="sxs-lookup"><span data-stu-id="b77b0-102">&lt;bindings&gt;</span></span>
<span data-ttu-id="b77b0-103">Esta sección contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="b77b0-103">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="b77b0-104">Cada entrada es un elemento `binding` que se puede identificar por su `name` único.</span><span class="sxs-lookup"><span data-stu-id="b77b0-104">Each entry is a `binding` element that can be identified by its unique `name`.</span></span> <span data-ttu-id="b77b0-105">Los servicios usan los enlaces vinculándose a ellos mediante `name`.</span><span class="sxs-lookup"><span data-stu-id="b77b0-105">Services use bindings by linking them using the `name`.</span></span> <span data-ttu-id="b77b0-106">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="b77b0-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="b77b0-107">Para obtener más información acerca de la configuración predeterminada y enlaces anónimos y los comportamientos, consulte [configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="b77b0-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="system-provided-binding"></a><span data-ttu-id="b77b0-108">Enlace proporcionado por el sistema</span><span class="sxs-lookup"><span data-stu-id="b77b0-108">System-Provided Binding</span></span>  
 <span data-ttu-id="b77b0-109">Los enlaces proporcionados por el sistema ocultan la complejidad de la pila de mensajería de WCF.</span><span class="sxs-lookup"><span data-stu-id="b77b0-109">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="b77b0-110">Las aplicaciones que utilizan los enlaces proporcionados por el sistema no requieren el control completo sobre la pila.</span><span class="sxs-lookup"><span data-stu-id="b77b0-110">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="b77b0-111">Los atributos expuestos en cada enlace proporcionado por el sistema son los más apropiados para el escenario de uso de las direcciones de enlace.</span><span class="sxs-lookup"><span data-stu-id="b77b0-111">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>  
  
 <span data-ttu-id="b77b0-112">La sección de configuración para cada enlace proporcionado por el sistema puede definir varias configuraciones utilizadas para configurar el enlace.</span><span class="sxs-lookup"><span data-stu-id="b77b0-112">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="b77b0-113">Un nombre único identifica a cada configuración.</span><span class="sxs-lookup"><span data-stu-id="b77b0-113">Each configuration is identified by a unique name.</span></span>  
  
 <span data-ttu-id="b77b0-114">No es posible agregar elementos o atributos a un enlace proporcionado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="b77b0-114">It is not possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="b77b0-115">Para esto, debería implementar un enlace personalizado como se describe en la sección "Enlace personalizado" de este tema.</span><span class="sxs-lookup"><span data-stu-id="b77b0-115">To do so, you should implement a custom binding as described in the "Custom Binding" section of this topic.</span></span> <span data-ttu-id="b77b0-116">Es posible definir un enlace personalizado que imite perfectamente un enlace proporcionado por el sistema y agregue unos valores sobre los que la aplicación de usuario desee tener el control.</span><span class="sxs-lookup"><span data-stu-id="b77b0-116">It is possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  
  
 <span data-ttu-id="b77b0-117">Para obtener una lista de enlaces proporcionados por el sistema, consulte [enlaces proporcionados](../../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="b77b0-117">For a list of system-provided bindings, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
## <a name="custom-binding"></a><span data-ttu-id="b77b0-118">Enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="b77b0-118">Custom Binding</span></span>  
 <span data-ttu-id="b77b0-119">Los enlaces personalizados proporcionan el control completo sobre la pila de mensajería WCF.</span><span class="sxs-lookup"><span data-stu-id="b77b0-119">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="b77b0-120">Un enlace individual define la pila de mensajes mediante la especificación de los elementos de configuración para los elementos de la pila en el orden que aparecen en la pila.</span><span class="sxs-lookup"><span data-stu-id="b77b0-120">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="b77b0-121">Cada elemento define y configura un elemento de la pila.</span><span class="sxs-lookup"><span data-stu-id="b77b0-121">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="b77b0-122">Debe haber un único elemento de `transport` en cada enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="b77b0-122">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="b77b0-123">Sin este elemento, la pila de la mensajería está incompleta.</span><span class="sxs-lookup"><span data-stu-id="b77b0-123">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="b77b0-124">El orden de aparición de los elementos en la pila es importante, porque es el orden en el que las operaciones se aplican al mensaje.</span><span class="sxs-lookup"><span data-stu-id="b77b0-124">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="b77b0-125">El orden requerido de elementos de pila es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b77b0-125">The required order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="b77b0-126">Transacciones (opcional)</span><span class="sxs-lookup"><span data-stu-id="b77b0-126">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="b77b0-127">Mensajería de confianza (opcional)</span><span class="sxs-lookup"><span data-stu-id="b77b0-127">Reliable Messaging (optional)</span></span>  
  
3.  <span data-ttu-id="b77b0-128">Seguridad (opcional)</span><span class="sxs-lookup"><span data-stu-id="b77b0-128">Security (optional)</span></span>  
  
4.  <span data-ttu-id="b77b0-129">Codificador</span><span class="sxs-lookup"><span data-stu-id="b77b0-129">Encoder</span></span>  
  
5.  <span data-ttu-id="b77b0-130">Transporte</span><span class="sxs-lookup"><span data-stu-id="b77b0-130">Transport</span></span>  
  
 <span data-ttu-id="b77b0-131">Los enlaces personalizados se identifican mediante su atributo `name`.</span><span class="sxs-lookup"><span data-stu-id="b77b0-131">Custom bindings are identified by their `name` attribute.</span></span> <span data-ttu-id="b77b0-132">Para obtener más información sobre los enlaces personalizados, consulte [enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="b77b0-132">For more information on custom bindings, see [Custom Bindings](../../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b77b0-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b77b0-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BindingsSection>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 [<span data-ttu-id="b77b0-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="b77b0-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b77b0-135">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="b77b0-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="b77b0-136">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b77b0-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="b77b0-137">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="b77b0-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

---
title: <binding>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 666183d6-4d1f-45c7-ac64-bdf93ee8f36f
ms.openlocfilehash: fb51eb1962603439b89a203eb668dfb543049170
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271478"
---
# <a name="binding"></a><span data-ttu-id="fea50-101">\<binding></span><span class="sxs-lookup"><span data-stu-id="fea50-101">\<binding></span></span>
<span data-ttu-id="fea50-102">Puede utilizar el elemento de `binding` para configurar los tipos diferentes de enlaces predefinidos proporcionados por Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fea50-102">You can use the `binding` element to configure different types of predefined bindings provided by Windows Communication Foundation (WCF).</span></span>  
  
## <a name="system-provided-binding"></a><span data-ttu-id="fea50-103">Enlace proporcionado por el sistema</span><span class="sxs-lookup"><span data-stu-id="fea50-103">System-Provided Binding</span></span>  
 <span data-ttu-id="fea50-104">Los enlaces proporcionados por el sistema ocultan la complejidad de la pila de mensajería de WCF.</span><span class="sxs-lookup"><span data-stu-id="fea50-104">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="fea50-105">Las aplicaciones que utilizan los enlaces proporcionados por el sistema no requieren el control completo sobre la pila.</span><span class="sxs-lookup"><span data-stu-id="fea50-105">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="fea50-106">Los atributos expuestos en cada enlace proporcionado por el sistema son los más apropiados para el escenario de uso de las direcciones de enlace.</span><span class="sxs-lookup"><span data-stu-id="fea50-106">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>  
  
 <span data-ttu-id="fea50-107">La sección de configuración para cada enlace proporcionado por el sistema puede definir varias configuraciones utilizadas para configurar el enlace.</span><span class="sxs-lookup"><span data-stu-id="fea50-107">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="fea50-108">Un nombre único identifica a cada configuración.</span><span class="sxs-lookup"><span data-stu-id="fea50-108">Each configuration is identified by a unique name.</span></span>  
  
 <span data-ttu-id="fea50-109">No es posible agregar elementos o atributos a un enlace proporcionado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="fea50-109">It is not possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="fea50-110">Para esto, debería implementar un enlace personalizado como se describe en la sección "Enlace personalizado" de este tema.</span><span class="sxs-lookup"><span data-stu-id="fea50-110">To do so, you should implement a custom binding as described in the "Custom Binding" section of this topic.</span></span> <span data-ttu-id="fea50-111">Es posible definir un enlace personalizado que imite perfectamente un enlace proporcionado por el sistema y agregue unos valores sobre los que la aplicación de usuario desee tener el control.</span><span class="sxs-lookup"><span data-stu-id="fea50-111">It is possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  
  
## <a name="custom-binding"></a><span data-ttu-id="fea50-112">Enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="fea50-112">Custom Binding</span></span>  
 <span data-ttu-id="fea50-113">Los enlaces personalizados proporcionan el control completo sobre la pila de mensajería WCF.</span><span class="sxs-lookup"><span data-stu-id="fea50-113">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="fea50-114">Un enlace individual define la pila de mensajes mediante la especificación de los elementos de configuración para los elementos de la pila en el orden que aparecen en la pila.</span><span class="sxs-lookup"><span data-stu-id="fea50-114">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="fea50-115">Cada elemento define y configura un elemento de la pila.</span><span class="sxs-lookup"><span data-stu-id="fea50-115">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="fea50-116">Debe haber un único elemento de `transport` en cada enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="fea50-116">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="fea50-117">Sin este elemento, la pila de la mensajería está incompleta.</span><span class="sxs-lookup"><span data-stu-id="fea50-117">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="fea50-118">El orden de aparición de los elementos en la pila es importante, porque es el orden en el que las operaciones se aplican al mensaje.</span><span class="sxs-lookup"><span data-stu-id="fea50-118">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="fea50-119">El orden recomendado de elementos de pila es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="fea50-119">The recommended order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="fea50-120">Transacciones (opcional)</span><span class="sxs-lookup"><span data-stu-id="fea50-120">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="fea50-121">Mensajería de confianza (opcional)</span><span class="sxs-lookup"><span data-stu-id="fea50-121">Reliable Messaging (optional)</span></span>  
  
3.  <span data-ttu-id="fea50-122">Seguridad (opcional)</span><span class="sxs-lookup"><span data-stu-id="fea50-122">Security (optional)</span></span>  
  
4.  <span data-ttu-id="fea50-123">Codificador</span><span class="sxs-lookup"><span data-stu-id="fea50-123">Encoder</span></span>  
  
5.  <span data-ttu-id="fea50-124">Transporte</span><span class="sxs-lookup"><span data-stu-id="fea50-124">Transport</span></span>  
  
 <span data-ttu-id="fea50-125">Los enlaces personalizados se identifican mediante su atributo `name`.</span><span class="sxs-lookup"><span data-stu-id="fea50-125">Custom bindings are identified by their `name` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fea50-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="fea50-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- [<span data-ttu-id="fea50-127">Enlaces</span><span class="sxs-lookup"><span data-stu-id="fea50-127">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="fea50-128">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="fea50-128">Custom Bindings</span></span>](../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="fea50-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="fea50-129">\<customBinding></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

---
title: "Personalización de un enlace proporcionado por el sistema"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f8b97862-e8bb-470d-8b96-07733c21fe26
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9b048b5c57d174ac921793ee8677622b88a0595
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-a-system-provided-binding"></a><span data-ttu-id="64949-102">Personalización de un enlace proporcionado por el sistema</span><span class="sxs-lookup"><span data-stu-id="64949-102">How to: Customize a System-Provided Binding</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="64949-103"> incluye varios enlaces proporcionados por el sistema que le permiten configurar algunas de las propiedades de los elementos de enlace subyacentes, pero no todas las propiedades.</span><span class="sxs-lookup"><span data-stu-id="64949-103"> includes several system-provided bindings that allow you to configure some of the properties of the underlying binding elements, but not all of the properties.</span></span> <span data-ttu-id="64949-104">En este tema se muestra cómo establecer las propiedades en los elementos de enlace para crear un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="64949-104">This topic demonstrates how to set properties on the binding elements to create a custom binding.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="64949-105">cómo crear directamente y configurar elementos de enlace sin usar los enlaces proporcionados por el sistema, consulte [enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="64949-105"> how to directly create and configure binding elements without using the system-provided bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="64949-106">crear y ampliar los enlaces personalizados, consulte [extender enlaces](../../../../docs/framework/wcf/extending/extending-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="64949-106"> creating and extending custom bindings, see [Extending Bindings](../../../../docs/framework/wcf/extending/extending-bindings.md).</span></span>  
  
 <span data-ttu-id="64949-107">En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] todos los enlaces se componen de *elementos de enlace*.</span><span class="sxs-lookup"><span data-stu-id="64949-107">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] all bindings are made up of *binding elements*.</span></span> <span data-ttu-id="64949-108">Cada elemento de enlace deriva de la clase <xref:System.ServiceModel.Channels.BindingElement>.</span><span class="sxs-lookup"><span data-stu-id="64949-108">Each binding element derives from the <xref:System.ServiceModel.Channels.BindingElement> class.</span></span> <span data-ttu-id="64949-109">Los enlaces proporcionados por el sistema, como <xref:System.ServiceModel.BasicHttpBinding> crean y configuran sus propios elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="64949-109">System-provided bindings such as <xref:System.ServiceModel.BasicHttpBinding> create and configure their own binding elements.</span></span> <span data-ttu-id="64949-110">En este tema se muestra cómo obtener acceso y cambiar las propiedades de estos elementos de enlace, que no se exponen directamente en el enlace; en concreto, la clase <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="64949-110">This topic shows you how to access and change the properties of these binding elements, which are not directly exposed on the binding; specifically, the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="64949-111">Los elementos de enlace individuales se incluyen en una colección representada por la clase <xref:System.ServiceModel.Channels.BindingElementCollection> y se agregan en este orden: flujo de la transacción, sesión confiable, seguridad, dúplex compuesto, unidireccional, seguridad de secuencia, codificación de mensajes y transporte.</span><span class="sxs-lookup"><span data-stu-id="64949-111">The individual binding elements are contained in a collection represented by the <xref:System.ServiceModel.Channels.BindingElementCollection> class and are added in this order: Transaction Flow, Reliable Session, Security, Composite Duplex, One-way, Stream Security, Message Encoding, and Transport.</span></span> <span data-ttu-id="64949-112">Tenga en cuenta que no todos los elementos de enlace enumerados se necesitan en cada enlace.</span><span class="sxs-lookup"><span data-stu-id="64949-112">Note that not all the binding elements listed are required in every binding.</span></span> <span data-ttu-id="64949-113">Los elementos de enlace definidos por el usuario pueden aparecer también en esta colección de elementos de enlace y deben aparecer en el orden descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="64949-113">User-defined binding elements can also appear in this binding element collection and must appear in the same order as previously described.</span></span> <span data-ttu-id="64949-114">Por ejemplo, un transporte definido por el usuario debe ser el último elemento de la colección de elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="64949-114">For example, a user-defined transport must be the last element of the binding element collection.</span></span>  
  
 <span data-ttu-id="64949-115">La clase <xref:System.ServiceModel.BasicHttpBinding> contiene tres elementos de enlace:</span><span class="sxs-lookup"><span data-stu-id="64949-115">The <xref:System.ServiceModel.BasicHttpBinding> class contains three binding elements:</span></span>  
  
1.  <span data-ttu-id="64949-116">Un elemento de enlace de seguridad opcional, la clase <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> utilizada con el transporte HTTP (seguridad de mensajes) o la clase <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, que se utiliza cuando el nivel de transporte proporciona seguridad, en cuyo caso se utiliza el transporte de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="64949-116">An optional security binding element, either the <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> class used with the HTTP transport (message level security) or the <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> class, which is used when the transport layer provides security, in which case the HTTPS transport is used.</span></span>  
  
2.  <span data-ttu-id="64949-117">Un elemento de enlace del codificador de mensajes requerido, <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> o <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="64949-117">A required message encoder binding element, either <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> or <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.</span></span>  
  
3.  <span data-ttu-id="64949-118">Un elemento de enlace del transporte requerido, o <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, o <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="64949-118">A required transport binding element, either <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, or <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.</span></span>  
  
 <span data-ttu-id="64949-119">En este ejemplo creamos una instancia del enlace, generamos un *enlace personalizado* de él, examinamos los elementos de enlace en el enlace personalizado y cuando encontramos el elemento de enlace de HTTP, establecemos su `KeepAliveEnabled` propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="64949-119">In this example we create an instance of the binding, generate a *custom binding* from it, examine the binding elements in the custom binding, and when we find the HTTP binding element, we set its `KeepAliveEnabled` property to `false`.</span></span> <span data-ttu-id="64949-120">La propiedad `KeepAliveEnabled` no se expone directamente en `BasicHttpBinding`, por lo que debemos crear un enlace personalizado para explorar hacia abajo hasta el elemento de enlace y establecer esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="64949-120">The `KeepAliveEnabled` property is not exposed directly on the `BasicHttpBinding`, so we must create a custom binding to navigate down to the binding element and set this property.</span></span>  
  
### <a name="to-modify-a-system-provided-binding"></a><span data-ttu-id="64949-121">Modificación de un enlace proporcionado por el sistema</span><span class="sxs-lookup"><span data-stu-id="64949-121">To modify a system-provided binding</span></span>  
  
1.  <span data-ttu-id="64949-122">Cree una instancia de la clase <xref:System.ServiceModel.BasicHttpBinding> y establezca su modo de seguridad en el nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="64949-122">Create an instance of the <xref:System.ServiceModel.BasicHttpBinding> class and set its security mode to message-level.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#1)]
     [!code-vb[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#1)]  
  
2.  <span data-ttu-id="64949-123">Cree un enlace personalizado a partir del enlace y cree una clase <xref:System.ServiceModel.Channels.BindingElementCollection> a partir de una de las propiedades del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="64949-123">Create a custom binding from the binding and create a <xref:System.ServiceModel.Channels.BindingElementCollection> class from one of the custom binding's properties.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#2)]
     [!code-vb[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#2)]  
  
3.  <span data-ttu-id="64949-124">Recorra a través de la clase <xref:System.ServiceModel.Channels.BindingElementCollection> y cuando encuentre la clase <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, establezca su propiedad <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="64949-124">Loop through the <xref:System.ServiceModel.Channels.BindingElementCollection> class, and when you find the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> class, set its <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> property to `false`.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#3)]
     [!code-vb[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="64949-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="64949-125">See Also</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="64949-126">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="64949-126">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)

---
title: "Cómo: Invalidar metadatos en una propiedad de dependencia"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [WPF], overriding for dependency properties
- dependency properties [WPF], overriding metadata for
- overriding metadata for dependency properties [WPF]
ms.assetid: f90f026e-60d8-428a-933d-edf0dba4441f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8e7cb01c81b5fb24830cbe0cc39befbadaf4405e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-override-metadata-for-a-dependency-property"></a><span data-ttu-id="e3186-102">Cómo: Invalidar metadatos en una propiedad de dependencia</span><span class="sxs-lookup"><span data-stu-id="e3186-102">How to: Override Metadata for a Dependency Property</span></span>
<span data-ttu-id="e3186-103">Este ejemplo muestra cómo invalidar los metadatos de propiedad de dependencia predeterminados que proceden de una clase heredada, mediante una llamada a la <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> método y proporcionar metadatos específicos del tipo.</span><span class="sxs-lookup"><span data-stu-id="e3186-103">This example shows how to override default dependency property metadata that comes from an inherited class, by calling the <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> method and providing type-specific metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3186-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e3186-104">Example</span></span>  
 <span data-ttu-id="e3186-105">Mediante la definición de su <xref:System.Windows.PropertyMetadata>, una clase puede definir los comportamientos de la propiedad de dependencia, como sus valor predeterminado propiedad y valor sistema las devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="e3186-105">By defining its <xref:System.Windows.PropertyMetadata>, a class can define the dependency property's behaviors, such as its default value and property system callbacks.</span></span> <span data-ttu-id="e3186-106">Muchas clases de propiedad de dependencia ya tienen metadatos predeterminados establecidos como parte de su proceso de registro.</span><span class="sxs-lookup"><span data-stu-id="e3186-106">Many dependency property classes already have default metadata established as part of their registration process.</span></span> <span data-ttu-id="e3186-107">Esto incluye las propiedades de dependencia que forman parte de la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3186-107">This includes the dependency properties that are part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)].</span></span> <span data-ttu-id="e3186-108">Una clase que hereda la propiedad de dependencia a través de la herencia de clase puede invalidar los metadatos originales para que las características de la propiedad que se pueden modificar mediante metadatos coincidan con los requisitos específicos de la subclase.</span><span class="sxs-lookup"><span data-stu-id="e3186-108">A class that inherits the dependency property through its class inheritance can override the original metadata so that the characteristics of the property that can be altered through metadata will match any subclass-specific requirements.</span></span>  
  
 <span data-ttu-id="e3186-109">La invalidación de metadatos en una propiedad de dependencia debe realizarse antes de que el sistema de propiedades ponga la propiedad en uso (esto equivale al momento en el que se crean instancias de objetos que registran la propiedad).</span><span class="sxs-lookup"><span data-stu-id="e3186-109">Overriding metadata on a dependency property must be done prior to that property being placed in use by the property system (this equates to the time that specific instances of objects that register the property are instantiated).</span></span> <span data-ttu-id="e3186-110">Las llamadas a <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> debe realizarse dentro de los constructores estáticos del tipo que se proporciona como el `forType` parámetro de <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="e3186-110">Calls to <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> must be performed within the static constructors of the type that provides itself as the `forType` parameter of <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>.</span></span> <span data-ttu-id="e3186-111">Si intenta cambiar los metadatos cuando ya existan instancias del tipo de propietario, no producirá excepciones, pero generará comportamientos incoherentes en el sistema de propiedades.</span><span class="sxs-lookup"><span data-stu-id="e3186-111">If you attempt to change metadata once instances of the owner type exist, this will not raise exceptions, but will result in inconsistent behaviors in the property system.</span></span> <span data-ttu-id="e3186-112">Además, los metadatos solo se pueden invalidar una vez por tipo.</span><span class="sxs-lookup"><span data-stu-id="e3186-112">Also, metadata can only be overridden once per type.</span></span> <span data-ttu-id="e3186-113">Los intentos posteriores de invalidar metadatos en el mismo tipo generarán una excepción.</span><span class="sxs-lookup"><span data-stu-id="e3186-113">Subsequent attempts to override metadata on the same type will raise an exception.</span></span>  
  
 <span data-ttu-id="e3186-114">En el ejemplo siguiente, la clase personalizada `MyAdvancedStateControl` invalida los metadatos proporcionados para `StateProperty` por `MyAdvancedStateControl` con nuevos metadatos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="e3186-114">In the following example, the custom class `MyAdvancedStateControl` overrides the metadata provided for `StateProperty` by `MyAdvancedStateControl` with new property metadata.</span></span> <span data-ttu-id="e3186-115">Por ejemplo, el valor predeterminado de `StateProperty` es ahora `true` cuando se consulta la propiedad en una instancia `MyAdvancedStateControl` de construcción reciente.</span><span class="sxs-lookup"><span data-stu-id="e3186-115">For instance, the default value of the `StateProperty` is now `true` when the property is queried on a newly constructed `MyAdvancedStateControl` instance.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#myadvancedstatecontrol)]
[!code-vb[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#myadvancedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="e3186-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3186-116">See Also</span></span>  
 <xref:System.Windows.DependencyProperty>  
 [<span data-ttu-id="e3186-117">Información general sobre las propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="e3186-117">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="e3186-118">Propiedades de dependencia personalizadas</span><span class="sxs-lookup"><span data-stu-id="e3186-118">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [<span data-ttu-id="e3186-119">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="e3186-119">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)

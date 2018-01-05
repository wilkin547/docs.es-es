---
title: "Cómo: Definir y hacer referencia a un recurso"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 173be3048f7bf082db2eef2ea21eb1e0319f9a43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-and-reference-a-resource"></a><span data-ttu-id="88435-102">Cómo: Definir y hacer referencia a un recurso</span><span class="sxs-lookup"><span data-stu-id="88435-102">How to: Define and Reference a Resource</span></span>
<span data-ttu-id="88435-103">Este ejemplo muestra cómo definir un recurso y hacer referencia a él mediante el uso de un atributo en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88435-103">This example shows how to define a resource and reference it by using an attribute in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="88435-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88435-104">Example</span></span>  
 <span data-ttu-id="88435-105">El siguiente ejemplo define dos tipos de recursos: un <xref:System.Windows.Media.SolidColorBrush> recursos y varios <xref:System.Windows.Style> recursos.</span><span class="sxs-lookup"><span data-stu-id="88435-105">The following example defines two types of resources: a <xref:System.Windows.Media.SolidColorBrush> resource, and several <xref:System.Windows.Style> resources.</span></span> <span data-ttu-id="88435-106">El <xref:System.Windows.Media.SolidColorBrush> recursos `MyBrush` se usa para proporcionar el valor de varias propiedades que toman cada uno un <xref:System.Windows.Media.Brush> tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="88435-106">The <xref:System.Windows.Media.SolidColorBrush> resource `MyBrush` is used to provide the value of several properties that each take a <xref:System.Windows.Media.Brush> type value.</span></span> <span data-ttu-id="88435-107">El <xref:System.Windows.Style> recursos `PageBackground`, `TitleText` y `Label` cada centrarse en un tipo de control determinado.</span><span class="sxs-lookup"><span data-stu-id="88435-107">The <xref:System.Windows.Style> resources `PageBackground`, `TitleText` and `Label` each target a particular control type.</span></span> <span data-ttu-id="88435-108">Los estilos de establecen una serie de propiedades diferentes en los controles de destino, cuando ese recurso de estilo al que hace referencia la clave de recurso y se usa para establecer el <xref:System.Windows.FrameworkElement.Style%2A> propiedad de varios elementos de control concretos definidos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88435-108">The styles set a variety of different properties on the targeted controls, when that style resource is referenced by resource key and is used to set the <xref:System.Windows.FrameworkElement.Style%2A> property of several specific control elements defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="88435-109">Tenga en cuenta que una de las propiedades de los establecedores de la `Label` estilo también hace referencia el `MyBrush` recurso definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="88435-109">Note that one of the properties within the setters of the `Label` style also references the `MyBrush` resource defined earlier.</span></span> <span data-ttu-id="88435-110">Ésta es una técnica común, pero es importante recordar que se analizan y se escribió en un diccionario de recursos en el orden en que se les asigna recursos.</span><span class="sxs-lookup"><span data-stu-id="88435-110">This is a common technique, but it is important to remember that resources are parsed and entered into a resource dictionary in the order that they are given.</span></span> <span data-ttu-id="88435-111">También se solicitan los recursos por el orden en que se encuentra en el diccionario si usas el [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) para hacer referencia a ellos desde dentro de otro recurso.</span><span class="sxs-lookup"><span data-stu-id="88435-111">Resources are also requested by the order found within the dictionary if you use the [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) to reference them from within another resource.</span></span> <span data-ttu-id="88435-112">Asegúrese de que cualquier recurso que se hace referencia se definió anteriormente dentro de la colección de recursos que donde, a continuación, se solicita ese recurso.</span><span class="sxs-lookup"><span data-stu-id="88435-112">Make sure that any resource that you reference is defined earlier within the resources collection than where that resource is then requested.</span></span> <span data-ttu-id="88435-113">Si es necesario, se puede solucionar el orden estricto de creación de referencias a recursos utilizando una [extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) hagan referencia al recurso en tiempo de ejecución en su lugar, pero debe tener en cuenta que este DynamicResource técnica tiene consecuencias en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="88435-113">If necessary, you can work around the strict creation order of resource refererences by using a [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) to reference the resource at runtime instead, but you should be aware that this DynamicResource technique has performance consequences.</span></span> <span data-ttu-id="88435-114">Para obtener más información, consulte [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="88435-114">For details, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 [!code-xaml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## <a name="see-also"></a><span data-ttu-id="88435-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="88435-115">See Also</span></span>  
 [<span data-ttu-id="88435-116">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="88435-116">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="88435-117">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="88435-117">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)

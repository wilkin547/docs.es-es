---
title: "Cómo: Usar recursos de aplicaciones"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bac1fa1576e684a4b10f00310c08e4e7101a5df0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-application-resources"></a><span data-ttu-id="020c3-102">Cómo: Usar recursos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="020c3-102">How to: Use Application Resources</span></span>
<span data-ttu-id="020c3-103">En este ejemplo se muestra cómo usar recursos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="020c3-103">This example shows how to use application resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="020c3-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="020c3-104">Example</span></span>  
 <span data-ttu-id="020c3-105">En el siguiente ejemplo se muestra un archivo de definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="020c3-105">The following example shows an application definition file.</span></span> <span data-ttu-id="020c3-106">El archivo de definición de aplicación define una sección de recursos (un valor para el <xref:System.Windows.Application.Resources%2A> propiedad).</span><span class="sxs-lookup"><span data-stu-id="020c3-106">The application definition file defines a resource section (a value for the <xref:System.Windows.Application.Resources%2A> property).</span></span> <span data-ttu-id="020c3-107">Todas las demás páginas que forman parte de la aplicación pueden obtener acceso a los recursos definidos en el nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="020c3-107">Resources defined at the application level can be accessed by all other pages that are part of the application.</span></span> <span data-ttu-id="020c3-108">En este caso, el recurso es un estilo declarado.</span><span class="sxs-lookup"><span data-stu-id="020c3-108">In this case, the resource is a declared style.</span></span> <span data-ttu-id="020c3-109">Dado que un estilo completo que incluye una plantilla de control puede ser bastante largo, este ejemplo omite la plantilla de control que se define en el <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> establecedor de propiedad del estilo.</span><span class="sxs-lookup"><span data-stu-id="020c3-109">Because a complete style that includes a control template can be lengthy, this example omits the control template that is defined within the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property setter of the style.</span></span>  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 <span data-ttu-id="020c3-110">El ejemplo siguiente muestra un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página que hace referencia al recurso de nivel de aplicación definido en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="020c3-110">The following example shows a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page that references the application-level resource that the previous example defined.</span></span> <span data-ttu-id="020c3-111">El recurso se hace referencia mediante un [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) que especifica la clave de recurso único para el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="020c3-111">The resource is referenced by using a     [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) that specifies the unique resource key for the requested resource.</span></span> <span data-ttu-id="020c3-112">No se encontró ningún recurso con la clave "GelButton" en la página actual, por lo que el ámbito de búsqueda de recursos para el recurso solicitado continúa más allá de la página actual y en los recursos de nivel de aplicación definidos.</span><span class="sxs-lookup"><span data-stu-id="020c3-112">No resource with key of "GelButton" is found in the current page, so the resource lookup scope for the requested resource continues beyond the current page and into the defined application-level resources.</span></span>  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a><span data-ttu-id="020c3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="020c3-113">See Also</span></span>  
 [<span data-ttu-id="020c3-114">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="020c3-114">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="020c3-115">Información general sobre la administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="020c3-115">Application Management Overview</span></span>](../../../../docs/framework/wpf/app-development/application-management-overview.md)  
 [<span data-ttu-id="020c3-116">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="020c3-116">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)

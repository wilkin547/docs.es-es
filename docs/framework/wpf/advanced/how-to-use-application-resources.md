---
title: 'Cómo: Usar recursos de aplicaciones'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: e4114466fa8016f8e31100d7a37038b0abfdccca
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460271"
---
# <a name="how-to-use-application-resources"></a><span data-ttu-id="e135f-102">Cómo: Usar recursos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e135f-102">How to: Use Application Resources</span></span>
<span data-ttu-id="e135f-103">En este ejemplo se muestra cómo usar recursos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e135f-103">This example shows how to use application resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e135f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e135f-104">Example</span></span>  
 <span data-ttu-id="e135f-105">En el siguiente ejemplo se muestra un archivo de definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e135f-105">The following example shows an application definition file.</span></span> <span data-ttu-id="e135f-106">El archivo de definición de aplicación define una sección de recursos (un valor para la propiedad <xref:System.Windows.Application.Resources%2A>).</span><span class="sxs-lookup"><span data-stu-id="e135f-106">The application definition file defines a resource section (a value for the <xref:System.Windows.Application.Resources%2A> property).</span></span> <span data-ttu-id="e135f-107">Todas las demás páginas que forman parte de la aplicación pueden obtener acceso a los recursos definidos en el nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e135f-107">Resources defined at the application level can be accessed by all other pages that are part of the application.</span></span> <span data-ttu-id="e135f-108">En este caso, el recurso es un estilo declarado.</span><span class="sxs-lookup"><span data-stu-id="e135f-108">In this case, the resource is a declared style.</span></span> <span data-ttu-id="e135f-109">Dado que un estilo completo que incluye una plantilla de control puede ser largo, en este ejemplo se omite la plantilla de control que se define dentro del <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> establecedor de la propiedad del estilo.</span><span class="sxs-lookup"><span data-stu-id="e135f-109">Because a complete style that includes a control template can be lengthy, this example omits the control template that is defined within the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property setter of the style.</span></span>  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 <span data-ttu-id="e135f-110">En el ejemplo siguiente se muestra una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página que hace referencia al recurso de nivel de aplicación que se ha definido en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="e135f-110">The following example shows a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page that references the application-level resource that the previous example defined.</span></span> <span data-ttu-id="e135f-111">Se hace referencia al recurso mediante una [extensión de marcado StaticResource](staticresource-markup-extension.md) que especifica la clave de recurso única para el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="e135f-111">The resource is referenced by using a     [StaticResource Markup Extension](staticresource-markup-extension.md) that specifies the unique resource key for the requested resource.</span></span> <span data-ttu-id="e135f-112">No se encontró ningún recurso con la clave "GelButton" en la página actual, por lo que el ámbito de búsqueda de recursos para el recurso solicitado continúa más allá de la página actual y en los recursos de nivel de aplicación definidos.</span><span class="sxs-lookup"><span data-stu-id="e135f-112">No resource with key of "GelButton" is found in the current page, so the resource lookup scope for the requested resource continues beyond the current page and into the defined application-level resources.</span></span>  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a><span data-ttu-id="e135f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e135f-113">See also</span></span>

- [<span data-ttu-id="e135f-114">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="e135f-114">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="e135f-115">Información general sobre la administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e135f-115">Application Management Overview</span></span>](../app-development/application-management-overview.md)
- [<span data-ttu-id="e135f-116">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="e135f-116">How-to Topics</span></span>](resources-how-to-topics.md)

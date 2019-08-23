---
title: Procedimiento Agregar adornos a elementos secundarios de un panel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 739ccaa0273e66c4650c35217a1156d64336dbbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923524"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a><span data-ttu-id="c0f9a-102">Procedimiento Agregar adornos a elementos secundarios de un panel</span><span class="sxs-lookup"><span data-stu-id="c0f9a-102">How to: Adorn the Children of a Panel</span></span>
<span data-ttu-id="c0f9a-103">En este ejemplo se muestra cómo enlazar un adorno mediante programación a los elementos secundarios de <xref:System.Windows.Controls.Panel>un especificado.</span><span class="sxs-lookup"><span data-stu-id="c0f9a-103">This example shows how to programmatically bind an adorner to the children of a specified <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0f9a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0f9a-104">Example</span></span>  
 <span data-ttu-id="c0f9a-105">Para enlazar un adorno a los elementos secundarios de <xref:System.Windows.Controls.Panel>, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c0f9a-105">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1. <span data-ttu-id="c0f9a-106">Declare un <xref:System.Windows.Documents.AdornerLayer> nuevo objeto y `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> llame al método para buscar una capa de adornos para el elemento cuyos elementos secundarios se van a adornar.</span><span class="sxs-lookup"><span data-stu-id="c0f9a-106">Declare a new <xref:System.Windows.Documents.AdornerLayer> object and call the `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> method to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2. <span data-ttu-id="c0f9a-107">Enumere los elementos secundarios del elemento primario y llame <xref:System.Windows.Documents.AdornerLayer.Add%2A> al método para enlazar un adorno a cada elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="c0f9a-107">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="c0f9a-108">En el ejemplo siguiente se enlaza un adorno simplecircleadorner (mostrado anteriormente) a los elementos secundarios <xref:System.Windows.Controls.StackPanel> de un *myStackPanel*con nombre.</span><span class="sxs-lookup"><span data-stu-id="c0f9a-108">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
> <span data-ttu-id="c0f9a-109">En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.</span><span class="sxs-lookup"><span data-stu-id="c0f9a-109">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f9a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0f9a-110">See also</span></span>

- [<span data-ttu-id="c0f9a-111">Información general sobre adornos</span><span class="sxs-lookup"><span data-stu-id="c0f9a-111">Adorners Overview</span></span>](adorners-overview.md)

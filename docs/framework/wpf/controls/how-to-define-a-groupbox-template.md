---
title: Filtrar Definir una plantilla de un control GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: 6b4ad4a588aab93f5445cda962af890bfcd41c14
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377669"
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="42a93-102">Filtrar Definir una plantilla de un control GroupBox</span><span class="sxs-lookup"><span data-stu-id="42a93-102">How to: Define a GroupBox Template</span></span>
<span data-ttu-id="42a93-103">En este ejemplo se muestra cómo crear una plantilla para un <xref:System.Windows.Controls.GroupBox> control.</span><span class="sxs-lookup"><span data-stu-id="42a93-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42a93-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="42a93-104">Example</span></span>  
 <span data-ttu-id="42a93-105">En el ejemplo siguiente se define un <xref:System.Windows.Controls.GroupBox> plantilla de control mediante el uso de un <xref:System.Windows.Controls.Grid> control para el diseño.</span><span class="sxs-lookup"><span data-stu-id="42a93-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="42a93-106">La plantilla utiliza un <xref:System.Windows.Controls.BorderGapMaskConverter> para definir el borde de la <xref:System.Windows.Controls.GroupBox> para que el borde no oculte el <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> contenido.</span><span class="sxs-lookup"><span data-stu-id="42a93-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="42a93-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="42a93-107">See also</span></span>
- <xref:System.Windows.Controls.GroupBox>
- <span data-ttu-id="42a93-108">[Cómo: Crear un control GroupBox](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="42a93-108">[How to: Create a GroupBox](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))</span></span>

---
title: Filtrar Cambiar la propiedad FlowDirection de contenido mediante programación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: ec159ed0efce8b5514788331e8715a55e7a8a638
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359333"
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a><span data-ttu-id="5f79e-102">Filtrar Cambiar la propiedad FlowDirection de contenido mediante programación</span><span class="sxs-lookup"><span data-stu-id="5f79e-102">How to: Change the FlowDirection of Content Programmatically</span></span>
<span data-ttu-id="5f79e-103">En este ejemplo se muestra cómo cambiar mediante programación el <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad de un <xref:System.Windows.Controls.FlowDocumentReader>.</span><span class="sxs-lookup"><span data-stu-id="5f79e-103">This example shows how to programmatically change the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property of a <xref:System.Windows.Controls.FlowDocumentReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f79e-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5f79e-104">Example</span></span>  
 <span data-ttu-id="5f79e-105">Dos <xref:System.Windows.Controls.Button> se crean elementos, cada uno que representa uno de los valores posibles de <xref:System.Windows.FlowDirection>.</span><span class="sxs-lookup"><span data-stu-id="5f79e-105">Two <xref:System.Windows.Controls.Button> elements are created, each representing one of the possible values of <xref:System.Windows.FlowDirection>.</span></span> <span data-ttu-id="5f79e-106">Cuando se hace clic en un botón, el valor de propiedad asociado se aplica al contenido de un <xref:System.Windows.Controls.FlowDocumentReader> denominado `tf1`.</span><span class="sxs-lookup"><span data-stu-id="5f79e-106">When a button is clicked, the associated property value is applied to the contents of a <xref:System.Windows.Controls.FlowDocumentReader> named `tf1`.</span></span>  <span data-ttu-id="5f79e-107">El valor de propiedad también se escribe en un <xref:System.Windows.Controls.TextBlock> denominado `txt1`.</span><span class="sxs-lookup"><span data-stu-id="5f79e-107">The property value is also written to a <xref:System.Windows.Controls.TextBlock> named `txt1`.</span></span>  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a><span data-ttu-id="5f79e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5f79e-108">Example</span></span>  
 <span data-ttu-id="5f79e-109">Los eventos asociados a los clics de botón definidos anteriormente se controlan en un C# archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="5f79e-109">The events associated with the button clicks defined above are handled in a C# code-behind file.</span></span>  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]

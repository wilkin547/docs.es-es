---
title: Filtrar Controlar el evento ScrollChanged
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], raising ScrollChanged events
- ScrollChanged events [WPF]
ms.assetid: 42c695d8-ee28-49d4-80fd-fc71e9be7f29
ms.openlocfilehash: 54f20a4b8c6e6fcc190257fcf5de4374415d68b4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206153"
---
# <a name="how-to-handle-the-scrollchanged-event"></a><span data-ttu-id="46206-102">Filtrar Controlar el evento ScrollChanged</span><span class="sxs-lookup"><span data-stu-id="46206-102">How to: Handle the ScrollChanged Event</span></span>
## <a name="example"></a><span data-ttu-id="46206-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46206-103">Example</span></span>  
 <span data-ttu-id="46206-104">En este ejemplo se muestra cómo controlar el <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> eventos de un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="46206-104">This example shows how to handle the <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> event of a <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
 <span data-ttu-id="46206-105">Un <xref:System.Windows.Documents.FlowDocument> elemento con <xref:System.Windows.Documents.Paragraph> partes se definen en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46206-105">A <xref:System.Windows.Documents.FlowDocument> element with <xref:System.Windows.Documents.Paragraph> parts is defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="46206-106">Cuando el <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> evento tiene lugar debido a la interacción del usuario, se invoca un controlador y el texto se escribe en un <xref:System.Windows.Controls.TextBlock> que indica que se ha producido el evento.</span><span class="sxs-lookup"><span data-stu-id="46206-106">When the <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> event occurs due to user interaction, a handler is invoked, and text is written to a <xref:System.Windows.Controls.TextBlock> indicating that the event has occurred.</span></span>  
  
 [!code-xaml[scrollchangedeventargsLayout#1](~/samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#1)]  
[!code-xaml[scrollchangedeventargsLayout#2](~/samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[scrollchangedeventargsLayout#3](~/samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml.cs#3)]
 [!code-vb[scrollchangedeventargsLayout#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/scrollchangedeventargsLayout/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="46206-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="46206-107">See also</span></span>

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>
- <xref:System.Windows.Controls.ScrollChangedEventHandler>
- <xref:System.Windows.Controls.ScrollChangedEventArgs>

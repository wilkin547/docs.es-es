---
title: "Cómo: Dibujar texto en el fondo de un control"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f0c98422e337678e68a8e4b72979635e8c867b4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-text-to-a-control39s-background"></a><span data-ttu-id="687d1-102">Cómo: Dibujar texto en el fondo de un control</span><span class="sxs-lookup"><span data-stu-id="687d1-102">How to: Draw Text to a Control&#39;s Background</span></span>
<span data-ttu-id="687d1-103">Puede dibujar texto directamente en el fondo de un control mediante la conversión de una cadena de texto a un <xref:System.Windows.Media.FormattedText> objeto y, a continuación, el objeto de dibujo para el control <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="687d1-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="687d1-104">También puede utilizar esta técnica para dibujar en el fondo de objetos derivados de <xref:System.Windows.Controls.Panel>, como <xref:System.Windows.Controls.Canvas> y <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="687d1-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="687d1-105">![Controles mostrando texto como fondo](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="687d1-105">![Controls displaying text as background](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")</span></span>  
<span data-ttu-id="687d1-106">Ejemplo de controles con fondos de texto personalizados</span><span class="sxs-lookup"><span data-stu-id="687d1-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="687d1-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="687d1-107">Example</span></span>  
 <span data-ttu-id="687d1-108">Para dibujar en el fondo de un control, cree un nuevo <xref:System.Windows.Media.DrawingBrush> objeto y dibujar el texto convertido en el objeto <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="687d1-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="687d1-109">A continuación, asigne el nuevo <xref:System.Windows.Media.DrawingBrush> a propiedad de fondo del control.</span><span class="sxs-lookup"><span data-stu-id="687d1-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="687d1-110">En el ejemplo de código siguiente se muestra cómo crear un <xref:System.Windows.Media.FormattedText> objeto y dibujar en el fondo de un <xref:System.Windows.Controls.Label> y <xref:System.Windows.Controls.Button> objeto.</span><span class="sxs-lookup"><span data-stu-id="687d1-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="687d1-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="687d1-111">See Also</span></span>  
 <xref:System.Windows.Media.FormattedText>  
 [<span data-ttu-id="687d1-112">Dibujar texto con formato</span><span class="sxs-lookup"><span data-stu-id="687d1-112">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)

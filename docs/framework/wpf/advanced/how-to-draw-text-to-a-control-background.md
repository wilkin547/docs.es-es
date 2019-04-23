---
title: Procedimiento Dibujar texto en el fondo de un control
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 76449c88f9a720741c8ed61255e04a40e6a8613f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128458"
---
# <a name="how-to-draw-text-to-a-controls-background"></a><span data-ttu-id="fba07-102">Procedimiento Dibujar texto en el fondo de un control</span><span class="sxs-lookup"><span data-stu-id="fba07-102">How to: Draw Text to a Control's Background</span></span>
<span data-ttu-id="fba07-103">Puede dibujar texto directamente en el fondo de un control mediante la conversión de una cadena de texto a un <xref:System.Windows.Media.FormattedText> objeto y, a continuación, dibuje el objeto para el control <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="fba07-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="fba07-104">También puede usar esta técnica para dibujar en el fondo de objetos derivados de <xref:System.Windows.Controls.Panel>, tales como <xref:System.Windows.Controls.Canvas> y <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="fba07-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="fba07-105">![Controles mostrando texto como fondo](./media/drawtext2background01.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="fba07-105">![Controls displaying text as background](./media/drawtext2background01.png "DrawText2Background01")</span></span>  
<span data-ttu-id="fba07-106">Ejemplo de controles con fondos de texto personalizados</span><span class="sxs-lookup"><span data-stu-id="fba07-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="fba07-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fba07-107">Example</span></span>  
 <span data-ttu-id="fba07-108">Para dibujar el fondo de un control, cree un nuevo <xref:System.Windows.Media.DrawingBrush> de objetos y dibujar el texto convertido en el objeto <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="fba07-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="fba07-109">A continuación, asigne el nuevo <xref:System.Windows.Media.DrawingBrush> a la propiedad del control en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="fba07-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="fba07-110">En el ejemplo de código siguiente se muestra cómo crear un <xref:System.Windows.Media.FormattedText> de objetos y dibujar en el fondo de un <xref:System.Windows.Controls.Label> y <xref:System.Windows.Controls.Button> objeto.</span><span class="sxs-lookup"><span data-stu-id="fba07-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="fba07-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="fba07-111">See also</span></span>

- <xref:System.Windows.Media.FormattedText>
- [<span data-ttu-id="fba07-112">Dibujar texto con formato</span><span class="sxs-lookup"><span data-stu-id="fba07-112">Drawing Formatted Text</span></span>](drawing-formatted-text.md)

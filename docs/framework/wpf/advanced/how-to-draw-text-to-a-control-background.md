---
title: 'Cómo: Dibujar texto en el fondo de un control'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 14300f763b67c6ac67ee408de2009c328d499c13
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424367"
---
# <a name="how-to-draw-text-to-a-controls-background"></a><span data-ttu-id="28ca8-102">Cómo: Dibujar texto en el fondo de un control</span><span class="sxs-lookup"><span data-stu-id="28ca8-102">How to: Draw Text to a Control's Background</span></span>
<span data-ttu-id="28ca8-103">Puede dibujar texto directamente en el fondo de un control convirtiendo una cadena de texto en un objeto <xref:System.Windows.Media.FormattedText> y, a continuación, dibujando el objeto en el <xref:System.Windows.Media.DrawingContext>del control.</span><span class="sxs-lookup"><span data-stu-id="28ca8-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="28ca8-104">También puede utilizar esta técnica para dibujar en el fondo de objetos derivados de <xref:System.Windows.Controls.Panel>, como <xref:System.Windows.Controls.Canvas> y <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="28ca8-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="28ca8-105">![Captura de pantalla de controles que muestran texto como fondo.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="28ca8-105">![Screenshot of controls displaying text as background.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")</span></span>  
<span data-ttu-id="28ca8-106">Ejemplo de controles con fondos de texto personalizados</span><span class="sxs-lookup"><span data-stu-id="28ca8-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="28ca8-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="28ca8-107">Example</span></span>  
 <span data-ttu-id="28ca8-108">Para dibujar en el fondo de un control, cree un nuevo objeto <xref:System.Windows.Media.DrawingBrush> y dibuje el texto convertido en el <xref:System.Windows.Media.DrawingContext>del objeto.</span><span class="sxs-lookup"><span data-stu-id="28ca8-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="28ca8-109">A continuación, asigne el nuevo <xref:System.Windows.Media.DrawingBrush> a la propiedad Background del control.</span><span class="sxs-lookup"><span data-stu-id="28ca8-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="28ca8-110">En el ejemplo de código siguiente se muestra cómo crear un objeto <xref:System.Windows.Media.FormattedText> y dibujar en el fondo de un objeto <xref:System.Windows.Controls.Label> y <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="28ca8-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="28ca8-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="28ca8-111">See also</span></span>

- <xref:System.Windows.Media.FormattedText>
- [<span data-ttu-id="28ca8-112">Dibujar texto con formato</span><span class="sxs-lookup"><span data-stu-id="28ca8-112">Drawing Formatted Text</span></span>](drawing-formatted-text.md)

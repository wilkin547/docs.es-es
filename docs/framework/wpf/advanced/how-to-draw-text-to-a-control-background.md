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
# <a name="how-to-draw-text-to-a-controls-background"></a>Cómo: Dibujar texto en el fondo de un control
Puede dibujar texto directamente en el fondo de un control convirtiendo una cadena de texto en un objeto <xref:System.Windows.Media.FormattedText> y, a continuación, dibujando el objeto en el <xref:System.Windows.Media.DrawingContext>del control. También puede utilizar esta técnica para dibujar en el fondo de objetos derivados de <xref:System.Windows.Controls.Panel>, como <xref:System.Windows.Controls.Canvas> y <xref:System.Windows.Controls.StackPanel>.  
  
 ![Captura de pantalla de controles que muestran texto como fondo.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")  
Ejemplo de controles con fondos de texto personalizados  
  
## <a name="example"></a>Ejemplo  
 Para dibujar en el fondo de un control, cree un nuevo objeto <xref:System.Windows.Media.DrawingBrush> y dibuje el texto convertido en el <xref:System.Windows.Media.DrawingContext>del objeto. A continuación, asigne el nuevo <xref:System.Windows.Media.DrawingBrush> a la propiedad Background del control.  
  
 En el ejemplo de código siguiente se muestra cómo crear un objeto <xref:System.Windows.Media.FormattedText> y dibujar en el fondo de un objeto <xref:System.Windows.Controls.Label> y <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.FormattedText>
- [Dibujar texto con formato](drawing-formatted-text.md)

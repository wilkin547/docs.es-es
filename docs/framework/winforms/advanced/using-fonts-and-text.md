---
title: Utilizar fuentes y texto
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: 73a4af5fe7367e777fcb83af8c84c09be91e5b1e
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505109"
---
# <a name="using-fonts-and-text"></a>Utilizar fuentes y texto
Hay varias clases proporcionadas por GDI + y GDI para dibujar texto en Windows Forms. GDI + <xref:System.Drawing.Graphics> clase tiene varias <xref:System.Drawing.Graphics.DrawString%2A> métodos que le permiten especificar diversas características de texto, como la ubicación, el rectángulo delimitador, fuentes y formato. Además, puede dibujar y medir el texto con GDI mediante estático <xref:System.Windows.Forms.TextRenderer.DrawText%2A> y <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> métodos que ofrece el `TextRenderer` clase. Los métodos GDI también permiten especificar la ubicación, la fuente y el formato. Puede elegir GDI o GDI + para la representación de texto; Sin embargo, GDI generalmente ofrece un mejor rendimiento y la medición de texto más precisa. Otras clases que contribuyen a la representación de texto incluyen `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, y `TextFormatFlags`.  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Construir fuentes y familias de fuentes](how-to-construct-font-families-and-fonts.md)  
 Muestra cómo crear `Font` y `FontFamily` objetos.  
  
 [Cómo: Dibujar texto en una ubicación especificada](how-to-draw-text-at-a-specified-location.md)  
 Describe cómo dibujar texto en una ubicación determinada con GDI + y GDI.  
  
 [Cómo: Dibujar texto ajustado en un rectángulo](how-to-draw-wrapped-text-in-a-rectangle.md)  
 Explica cómo dibujar texto en un rectángulo con GDI + y GDI.  
  
 [Cómo: Dibujar texto con GDI](how-to-draw-text-with-gdi.md)  
 Muestra cómo usar GDI para dibujar texto.  
  
 [Cómo: Alinear texto dibujado](how-to-align-drawn-text.md)  
 Muestra cómo dar formato al texto GDI + y GDI.  
  
 [Cómo: Crear texto Vertical](how-to-create-vertical-text.md)  
 Describe cómo se va a dibujar el texto alineado verticalmente con GDI +.  
  
 [Cómo: Establecer posiciones de tabulación en texto dibujado](how-to-set-tab-stops-in-drawn-text.md)  
 Muestra cómo dibujar texto con tabulaciones con GDI +.  
  
 [Cómo: Enumerar las fuentes instaladas](how-to-enumerate-installed-fonts.md)  
 Explica cómo enumerar los nombres de las fuentes instaladas.  
  
 [Cómo: Crear una colección de fuentes privada](how-to-create-a-private-font-collection.md)  
 Describe cómo crear un <xref:System.Drawing.Text.PrivateFontCollection> objeto.  
  
 [Cómo: Obtener medidas de fuentes](how-to-obtain-font-metrics.md)  
 Se muestra cómo obtener medidas de fuentes, como el ascenso de celda y el descenso.  
  
 [Cómo: Usa suavizado de contorno con texto](how-to-use-antialiasing-with-text.md)  
 Explica cómo utilizar el suavizado de contorno al dibujar el texto.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Drawing.Font>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Drawing.FontFamily>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.TextRenderer>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 Describe esta clase y contiene vínculos a todos sus miembros.

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
ms.openlocfilehash: c9fe16752223203806c7d3828f632aad0cab0c28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769426"
---
# <a name="using-fonts-and-text"></a>Utilizar fuentes y texto
Hay varias clases proporcionadas por [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] para dibujar texto en Windows Forms. El [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> clase tiene varias <xref:System.Drawing.Graphics.DrawString%2A> métodos que le permiten especificar diversas características de texto, como la ubicación, el rectángulo delimitador, fuentes y formato. Además, puede dibujar y medir el texto con [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] mediante estático <xref:System.Windows.Forms.TextRenderer.DrawText%2A> y <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> métodos que ofrece el `TextRenderer` clase. El [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] métodos también permiten especificar la ubicación, la fuente y el formato. Puede elegir [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] o [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] para representar texto; sin embargo, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] generalmente ofrece un mejor rendimiento y la medición de texto más precisa. Otras clases que contribuyen a la representación de texto incluyen `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, y `TextFormatFlags`.  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Construir fuentes y familias de fuentes](how-to-construct-font-families-and-fonts.md)  
 Muestra cómo crear `Font` y `FontFamily` objetos.  
  
 [Cómo: Dibujar texto en una ubicación especificada](how-to-draw-text-at-a-specified-location.md)  
 Describe cómo dibujar texto en un determinado almacén utiliza [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Cómo: Dibujar texto ajustado en un rectángulo](how-to-draw-wrapped-text-in-a-rectangle.md)  
 Explica cómo dibujar texto en un rectángulo mediante [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Cómo: Dibujar texto con GDI](how-to-draw-text-with-gdi.md)  
 Muestra cómo usar [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] para dibujar texto.  
  
 [Cómo: Alinear texto dibujado](how-to-align-drawn-text.md)  
 Muestra cómo dar formato a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] texto.  
  
 [Cómo: Crear texto Vertical](how-to-create-vertical-text.md)  
 Describe cómo dibujar texto alineado verticalmente con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Cómo: Establecer posiciones de tabulación en texto dibujado](how-to-set-tab-stops-in-drawn-text.md)  
 Muestra cómo dibujar texto con tabulaciones con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
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

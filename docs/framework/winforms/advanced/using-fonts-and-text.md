---
title: Utilizar fuentes y texto
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f4febeed6aff2c18b5040020c2c1d3ee6cf59a52
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-fonts-and-text"></a>Utilizar fuentes y texto
Hay varias clases proporcionadas por [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] para dibujar texto en formularios Windows Forms. El [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> clase tiene varias <xref:System.Drawing.Graphics.DrawString%2A> métodos que le permiten especificar varias características de texto, como ubicación, rectángulo delimitador, fuente y formato. Además, puede dibujar y medir el texto con [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] mediante el método estático <xref:System.Windows.Forms.TextRenderer.DrawText%2A> y <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> métodos que ofrece el `TextRenderer` clase. El [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] métodos también le permiten especificar la ubicación, la fuente y el formato. Puede elegir cualquiera [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] o [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] para representar texto; sin embargo, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] generalmente ofrece un mejor rendimiento y una medición de texto más precisa. Otras clases que contribuyen a la representación de texto incluyen `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, y `TextFormatFlags`.  
  
## <a name="in-this-section"></a>En esta sección  
 [Construir fuentes y familias de fuentes](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 Muestra cómo crear `Font` y `FontFamily` objetos.  
  
 [Dibujar texto en una ubicación especificada](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)  
 Describe cómo dibujar texto en un determinado almacén utiliza [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Dibujar texto ajustado en un rectángulo](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)  
 Explica cómo dibujar texto en un rectángulo mediante [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Dibujar texto con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 Muestra cómo utilizar [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] para dibujar el texto.  
  
 [Alinear texto dibujado](../../../../docs/framework/winforms/advanced/how-to-align-drawn-text.md)  
 Muestra cómo dar formato a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] texto.  
  
 [Crear texto vertical](../../../../docs/framework/winforms/advanced/how-to-create-vertical-text.md)  
 Describe cómo dibujar texto alineado verticalmente con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Establecer posiciones de tabulación en texto dibujado](../../../../docs/framework/winforms/advanced/how-to-set-tab-stops-in-drawn-text.md)  
 Muestra cómo dibujar texto con posiciones de tabulación con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Enumerar las fuentes instaladas](../../../../docs/framework/winforms/advanced/how-to-enumerate-installed-fonts.md)  
 Explica cómo enumerar los nombres de las fuentes instaladas.  
  
 [Crear una colección de fuentes privada](../../../../docs/framework/winforms/advanced/how-to-create-a-private-font-collection.md)  
 Describe cómo crear un <xref:System.Drawing.Text.PrivateFontCollection> objeto.  
  
 [Obtener medidas de fuentes](../../../../docs/framework/winforms/advanced/how-to-obtain-font-metrics.md)  
 Muestra cómo obtener medidas de fuentes como ascenso de celda y descenso.  
  
 [Utilizar la función de suavizado de contorno con texto](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)  
 Explica cómo utilizar el suavizado de contorno al dibujar texto.  
  
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

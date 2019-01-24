---
title: Introducción a los controles de líneas y formas (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- Line control [Visual Basic], overview
- Shape control [Visual Basic], overview
- lines, drawing
- shapes, drawing
ms.assetid: 5c4e8b1a-0733-4020-af6c-f582f4026728
ms.openlocfilehash: 3623c2363f39150fd4bb202ba61ebd51df383ca8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699927"
---
# <a name="introduction-to-the-line-and-shape-controls-visual-studio"></a>Introducción a los controles de líneas y formas (Visual Studio)
Los controles de Visual Basic Power Packs Line y Shape son un conjunto de tres controles gráficos que le permiten dibujar líneas y formas en formularios y contenedores. El <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control se usa para dibujar líneas horizontales, verticales y diagonales. El <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> control se usa para dibujar los círculos y elipses y el <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> control se usa para dibujar rectángulos y cuadrados.  
  
## <a name="line-and-shape-controls"></a>Controles de líneas y formas  
 Controles Line y Shape encapsulan muchos de los métodos gráficos contenidos en el <xref:System.Drawing> espacio de nombres. Esto le permite dibujar líneas y formas en un solo paso sin tener que crear objetos gráficos, lápices y pinceles. Pueden realizarse complejas técnicas gráficas como rellenos degradados con sólo configurar algunas propiedades.  
  
 Aunque también es posible dibujar líneas y formas utilizando métodos gráficos, hay varias ventajas al uso de los controles Line y Shape:  
  
-   Métodos de gráficos se pueden llamar en tiempo de ejecución. Controles Line y Shape se pueden agregar a un formulario en tiempo de diseño. Esto le permite ver su aspecto y colocarlos exactamente; También se pueden agregar en tiempo de ejecución.  
  
-   Controles Line y Shape son seleccionables en tiempo de ejecución, que proporciona eventos como <xref:Microsoft.VisualBasic.PowerPacks.Shape.Click> y <xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A>. Las salidas de los métodos gráficos no se pueden seleccionables y no proporcionan eventos.  
  
-   Proporcionan controles Line y Shape <xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A> y <xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A> métodos que permiten controlar el orden z en tiempo de diseño y en tiempo de ejecución. El orden z de los métodos gráficos puede controlarse cambiando su orden de ejecución en tiempo de ejecución.  
  
-   Controles Line y Shape son controles sin ventana; no tienen ningún identificador de ventana y, por tanto, utiliza menos recursos del sistema.  
  
### <a name="object-model"></a>Modelo de objetos  
 Controles Line y Shape que se derivan de una base de <xref:Microsoft.VisualBasic.PowerPacks.Shape> clase que define sus propiedades compartidas, métodos y eventos.  
  
 La siguiente ilustración muestra la jerarquía de objetos Line y Shape.  
  
 ![Un diagrama de la jerarquía de objetos Line y Shape](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")  
Jerarquía de objetos Line y Shape  
  
 La clase derivada <xref:Microsoft.VisualBasic.PowerPacks.LineShape> clase contiene propiedades, métodos y eventos que son exclusivos de las líneas. La clase derivada <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> clase es la clase base para <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> y <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>; contiene las propiedades, métodos y eventos comunes a todas las formas. También puede derivar de <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> para crear sus propios `Shape` controles.  
  
 El <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> y <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> clases pueden utilizarse para dibujar círculos, elipses, rectángulos y rectángulos con esquinas redondeadas.  
  
 Cuando un control de línea o forma se agrega a un formulario o contenedor, un invisible <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> se crea el objeto. El <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> actúa como un lienzo para las formas dentro de cada control contenedor; cada <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> le corresponde una <xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection> que le permite recorrer en iteración los controles Line y Shape. Puede mover las formas de un contenedor a otro mediante cortar y pegar o arrastrar y colocar. Cuando se quita la última forma de un contenedor, el <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> también se quita.  
  
> [!NOTE]
>  No todos los controles de contenedor admiten los controles Line y Shape. No se puede hospedar un control de línea o forma en un <xref:System.Windows.Forms.TableLayoutPanel> o <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.PowerPacks>
- [Cómo: Dibujar líneas con el Control LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
- [Cómo: Dibujar formas con los controles OvalShape y RectangleShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
- [Cómo: Habilitar la tabulación entre las formas](../../../visual-basic/developing-apps/windows-forms/how-to-enable-tabbing-between-shapes-visual-studio.md)

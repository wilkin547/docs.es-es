---
title: Procedimiento Dibujar formas con los controles OvalShape y RectangleShape (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OvalShape control [Visual Basic]
- shapes, drawing
- RectangleShape control [Visual Basic]
ms.assetid: 0275b4c6-7a13-46c8-90f3-61db308c6b5d
ms.openlocfilehash: fe937236332591f6065e618c49ca5cf2c54b987c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701227"
---
# <a name="how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls-visual-studio"></a>Procedimiento Dibujar formas con los controles OvalShape y RectangleShape (Visual Studio)
Puede utilizar el control <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> para dibujar círculos u óvalos en un formulario o contenedor, tanto en tiempo de diseño como en tiempo de ejecución. Puede utilizar el control <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> para dibujar cuadrados, rectángulos o rectángulos con esquinas redondeadas en un formulario o contenedor. También puede utilizar este control para dibujar formas en tiempo de diseño y en tiempo de ejecución.  
  
 Puede personalizar la apariencia de una forma cambiando el ancho, el color y el estilo del borde. El fondo de una forma es transparente de manera predeterminada. Puede personalizar el fondo para mostrar un color sólido, una trama, un relleno de degradado (transición de un color a otro) o una imagen.  
  
### <a name="to-draw-a-simple-shape-at-design-time"></a>Dibujar una forma simple en tiempo de diseño  
  
1.  Arrastre el <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> o <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controlar desde la **Visual Basic PowerPacks** ficha (para instalar, consulte [controles Power Packs de Visual Basic](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)) en el **cuadro de herramientas** para un control de formulario o contenedor.  
  
2.  Arrastre los controladores de tamaño y movimiento para cambiar el tamaño y la posición de la forma.  
  
     También puede cambiar el tamaño y posición de la forma cambiando el `Size` y `Position` propiedades en el **propiedades** ventana.  
  
     Para crear un rectángulo con esquinas redondeadas, seleccione la `CornerRadius` propiedad en el **propiedades** ventana y establézcalo en un valor que es mayor que 0.  
  
3.  En el **propiedades** ventana, puede configurar otras propiedades para cambiar la apariencia de la forma.  
  
### <a name="to-draw-a-simple-shape-at-run-time"></a>Dibujar una forma simple en tiempo de ejecución  
  
1.  En el menú **Proyecto**, haga clic en **Agregar referencia**.  
  
2.  En el **Agregar referencia** cuadro de diálogo, seleccione **Microsoft.VisualBasic.PowerPacks.VS**y, a continuación, haga clic en **Aceptar**.  
  
3.  En el **Editor de código**, agregue un `Imports` o `using` instrucción en la parte superior del módulo:  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  Agregue el código siguiente en un procedimiento `Event`:  
  
     [!code-csharp[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.cs)]
     [!code-vb[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.vb)]  
  
## <a name="customizing-shapes"></a>Personalizar las formas  
 Cuando se utiliza la configuración predeterminada, los controles <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> y <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> se muestran con un borde negro sólido de un píxel de ancho y con un fondo transparente. Puede cambiar el ancho, el estilo y el color del borde estableciendo las propiedades. Las propiedades adicionales le permiten cambiar el fondo de una forma a un color sólido, una trama, un relleno de degradado o una imagen.  
  
 Antes de cambiar el fondo de una forma, debe saber cómo interactúan algunas de las propiedades.  
  
-   El valor de la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> no tiene ningún efecto a menos que la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> se haya establecido en <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.  
  
-   Si la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> se establece en <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>, <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> reemplaza a <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>.  
  
-   Si la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> se establece en un valor de trama como <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> o <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>, la trama se mostrará en el <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>. El fondo se mostrarán en el <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>, siempre y cuando la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> se haya establecido en <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.  
  
-   Para mostrar un relleno de degradado, la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> debe establecerse en <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid> y la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> debe establecerse en un valor distinto de <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None>.  
  
-   La configuración de la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> en una imagen reemplaza todas las demás opciones de fondo.  
  
#### <a name="to-draw-a-circle-that-has-a-custom-border"></a>Dibujar un círculo con un borde personalizado  
  
1.  Arrastre el `OvalShape` controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.  
  
2.  En el **propiedades** ventana, en el `Size` establecer la propiedad, `Height` y `Width` en los mismos valores.  
  
3.  Establezca la propiedad `BorderColor` en el color que desee.  
  
4.  Establezca la propiedad `BorderStyle` en cualquier valor distinto de `Solid`.  
  
5.  Establezca el `BorderWidth` en el tamaño que desee, en píxeles.  
  
#### <a name="to-draw-a-circle-that-has-a-solid-fill"></a>Dibujar un círculo con un relleno sólido  
  
1.  Arrastre el `OvalShape` controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.  
  
2.  En el **propiedades** ventana, en el `Size` establecer la propiedad, `Height` y `Width` en los mismos valores.  
  
3.  Establezca la propiedad `BackColor` en el color que desee.  
  
4.  Establezca la propiedad `BackStyle` en `Opaque`.  
  
#### <a name="to-draw-a-circle-that-has-a-patterned-fill"></a>Dibujar un círculo con un relleno de trama  
  
1.  Arrastre el `OvalShape` controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.  
  
2.  En el **propiedades** ventana, en el `Size` establecer la propiedad, `Height` y `Width` en los mismos valores.  
  
3.  Establezca la propiedad `BackColor` en el color que desee para el fondo.  
  
4.  Establezca la propiedad `BackStyle` en `Opaque`.  
  
5.  Establezca la propiedad `FillColor` en el color que desee para la trama.  
  
6.  Establezca la propiedad `FillStyle` en un valor distinto de `Transparent` o `Solid`.  
  
#### <a name="to-draw-a-circle-that-has-a-gradient-fill"></a>Dibujar un círculo con un relleno de degradado  
  
1.  Arrastre el `OvalShape` controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.  
  
2.  En el **propiedades** ventana, en el `Size` establecer la propiedad, `Height` y `Width` en los mismos valores.  
  
3.  Establezca la propiedad `FillColor` en el color que desee para el color inicial.  
  
4.  Establezca la propiedad `FillGradientColor` en el color que desee para el color final.  
  
5.  Establezca la propiedad `FillGradientStyle` en un valor distinto de `None`.  
  
#### <a name="to-draw-a-circle-that-is-filled-with-an-image"></a>Dibujar un círculo que se rellena con una imagen  
  
1.  Arrastre el `OvalShape` controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.  
  
2.  En el **propiedades** ventana, en el `Size` establecer la propiedad, `Height` y `Width` en los mismos valores.  
  
3.  Seleccione el `BackgroundImage` propiedad y haga clic en el **puntos suspensivos** botón (…).  
  
4.  En el **Seleccionar recurso** cuadro de diálogo, seleccione una imagen para mostrar. Si no aparece ningún recurso de imagen, haga clic en **importación** para ir a la ubicación de una imagen.  
  
5.  Haga clic en **Aceptar** para insertar la imagen.  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>
- <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>
- [Introducción a los controles de líneas y formas](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
- [Cómo: Dibujar líneas con el Control LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)

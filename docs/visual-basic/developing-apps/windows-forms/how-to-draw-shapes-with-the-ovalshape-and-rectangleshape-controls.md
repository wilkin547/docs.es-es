---
title: "C&#243;mo: Dibujar formas con los controles OvalShape y RectangleShape (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "OvalShape (control)"
  - "RectangleShape (control)"
  - "formas, dibujar"
ms.assetid: 0275b4c6-7a13-46c8-90f3-61db308c6b5d
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Dibujar formas con los controles OvalShape y RectangleShape (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Puede utilizar el control <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> para dibujar círculos u óvalos en un formulario o contenedor, tanto en tiempo de diseño como en tiempo de ejecución.  Puede utilizar el control <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> para dibujar cuadrados, rectángulos o rectángulos con esquinas redondeadas en un formulario o contenedor.  También puede utilizar este control para dibujar formas en tiempo de diseño y en tiempo de ejecución.  
  
 Puede personalizar la apariencia de una forma cambiando el ancho, el color y el estilo del borde.  El fondo de una forma es transparente de manera predeterminada. Puede personalizar el fondo para mostrar un color sólido, una trama, un relleno de degradado \(transición de un color a otro\) o una imagen.  
  
### Dibujar una forma simple en tiempo de diseño  
  
1.  Arrastre el control <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> o <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> de la ficha **Visual Basic PowerPacks** \(para instalar, consulte [Controles Visual Basic Power Packs](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)\) del **Cuadro de herramientas** a un formulario o un control contenedor.  
  
2.  Arrastre los controladores de tamaño y movimiento para cambiar el tamaño y la posición de la forma.  
  
     También puede cambiar el tamaño y la posición de la forma cambiando las propiedades `Size` y `Position` en la ventana **Propiedades**.  
  
     Para crear un rectángulo con esquinas redondeadas, seleccione la propiedad `CornerRadius` en la ventana **Propiedades** y establézcala en un valor mayor que 0.  
  
3.  En la ventana **Propiedades**, puede configurar otras propiedades para cambiar el aspecto de la forma.  
  
### Dibujar una forma simple en tiempo de ejecución  
  
1.  En el menú **Proyecto**, haga clic en **Agregar referencia**.  
  
2.  En el cuadro de diálogo **Agregar referencia**, seleccione **Microsoft.VisualBasic.PowerPacks.VS** y, a continuación, haga clic en **Aceptar**.  
  
3.  En el **Editor de código**, agregue una instrucción `Imports` o `using` en la parte superior del módulo:  
  
    ```vb#  
    Imports Microsoft.VisualBasic.PowerPacks  
    ```  
  
    ```c#  
    using Microsoft.VisualBasic.PowerPacks;  
    ```  
  
4.  Agregue el código siguiente en un procedimiento `Event`:  
  
     [!code-cs[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.cs)]
     [!code-vb[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.vb)]  
  
## Personalizar las formas  
 Cuando se utiliza la configuración predeterminada, los controles <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> y <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> se muestran con un borde negro sólido de un píxel de ancho y con un fondo transparente.  Puede cambiar el ancho, el estilo y el color del borde estableciendo las propiedades.  Las propiedades adicionales le permiten cambiar el fondo de una forma a un color sólido, una trama, un relleno de degradado o una imagen.  
  
 Antes de cambiar el fondo de una forma, debe saber cómo interactúan algunas de las propiedades.  
  
-   El valor de la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> no tiene ningún efecto a menos que la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> se haya establecido en <xref:Microsoft.VisualBasic.PowerPacks.BackStyle>.  
  
-   Si la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> se establece en <xref:Microsoft.VisualBasic.PowerPacks.FillStyle>, <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> reemplaza a <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>.  
  
-   Si la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> se establece en un valor de trama como <xref:Microsoft.VisualBasic.PowerPacks.FillStyle> o <xref:Microsoft.VisualBasic.PowerPacks.FillStyle>, la trama se mostrará en el <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>.  El fondo se mostrarán en el <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>, siempre y cuando la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> se haya establecido en <xref:Microsoft.VisualBasic.PowerPacks.BackStyle>.  
  
-   Para mostrar un relleno de degradado, la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> debe establecerse en <xref:Microsoft.VisualBasic.PowerPacks.FillStyle> y la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> debe establecerse en un valor distinto de <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle>.  
  
-   La configuración de la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> en una imagen reemplaza todas las demás opciones de fondo.  
  
#### Dibujar un círculo con un borde personalizado  
  
1.  Arrastre el control `OvalShape` de la ficha **Visual Basic PowerPacks** del **Cuadro de herramientas** a un formulario o un control contenedor.  
  
2.  En la ventana **Propiedades**, en la propiedad `Size`, establezca `Height` y `Width` en los mismos valores.  
  
3.  Establezca la propiedad `BorderColor` en el color que desee.  
  
4.  Establezca la propiedad `BorderStyle` en cualquier valor distinto de `Solid`.  
  
5.  Establezca el `BorderWidth` en el tamaño que desee, en píxeles.  
  
#### Dibujar un círculo con un relleno sólido  
  
1.  Arrastre el control `OvalShape` de la ficha **Visual Basic PowerPacks** del **Cuadro de herramientas** a un formulario o un control contenedor.  
  
2.  En la ventana **Propiedades**, en la propiedad `Size`, establezca `Height` y `Width` en los mismos valores.  
  
3.  Establezca la propiedad `BackColor` en el color que desee.  
  
4.  Establezca la propiedad `BackStyle` en `Opaque`.  
  
#### Dibujar un círculo con un relleno de trama  
  
1.  Arrastre el control `OvalShape` de la ficha **Visual Basic PowerPacks** del **Cuadro de herramientas** a un formulario o un control contenedor.  
  
2.  En la ventana **Propiedades**, en la propiedad `Size`, establezca `Height` y `Width` en los mismos valores.  
  
3.  Establezca la propiedad `BackColor` en el color que desee para el fondo.  
  
4.  Establezca la propiedad `BackStyle` en `Opaque`.  
  
5.  Establezca la propiedad `FillColor` en el color que desee para la trama.  
  
6.  Establezca la propiedad `FillStyle` en un valor distinto de `Transparent` o `Solid`.  
  
#### Dibujar un círculo con un relleno de degradado  
  
1.  Arrastre el control `OvalShape` de la ficha **Visual Basic PowerPacks** del **Cuadro de herramientas** a un formulario o un control contenedor.  
  
2.  En la ventana **Propiedades**, en la propiedad `Size`, establezca `Height` y `Width` en los mismos valores.  
  
3.  Establezca la propiedad `FillColor` en el color que desee para el color inicial.  
  
4.  Establezca la propiedad `FillGradientColor` en el color que desee para el color final.  
  
5.  Establezca la propiedad `FillGradientStyle` en un valor distinto de `None`.  
  
#### Dibujar un círculo que se rellena con una imagen  
  
1.  Arrastre el control `OvalShape` de la ficha **Visual Basic PowerPacks** del **Cuadro de herramientas** a un formulario o un control contenedor.  
  
2.  En la ventana **Propiedades**, en la propiedad `Size`, establezca `Height` y `Width` en los mismos valores.  
  
3.  Seleccione la propiedad `BackgroundImage` y haga clic en el botón de **puntos suspensivos** \(...\).  
  
4.  En el cuadro de diálogo **Seleccionar recurso**, seleccione una imagen para mostrar.  Si no aparece ningún recurso de imagen, haga clic en **Importar** para ir a la ubicación de una imagen.  
  
5.  Haga clic en **Aceptar** para insertar la imagen.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>   
 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>   
 [Introducción a los controles de líneas y formas](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)   
 [Cómo: Dibujar líneas con el control LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
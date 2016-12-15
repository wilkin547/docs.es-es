---
title: "Introducci&#243;n a los controles de l&#237;neas y formas (Visual Studio) | Microsoft Docs"
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
  - "Line (control), información general"
  - "líneas, dibujar"
  - "Shape (control), información general"
  - "formas, dibujar"
ms.assetid: 5c4e8b1a-0733-4020-af6c-f582f4026728
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Introducci&#243;n a los controles de l&#237;neas y formas (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los controles Visual Basic Power Packs Line y Shape constituyen un conjunto de tres controles gráficos que permiten dibujar líneas y formas en formularios y contenedores.  El control <xref:Microsoft.VisualBasic.PowerPacks.LineShape> se utiliza para dibujar líneas horizontales, verticales y diagonales.  El control <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> se utiliza para dibujar círculos y óvalos, y el control <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> se usa para dibujar rectángulos y cuadrados.  
  
## Controles de líneas y formas  
 Los controles de líneas y formas encapsulan muchos de los métodos gráficos contenidos en el espacio de nombres <xref:System.Drawing>.  Esto permite dibujar líneas y formas en un solo paso, sin tener que crear objetos gráficos, lápices ni pinceles.  Las técnicas de gráficos complejas, como rellenos de degradado, se pueden ejecutar fácilmente estableciendo algunas propiedades.  
  
 Aunque también es posible dibujar líneas y formas utilizando métodos gráficos, el uso de controles de líneas y formas presenta varias ventajas:  
  
-   Solo se puede llamar a los métodos gráficos en tiempo de ejecución.  Los controles de líneas y formas se pueden agregar en un formulario en tiempo de diseño.  Esto permite ver el aspecto que tienen y colocarlos con precisión; se pueden agregar asimismo en tiempo de ejecución.  
  
-   Los controles de líneas y formas se pueden seleccionar en tiempo de ejecución, y proporcionan eventos como <xref:Microsoft.VisualBasic.PowerPacks.Shape.Click> y <xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A>.  Los resultados de los métodos gráficos no se pueden seleccionar y no proporcionan eventos.  
  
-   Los controles de líneas y formas proporcionan métodos <xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A> y <xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A> que permiten controlar su orden z en tiempo de diseño y en tiempo de ejecución.  El orden z de los métodos gráficos únicamente se puede controlar cambiando su orden de ejecución en tiempo de ejecución.  
  
-   Los controles de líneas y formas son controles sin ventana; no tienen ningún identificador de ventana y, por consiguiente, utilizan menos recursos del sistema.  
  
### Modelo de objetos  
 Los controles de líneas y formas se derivan de una clase <xref:Microsoft.VisualBasic.PowerPacks.Shape> base que define sus propiedades, métodos y eventos compartidos.  
  
 La ilustración siguiente muestra la jerarquía de objetos de líneas y formas.  
  
 ![Diagrama de la jerarquía de objetos de línea y forma](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")  
Jerarquía de objetos de líneas y formas  
  
 La clase <xref:Microsoft.VisualBasic.PowerPacks.LineShape> derivada contiene propiedades, métodos y eventos que son exclusivos de las líneas.  La clase <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> derivada es la clase base de <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> y <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>; contiene propiedades, métodos y eventos comunes para todas las formas.  También puede derivar de <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> para crear sus propios controles `Shape`.  
  
 Las clases <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> y <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> se pueden utilizar para dibujar círculos, óvalos, rectángulos y rectángulos con esquinas redondeadas.  
  
 Cuando se agrega un control de línea o forma a un formulario o contenedor, se crea un objeto <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> invisible.  <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> actúa como un lienzo para las formas incluidas en cada control contenedor; cada <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> tiene un <xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection> correspondiente que le permite recorrer en iteración los controles de líneas y formas.  Puede mover las formas de un contenedor a otro cortándolas y pegándolas, o arrastrándolas y colocándolas.  Al quitar la última forma de un contenedor, también se quita el objeto <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer>.  
  
> [!NOTE]
>  No todos los controles contenedor admiten controles de líneas y formas.  No puede hospedar controles de líneas o formas en un <xref:System.Windows.Forms.TableLayoutPanel> o un <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks>   
 [Cómo: Dibujar líneas con el control LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)   
 [Cómo: Dibujar formas con los controles OvalShape y RectangleShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)   
 [Cómo: Habilitar la tabulación entre las formas](../../../visual-basic/developing-apps/windows-forms/how-to-enable-tabbing-between-shapes-visual-studio.md)
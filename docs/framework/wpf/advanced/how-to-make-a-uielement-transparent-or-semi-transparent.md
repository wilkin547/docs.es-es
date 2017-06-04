---
title: "C&#243;mo: Hacer que un elemento UIElement sea transparente o semitransparente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "opacidad, de UIElements"
  - "transparencia de UIElements"
  - "UIElements, opacidad"
  - "UIElements, transparencia"
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Hacer que un elemento UIElement sea transparente o semitransparente
En este ejemplo se muestra cómo hacer que un elemento <xref:System.Windows.UIElement> sea transparente o semitransparente.  Para hacer que un elemento sea transparente o semitransparente, se establece su propiedad <xref:System.Windows.UIElement.Opacity%2A>.  Un valor de `0.0` hace que el elemento sea completamente transparente, mientras que un valor de `1.0` lo deja completamente opaco.  Un valor de `0.5` aplica al elemento una opacidad del 50%, y así sucesivamente.  La propiedad <xref:System.Windows.UIElement.Opacity%2A> de un elemento se establece en `1.0` de manera predeterminada.  
  
## Ejemplo  
 En el ejemplo siguiente se establece la propiedad <xref:System.Windows.UIElement.Opacity%2A> de un botón en `0.25`, de modo que se aplica a él y a su contenido \(en este caso, el texto del botón\) una opacidad del 25%.  
  
 [!code-xml[brushsamples_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 Si el contenido de un elemento tiene sus propios valores de <xref:System.Windows.UIElement.Opacity%2A>, éstos se multiplican por el valor de la propiedad <xref:System.Windows.UIElement.Opacity%2A> del elemento contenedor.  
  
 En el ejemplo siguiente se establece la propiedad <xref:System.Windows.UIElement.Opacity%2A> de un botón en `0.25` la propiedad <xref:System.Windows.UIElement.Opacity%2A> de un control <xref:System.Windows.Controls.Image> contenido en el botón en `0.5`.  Como resultado, la opacidad resultante de la imagen es del 12,5%: 0,25 \* 0,5 \= 0,125.  
  
 [!code-xml[brushsamples_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 Otra manera de controlar la opacidad de un elemento es establecer la opacidad del objeto <xref:System.Windows.Media.Brush> que pinta el elemento.  Este enfoque permite modificar selectivamente la opacidad de algunas partes de un elemento y proporciona ventajas de rendimiento con respecto al uso de la propiedad <xref:System.Windows.UIElement.Opacity%2A> del elemento.  En el ejemplo siguiente se establece en `0.25` la propiedad <xref:System.Windows.Media.Brush.Opacity%2A> de un objeto <xref:System.Windows.Media.SolidColorBrush> utilizado para pintar la propiedad <xref:System.Windows.Controls.Control.Background%2A> del botón.  Como resultado, el fondo del pincel tiene una opacidad del 25%, pero la opacidad de su contenido \(el texto del botón\) sigue siendo del 100%.  
  
 [!code-xml[brushsamples_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 También puede controlar la opacidad de colores individuales dentro de un pincel.  Para obtener más información acerca de los colores y los pinceles, vea [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  Para obtener un ejemplo que muestra cómo animar la opacidad de un elemento, vea [Animar la opacidad de un elemento o pincel](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).
---
title: "C&#243;mo: Crear una decoraci&#243;n de texto | Microsoft Docs"
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
  - "tipo de línea base"
  - "fuentes, línea base"
  - "fuentes, línea alta"
  - "fuentes, subrayado"
  - "fuentes, subrayado"
  - "tipo de línea alta"
  - "tipo de subrayado"
  - "texto, decoraciones"
  - "tipografía, decoraciones de texto"
  - "tipo de subrayado"
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Crear una decoraci&#243;n de texto
Un objeto <xref:System.Windows.TextDecoration> es una ornamentación visual que se puede agregar al texto.  Hay cuatro tipos de decoraciones de texto: subrayado, línea base, tachado y línea alta.  En el ejemplo siguiente, se muestran las ubicaciones de las decoraciones de texto con respecto al texto.  
  
 ![Diagrama de ubicaciones de decoraciones de texto](../../../../docs/framework/wpf/advanced/media/textdecoration01.png "TextDecoration01")  
Ejemplo de tipos de decoración de texto  
  
 Para agregar una decoración al texto, cree un objeto <xref:System.Windows.TextDecoration> y modifique sus propiedades.  Utilice la propiedad <xref:System.Windows.TextDecoration.Location%2A> para especificar dónde aparecerá la decoración de texto, como un subrayado.  Utilice la propiedad <xref:System.Windows.TextDecoration.Pen%2A> para especificar el aspecto de la decoración de texto, como un relleno sólido o un color de degradado.  Si no especifica un valor para la propiedad <xref:System.Windows.TextDecoration.Pen%2A>, las decoraciones tienen como valor predeterminado el mismo color que el texto.  Una vez definido un objeto <xref:System.Windows.TextDecoration>, agréguelo a la colección <xref:System.Windows.TextDecorations> del objeto de texto deseado.  
  
 En el ejemplo siguiente, se muestra una decoración de texto a la que se la ha aplicado el estilo con un pincel de degradado lineal y un lápiz rayado.  
  
 ![Decoración de texto con subrayado degradado lineal](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")  
Ejemplo de subrayado con un pincel de degradado lineal y un lápiz rayado  
  
 El objeto <xref:System.Windows.Documents.Hyperlink> es un elemento de contenido dinámico insertado que permite hospedar hipervínculos dentro del contenido dinámico.  De forma predeterminada, <xref:System.Windows.Documents.Hyperlink> usa un objeto <xref:System.Windows.TextDecoration> para mostrar un subrayado.  Los objetos <xref:System.Windows.TextDecoration> pueden mejorar el rendimiento al crear instancias, especialmente si dispone de muchos objetos <xref:System.Windows.Documents.Hyperlink>.  Si realiza un uso excesivo de elementos <xref:System.Windows.Documents.Hyperlink>, puede ser conveniente mostrar la línea de subrayado únicamente al desencadenar un evento, como el evento <xref:System.Windows.ContentElement.MouseEnter>.  
  
 En el ejemplo siguiente, el subrayado para el vínculo "My MSN" es dinámico: únicamente aparece cuando se activa el evento <xref:System.Windows.ContentElement.MouseEnter>.  
  
 ![Hipervínculos que muestran TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Hipervínculos definidos con TextDecorations  
  
 Para obtener más información, consulte [Especificar el subrayado de un hipervínculo](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
## Ejemplo  
 En el ejemplo de código siguiente, una decoración de texto de subrayado utiliza el valor de fuente predeterminado.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 En el ejemplo de código siguiente, se crea una decoración de texto de subrayado con un pincel de color sólido para el lápiz.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 En el ejemplo de código siguiente, se crea una decoración de texto subrayado con un pincel de degradado lineal para el lápiz rayado.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## Vea también  
 <xref:System.Windows.TextDecoration>   
 <xref:System.Windows.Documents.Hyperlink>   
 [Especificar el subrayado de un hipervínculo](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)
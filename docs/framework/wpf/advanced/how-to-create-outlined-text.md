---
title: "C&#243;mo: Crear texto con contorno | Microsoft Docs"
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
  - "pincel de degradado"
  - "pincel de degradado lineal"
  - "texto con contorno"
  - "tipografía, pincel de degradado lineal"
  - "tipografía, efectos de contorno"
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Crear texto con contorno
En la mayoría de los casos, al agregar ornamentación a las cadenas de texto en una aplicación de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], se utiliza el texto considerándolo una colección de caracteres discretos, o glifos.  Por ejemplo, podría crear un pincel de degradado lineal y aplicarlo a la propiedad <xref:System.Windows.Controls.Control.Foreground%2A> de un objeto <xref:System.Windows.Controls.TextBox>.  Al mostrar o modificar el cuadro de texto, el pincel de degradado lineal se aplica automáticamente al conjunto actual de caracteres de la cadena de texto.  
  
 ![Texto que se muestra con un pincel de degradado lineal](../../../../docs/framework/wpf/advanced/media/outlinedtext01.png "OutlinedText01")  
Ejemplo de un pincel de degradado lineal aplicado a un cuadro de texto  
  
 Sin embargo, también puede convertir el texto en objetos <xref:System.Windows.Media.Geometry>, lo que permite crear otros tipos de texto visualmente enriquecido.  Por ejemplo, podría crear un objeto <xref:System.Windows.Media.Geometry> basado en el contorno de una cadena de texto.  
  
 ![Esquema de texto que usa un pincel de degradado lineal](../../../../docs/framework/wpf/advanced/media/outlinedtext02.png "OutlinedText02")  
Ejemplo de un pincel de degradado lineal aplicado a la geometría del contorno de texto  
  
 Cuando se convierte el texto en un objeto <xref:System.Windows.Media.Geometry>, deja de ser una colección de caracteres; no se pueden modificar los caracteres de la cadena de texto.  Sin embargo, se puede cambiar la apariencia del texto convertido modificando sus propiedades de trazo y relleno.  El trazo se refiere al contorno del texto convertido; el relleno se refiere al área situada dentro del contorno del texto convertido.  
  
 En los ejemplos siguientes se muestran varias maneras de crear efectos visuales modificando el trazo y el relleno del texto convertido.  
  
 ![Texto con colores diferentes para relleno y trazo](../../../../docs/framework/wpf/advanced/media/outlinedtext03.png "OutlinedText03")  
Ejemplo de cómo establecer el trazo y el relleno en diferentes colores  
  
 ![Texto con pincel de imagen aplicado a trazo](../../../../docs/framework/wpf/advanced/media/outlinedtext04.png "OutlinedText04")  
Ejemplo de un pincel de imagen aplicado al trazo  
  
 También es posible modificar el rectángulo de selección o resaltado del texto convertido.  En el ejemplo siguiente se muestra una manera de crear efectos visuales modificando el trazo y el resaltado del texto convertido.  
  
 ![Texto con pincel de imagen aplicado a trazo](../../../../docs/framework/wpf/advanced/media/outlinedtext05.png "OutlinedText05")  
Ejemplo de un pincel de imagen aplicado al trazo y al resaltado  
  
## Ejemplo  
 La clave para convertir texto en un objeto <xref:System.Windows.Media.Geometry> es utilizar el objeto <xref:System.Windows.Media.FormattedText>.  Una vez creado este objeto, puede utilizar los métodos <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> y <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> para convertir el texto en objetos <xref:System.Windows.Media.Geometry>.  El primer método devuelve la geometría del texto con formato; el segundo método devuelve la geometría del rectángulo de selección del texto con formato.  En el ejemplo de código siguiente se muestra cómo crear un objeto <xref:System.Windows.Media.FormattedText> y recuperar las geometrías del texto con formato y su rectángulo de selección.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 Para mostrar los objetos <xref:System.Windows.Media.Geometry> recuperados, deberá tener acceso al <xref:System.Windows.Media.DrawingContext> del objeto que muestra el texto convertido.  En estos ejemplos de código, esto se hace creando un objeto de control personalizado derivado de una clase que admite la representación definida por el usuario.  
  
 Para mostrar objetos <xref:System.Windows.Media.Geometry> en el control personalizado, invalide el método <xref:System.Windows.UIElement.OnRender%2A>.  El método invalidado deberá utilizar el método <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> para dibujar los objetos <xref:System.Windows.Media.Geometry>.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
## Vea también  
 [Dibujar texto con formato](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
---
title: "C&#243;mo: Habilitar el recorte de texto | Microsoft Docs"
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
  - "documentos, recortar texto"
  - "texto, recortar"
  - "recortar texto"
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Habilitar el recorte de texto
En este ejemplo se muestran el uso y los efectos de los valores disponibles en la enumeración <xref:System.Windows.TextTrimming>.  
  
## Ejemplo  
 En el ejemplo siguiente se define un elemento <xref:System.Windows.Controls.TextBlock> con el atributo <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> establecido.  
  
 [!code-xml[TextTrimmingSnippets#_TextTrimmingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## Ejemplo  
 A continuación se muestra cómo establecer la propiedad <xref:System.Windows.TextTrimming> correspondiente mediante código.  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 En la actualidad existen tres opciones para recortar texto: **CharacterEllipsis**, **WordEllipsis** y **None**.  
  
 Cuando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> se establece en **CharacterEllipsis**, el texto se recorta y se continúa con puntos suspensivos en el carácter situado más próximo al borde de recorte.  Este valor suele recortar el texto de modo que se ajuste más al límite de recorte, pero puede dar lugar al recorte parcial de palabras.  En la ilustración siguiente se muestra el efecto de este valor en un objeto <xref:System.Windows.Controls.TextBlock> similar al definido anteriormente.  
  
 ![Ejemplo: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming\_Character")  
  
 Cuando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> se establece en **WordEllipsis**, el texto se recorta y se continúa con puntos suspensivos al final de la primera palabra completa más próxima al borde de recorte.  Este valor no mostrará palabras parcialmente recortadas, pero no suele recortar el texto tan cerca del borde de recorte como el valor **CharacterEllipsis**.  En la ilustración siguiente se muestra el efecto de este valor en el objeto <xref:System.Windows.Controls.TextBlock> definido anteriormente.  
  
 ![Ejemplo: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming\_Word")  
  
 Cuando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> se establece en **None**, no se recorta el texto.  En este caso, el texto se corta simplemente en el límite del contenedor de texto primario.  En la ilustración siguiente se muestra el efecto de este valor en un objeto <xref:System.Windows.Controls.TextBlock> similar al definido anteriormente.  
  
 ![Ejemplo: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming\_None")
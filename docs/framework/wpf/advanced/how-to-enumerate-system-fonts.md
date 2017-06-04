---
title: "C&#243;mo: Enumerar fuentes del sistema | Microsoft Docs"
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
  - "enumerar, fuentes del sistema"
  - "fuentes, enumerar"
  - "fuentes del sistema, enumerar"
  - "tipografía, enumerar fuentes del sistema"
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Enumerar fuentes del sistema
## Ejemplo  
 En el ejemplo siguiente se muestra cómo enumerar las fuentes en la colección de fuentes del sistema.  El nombre de la familia de fuentes de cada <xref:System.Windows.Media.FontFamily> de <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> se agrega como un elemento a un cuadro combinado.  
  
 [!code-csharp[TextOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 Si hay varias versiones de la misma familia de fuentes que residen en el mismo directorio, la enumeración de fuentes de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] devuelve la versión más reciente de la fuente.  Si la información de versión no proporciona la resolución, se devuelve la fuente con la marca de tiempo más reciente.  Si la información de marca de tiempo es equivalente, se devuelve el archivo de fuente que aparece primero en orden alfabético.
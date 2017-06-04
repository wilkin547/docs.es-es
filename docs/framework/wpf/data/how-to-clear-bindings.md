---
title: "C&#243;mo: Borrar enlaces | Microsoft Docs"
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
  - "enlaces, borrar"
  - "borrar enlaces"
  - "enlace de datos, borrar enlaces"
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Borrar enlaces
En este ejemplo se muestra cómo borrar los enlaces de un objeto.  
  
## Ejemplo  
 Para borrar un enlace de una propiedad individual de un objeto, llame a <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> como se muestra en el ejemplo siguiente.  En el ejemplo siguiente se quita el enlace de <xref:System.Windows.Controls.TextBlock.TextProperty> de *mytext*, un objeto <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 Al borrar el enlace, se quita el enlace de modo que el valor de la [propiedad de dependencia](GTMT) se cambia a aquél que tendría sin el enlace.  Este valor puede ser un valor predeterminado, un valor heredado o un valor de un enlace de la plantilla de datos.  
  
 Para borrar los enlaces de todas las posibles propiedades de un objeto, utilice <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.  
  
## Vea también  
 <xref:System.Windows.Data.BindingOperations>   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
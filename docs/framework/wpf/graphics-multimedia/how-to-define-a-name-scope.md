---
title: "C&#243;mo: Definir un &#225;mbito de nombres | Microsoft Docs"
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
  - "animación, Guiones gráficos, en código de procedimientos"
  - "ámbito de nombres, definir"
  - "Guiones gráficos, animar en código de procedimientos"
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Definir un &#225;mbito de nombres
Para animar con <xref:System.Windows.Media.Animation.Storyboard> en código, debe crear un objeto <xref:System.Windows.NameScope> y registrar los nombres de los objetos de destino para el elemento que posee ese ámbito de nombres.  En el ejemplo siguiente se crea un objeto <xref:System.Windows.NameScope> para `myMainPanel`.  Se agregan dos botones, `button1` y `button2`, al panel, y se registran sus nombres.  Se crean varias animaciones y un <xref:System.Windows.Media.Animation.Storyboard>.  El método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> del guión gráfico se utiliza para iniciar las animaciones.  
  
 Dado que `button1`, `button2` y `myMainPanel` comparten el mismo ámbito de nombres, cualquiera de ellos se puede utilizar con el método <xref:System.Windows.Media.Animation.Storyboard><xref:System.Windows.Media.Animation.Storyboard.Begin%2A> para iniciar las animaciones.  
  
## Ejemplo  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## Vea también  
 [Animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
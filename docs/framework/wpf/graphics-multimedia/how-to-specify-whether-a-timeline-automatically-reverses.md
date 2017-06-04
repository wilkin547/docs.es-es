---
title: "C&#243;mo: Especificar si una escala de tiempo se invierte autom&#225;ticamente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "AutoReverse (propiedad de escalas de tiempo)"
  - "Escalas de tiempo, AutoReverse (propiedad)"
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Especificar si una escala de tiempo se invierte autom&#225;ticamente
La propiedad <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> de una escala de tiempo determina si ésta retrocede después de completar una iteración de avance.  En el ejemplo siguiente se muestran varias animaciones con valores idénticos de duración y destino, pero con valores de <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> diferentes.  Para mostrar cómo se comporta la propiedad <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> con valores de <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> diferentes, algunas animaciones se configuran para que se repitan.  La última animación muestra cómo funciona la propiedad <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> en las escalas de tiempo anidadas.  
  
## Ejemplo  
 [!code-xml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
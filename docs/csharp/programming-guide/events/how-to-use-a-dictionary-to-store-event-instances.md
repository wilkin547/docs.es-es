---
title: "C&#243;mo: Utilizar un diccionario para almacenar instancias de eventos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "eventos [C#], almacenar instancias en un diccionario"
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Utilizar un diccionario para almacenar instancias de eventos (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Uno de los usos de `accessor-declarations` consiste en exponer numerosos eventos sin tener que asignar un campo para cada uno, sino utilizando en su lugar un diccionario para almacenar las instancias de los eventos.  Esto sólo resulta útil si se dispone de muchos eventos, pero se prevé que la mayoría de ellos no se implementarán.  
  
## Ejemplo  
 [!code-cs[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Eventos](../../../csharp/programming-guide/events/index.md)   
 [Delegados](../../../csharp/programming-guide/delegates/index.md)
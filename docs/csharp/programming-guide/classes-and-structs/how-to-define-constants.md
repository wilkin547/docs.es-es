---
title: "C&#243;mo: Definir constantes en C# | Microsoft Docs"
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
  - "lenguaje C#, constantes"
  - "constantes [C#]"
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Definir constantes en C# #
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Las constantes son campos cuyos valores se establecen en tiempo de compilación y no se pueden cambiar.  Utilice constantes a fin de proporcionar nombres significativos en lugar de literales numéricos \("números mágicos"\) para valores especiales.  
  
> [!NOTE]
>  En C\#, la directiva de preprocesador [\#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) no se puede utilizar para definir constantes de la forma en que se utiliza habitualmente en C y C\+\+.  
  
 Para definir valores constantes de tipos enteros \(`int`, `byte`, etc.\) utilice un tipo enumerado.  Para obtener más información, consulte [enum](../../../csharp/language-reference/keywords/enum.md).  
  
 Un método para definir constantes no integrales consiste en agruparlas en una clase estática única denominada `Constants`.  Esto requerirá que todas las referencias a las constantes vayan precedidas del nombre de clase, como se muestra en el ejemplo siguiente.  
  
## Ejemplo  
 [!code-cs[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]  
  
 El uso del calificador de nombres de clase ayuda a garantizar que los usuarios de la constante entiendan que es una constante y no se puede modificar.  
  
## Vea también  
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)
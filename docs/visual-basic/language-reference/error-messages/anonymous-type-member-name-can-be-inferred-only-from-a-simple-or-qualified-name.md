---
title: "El nombre de miembro de tipo an&#243;nimo s&#243;lo se puede inferir a partir de un nombre simple o completo sin argumentos | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36556"
  - "bc36556"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36556"
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El nombre de miembro de tipo an&#243;nimo s&#243;lo se puede inferir a partir de un nombre simple o completo sin argumentos
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

No puede inferir un nombre de miembro de tipo anónimo a partir de una expresión compleja.  
  
```vb#  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 Para obtener más información sobre los orígenes a partir de los cuales los tipos anónimos pueden inferir o no nombres de miembros y tipos, vea [Cómo: Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
 **Id. de error:** BC36556  
  
### Para corregir este error  
  
-   Asigne la expresión a un nombre de miembro, como se muestra en el código siguiente:  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## Vea también  
 [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Cómo: Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
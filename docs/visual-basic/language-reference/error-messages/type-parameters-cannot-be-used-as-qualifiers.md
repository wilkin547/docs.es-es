---
title: "Los par&#225;metros de tipo no se pueden utilizar como calificadores | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc32098"
  - "bc32098"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32098"
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Los par&#225;metros de tipo no se pueden utilizar como calificadores
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un elemento de programación se califica con una cadena de calificación que incluye un parámetro de tipo.  
  
 Un parámetro de tipo representa un requisito para un tipo que será proporcionado cuando se construya el tipo genérico.  No representa un tipo definido concreto.  Una cadena de calificación sólo debe incluir elementos que se definen en tiempo de compilación.  
  
 Las instrucciones siguientes pueden generar este error.  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 **Identificador de error:** BC32098  
  
### Para corregir este error  
  
1.  Quite el parámetro de tipo de la cadena de calificación o reemplácelo con un tipo definido.  
  
2.  Si necesita utilizar un tipo construido para buscar el elemento de programación que se califica, debe utilizar lógica de programa adicional.  
  
## Vea también  
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)
---
title: "No se admite la inferencia de tipos que acepten valores NULL en este contexto | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc36629"
  - "bc36629"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36629"
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# No se admite la inferencia de tipos que acepten valores NULL en este contexto
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Las estructuras y tipos de valor se pueden declarar como tipos que aceptan valores NULL.  
  
```vb#  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Sin embargo, no puede usar la declaración que acepta valores NULL en combinación con la inferencia de tipos.  Los ejemplos siguientes producen este error.  
  
```vb#  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **Id. de error:** BC36629  
  
### Para corregir este error  
  
-   Use una cláusula `As` para declarar la variable como tipo que acepta valores NULL.  
  
## Vea también  
 [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
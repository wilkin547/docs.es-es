---
title: "Los par&#225;metros gen&#233;ricos utilizados como tipos de par&#225;metros opcionales deben tener restricci&#243;n de clase | Microsoft Docs"
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
  - "vbc32124"
  - "bc32124"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32124"
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Los par&#225;metros gen&#233;ricos utilizados como tipos de par&#225;metros opcionales deben tener restricci&#243;n de clase
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Un procedimiento está declarado con un parámetro opcional que utiliza un parámetro de tipo que no está restringido para ser un tipo de referencia.  
  
 Siempre debe proporcionar un valor predeterminado para cada parámetro opcional.  Si el parámetro es de un tipo de referencia, el valor opcional debe ser `Nothing`, que es un valor válido para cualquier tipo de referencia.  Sin embargo, si el parámetro es de tipo de valor, ese tipo debe ser un tipo de datos básico predefinido por Visual Basic.  Esto se debe a que un tipo de valor compuesto, como una estructura definida por el usuario, no tiene ningún valor predeterminado válido.  
  
 Cuando utilice un parámetro de tipo para un parámetro opcional, debe garantizar que es de un tipo de referencia para impedir la posibilidad de un tipo de valor que no tenga ningún valor predeterminado válido.  Esto significa que debe restringir el parámetro de tipo con la palabra clave `Class` o con el nombre de una clase específica.  
  
 **Identificador de error:** BC32124  
  
### Para corregir este error  
  
-   Restrinja el parámetro de tipo para aceptar sólo un tipo de referencia o no lo utilice para el parámetro opcional.  
  
## Vea también  
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)   
 [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Nothing](../../../visual-basic/language-reference/nothing.md)
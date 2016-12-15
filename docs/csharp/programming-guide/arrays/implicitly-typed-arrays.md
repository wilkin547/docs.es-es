---
title: "Matrices con asignaci&#243;n impl&#237;cita de tipos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "matrices [C#], con tipo implícito"
  - "lenguaje C#, matrices con tipo implícito"
  - "matrices con tipo implícito [C#]"
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Matrices con asignaci&#243;n impl&#237;cita de tipos (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Puede crear una matriz con tipo implícito en la que el tipo de la instancia de matriz se deduce de los elementos especificados en el inicializador de matriz.  Las reglas de cualquier variable con tipo implícito también se aplican a las matrices con tipo implícito.  Para obtener más información, consulte [Variables locales con asignación implícita de tipos](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
 Las matrices con tipo implícito se utilizan normalmente en expresiones de consulta junto con tipos anónimos e inicializadores de objeto y colección.  
  
 En los ejemplos siguientes se muestra cómo crear una matriz con tipo implícito:  
  
 [!code-cs[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]  
  
 En el ejemplo anterior, observe que con las matrices con tipo implícito no se utilizan corchetes en el lado izquierdo de la instrucción de inicialización.  Observe además que las matrices escalonadas se inicializan utilizando `new []` al igual que las matrices unidimensionales.  
  
## Matrices con tipo implícito en inicializadores de objeto  
 Cuando se crea un tipo anónimo que contiene una matriz, la matriz debe tener un tipo implícito en el inicializador de objeto del tipo.  En el ejemplo siguiente, `contacts` es una matriz con tipo implícito de tipos anónimos, cada uno de los cuales contiene una matriz denominada `PhoneNumbers`.  Observe que la palabra clave `var` no se utiliza en los inicializadores de objeto.  
  
 [!code-cs[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Variables locales con asignación implícita de tipos](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)   
 [Matrices](../../../csharp/programming-guide/arrays/index.md)   
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Inicializadores de objeto y colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)   
 [var](../../../csharp/language-reference/keywords/var.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)
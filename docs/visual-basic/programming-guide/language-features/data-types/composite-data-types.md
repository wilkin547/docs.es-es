---
title: "Tipos de datos compuestos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "matrices [Visual Basic], tipos de datos compuestos"
  - "clases [Visual Basic], tipos de datos compuestos"
  - "clases [Visual Basic], tipos compuestos"
  - "tipos de datos compuestos"
  - "tipos compuestos"
  - "tipos de datos [Visual Basic], compuestos"
  - "estructuras, tipos de datos compuestos"
  - "tipos [Visual Basic], compuestos"
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Tipos de datos compuestos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Además de los tipos de datos básicos que [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona, también es posible juntar elementos de distintos tipos para crear *tipos de datos compuestos*, como estructuras, matrices y clases.  Pueden crearse tipos de datos compuestos a partir de tipos elementales y de otros tipos compuestos.  Por ejemplo, puede definir una matriz de elementos de estructura, o una estructura con miembros de matriz.  
  
## Tipos de datos  
 Un tipo compuesto es diferente del tipo de datos de cualquiera de sus componentes.  Por ejemplo, una matriz de elementos `Integer` no es del tipo de datos `Integer`.  
  
 Un tipo de datos de matriz se representa normalmente mediante el tipo de elemento, paréntesis y comas, tal como necesario.  Por ejemplo, una matriz unidimensional de los elementos `String` se representa como `String()` y una matriz bidimensional de los elementos `Boolean` se representa como `Boolean(,)`.  
  
## Tipos de estructura  
 No existe ningún tipo de datos que incluya todas las estructuras.  En su lugar, una definición de una estructura representa un tipo de datos único, aunque dos estructuras definan elementos idénticos en el mismo orden.  Sin embargo, si crea dos o más instancias de la misma estructura, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] considera que son del mismo tipo de datos.  
  
## Tipos de matriz  
 No existe ningún tipo de datos que incluya todas las matrices.  El tipo de datos de una instancia específica de una matriz está determinada por lo siguiente:  
  
-   El hecho de ser una matriz  
  
-   El rango \(las dimensiones\) de la matriz  
  
-   El tipo de elemento de la matriz  
  
 En particular, la longitud de una dimensión determinada no forma parte del tipo de datos de la instancia.  Esto se ilustra en el siguiente ejemplo:  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 En el ejemplo anterior, las variables de matriz `arrayA` y `arrayB` se consideran del mismo tipo de datos \(`Byte()`\), aunque se hayan inicializado con distintas longitudes.  Las variables `arrayB` y `arrayC` no son del mismo tipo porque sus tipos de elementos son diferentes.  Las variables `arrayC` y `arrayD` no son del mismo tipo porque sus rangos son diferentes.  Las variables `arrayD` y `arrayE` tienen el mismo tipo \(`Short(,)`\) porque sus rangos y tipos de elementos son los mismos, incluso aunque `arrayD` no esté aún inicializado.  
  
 Para obtener más información sobre matrices, consulte [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## Tipos de clase  
 No existe ningún tipo de datos que incluya todas las clases.  Aunque una clase puede heredar de otra clase, cada una es de un tipo de datos distinto.  Varias instancias de la misma clase son del mismo tipo de datos.  Si asigna una variable de instancia de clase a otra, no sólo tienen el mismo tipo de datos, sino que señalan a la misma instancia de clase en memoria.  
  
 Para obtener más información sobre clases, consulte [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Tipos de datos elementales](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Tipos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Cómo: Contener más de un valor en una variable](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
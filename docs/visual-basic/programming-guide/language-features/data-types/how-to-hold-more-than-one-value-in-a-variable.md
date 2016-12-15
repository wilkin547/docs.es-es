---
title: "C&#243;mo: Contener m&#225;s de un valor en una variable (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "matrices [Visual Basic], errores de compilación"
  - "matrices [Visual Basic], tipos de datos compuestos"
  - "clases [Visual Basic], tipos de datos compuestos"
  - "tipos de datos compuestos"
  - "tipos compuestos"
  - "tipos de datos [Visual Basic], compuestos"
  - "estructuras, tipos de datos compuestos"
  - "tipos [Visual Basic], compuestos"
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Contener m&#225;s de un valor en una variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Una variable contiene más de un valor si la declara como un *tipo de datos compuesto*.  
  
 [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) incluye estructuras, matrices y clases.  Una variable de un tipo de datos compuesto puede contener una combinación de tipos de datos básicos y otros tipos compuestos.  Las estructuras y clases pueden contener código así como datos.  
  
### Para contener varios valores en una variable  
  
1.  Determine qué tipo de datos compuesto desea utilizar para la variable.  
  
2.  Si el tipo de datos compuesto no está aún definido, defínalo para que la variable pueda utilizarlo.  
  
    -   Defina una estructura con [Structure \(Instrucción\)](../../../../visual-basic/language-reference/statements/structure-statement.md).  
  
    -   Defina una matriz con [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
    -   Defina una clase con [Class \(Instrucción\)](../../../../visual-basic/language-reference/statements/class-statement.md).  
  
3.  Declare la variable con una instrucción `Dim`.  
  
4.  Agregue detrás del nombre de variable una cláusula `As`.  
  
5.  Agregue detrás de la palabra clave `As` el nombre del tipo de datos compuesto adecuado.  
  
## Vea también  
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
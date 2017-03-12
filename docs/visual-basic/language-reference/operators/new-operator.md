---
title: "New (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.new"
  - "vb.NewConstraint"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "restricciones, New (palabra clave)"
  - "restricciones, tipos genéricos de Visual Basic"
  - "genéricos [Visual Basic], restricciones"
  - "New (restricción)"
  - "New (palabra clave)"
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# New (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Introduce una cláusula `New` para crear una nueva instancia de objeto, especifica una restricción de constructor en un parámetro de tipo o identifica un procedimiento `Sub` como constructor de clase.  
  
## Comentarios  
 En una declaración o instrucción de asignación, una cláusula `New` debe especificar una clase definida a partir de la que se pueda crear la instancia.  Esto significa que la clase debe exponer uno o más constructores a los que el código de llamada pueda tener acceso.  
  
 Puede utilizar una cláusula `New` en una instrucción de declaración o en una instrucción de asignación.  Cuando se ejecuta la instrucción, esta llama al constructor apropiado de la clase especificada y le pasa los argumentos que se le han proporcionado.  En el ejemplo siguiente se muestra esto creando instancias de una clase `Customer` que tiene dos constructores, uno que no toma parámetros y otro que toma un parámetro de cadena.  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/visualbasic/new-operator_1.vb)]  
  
 Dado que las matrices son clases, `New` puede crear una nueva instancia de la matriz, como se muestra en los ejemplos siguientes.  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/visualbasic/new-operator_2.vb)]  
  
 Common Language Runtime \(CLR\) produce un error <xref:System.OutOfMemoryException> si no hay memoria suficiente para crear la nueva instancia.  
  
> [!NOTE]
>  La palabra clave `New` también se usa en listas de parámetros de tipo para especificar que el tipo proporcionado debe exponer un constructor sin parámetros al que el código pueda tener acceso.  Para obtener más información sobre los parámetros de tipo y las restricciones, vea [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Para crear un procedimiento de constructor para una clase, establezca el nombre de un procedimiento `Sub` en la palabra clave `New`.  Para obtener más información, vea [Duración de los objetos: cómo se crean y destruyen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
 La palabra clave `New` se puede utilizar en estos contextos:  
  
 [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Vea también  
 <xref:System.OutOfMemoryException>   
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)   
 [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)   
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Duración de los objetos: cómo se crean y destruyen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
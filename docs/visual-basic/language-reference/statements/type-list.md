---
title: "Lista de tipos (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "StructureConstraint"
  - "vb.StructureConstraint"
  - "ClassConstraint"
  - "vb.ClassConstraint"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "restricción de clase"
  - "restricciones, Class (palabra clave)"
  - "restricciones, en parámetros de tipo"
  - "restricciones, Structure (palabra clave)"
  - "restricciones, tipos genéricos de Visual Basic"
  - "parámetros genéricos"
  - "genéricos [Visual Basic], restricciones"
  - "genéricos [Visual Basic], tipos genéricos"
  - "genéricos [Visual Basic], lista de tipos"
  - "genéricos [Visual Basic], parámetros de tipo"
  - "parámetros, genéricos"
  - "parámetros, tipo"
  - "Structure (restricción)"
  - "parámetros de tipo"
  - "parámetros de tipo, restricciones"
  - "tipos [Visual Basic], genéricos"
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
caps.latest.revision: 33
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 33
---
# Lista de tipos (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica los *parámetros de tipo* para un elemento de programación *genérico*.  Los parámetros múltiples se separan por comas.  A continuación, aparece la sintaxis para un parámetro de tipo.  
  
## Sintaxis  
  
```  
  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`genericmodifier`|Opcional.  Solo se puede utilizar en interfaces y delegados genéricos.  Puede declarar una covariante de tipo utilizando la palabra clave [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) o una contravariante utilizando la palabra clave [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md).  Vea [Covarianza y contravarianza](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md).|  
|`typename`|Obligatorio.  Nombre del parámetro de tipo.  Éste es un marcador de posición, que debe ser reemplazado por un tipo definido proporcionado por el argumento de tipo correspondiente.|  
|`constraintlist`|Opcional.  Lista de requisitos que restringe el tipo de datos que se puede proporcionar para `typename`.  Si tiene varias restricciones, inclúyalas entre llaves \(`{ }`\) y sepárelas por comas.  Debe introducir la lista de restricciones con la palabra clave [As](../../../visual-basic/language-reference/statements/as-clause.md).  Sólo se utiliza `As` una vez, al principio de la lista.|  
  
## Comentarios  
 Cada elemento de programación genérico debe aceptar por lo menos un parámetro de tipo.  Un parámetro de tipo es un marcador de posición para un tipo específico \(un *elemento construido*\) que el código de cliente especifica cuando crea una instancia del tipo genérico.  Puede definir una clase, estructura, interfaz, procedimiento o delegado de tipo genérico.  
  
 Para obtener más información sobre cuándo definir un tipo genérico, vea [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).  Para obtener más información sobre nombres de parámetros de tipo, vea [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## Reglas  
  
-   **Paréntesis.** Si proporciona una lista de parámetros de tipo, debe incluirla entre paréntesis e introducir la lista con la palabra clave [Of](../../../visual-basic/language-reference/statements/of-clause.md).  Sólo se utiliza `Of` una vez, al principio de la lista.  
  
-   **Restricciones.** Una lista de *restricciones* de un parámetro de tipo puede incluir los elementos siguientes en cualquier combinación:  
  
    -   Cualquier número de interfaces.  El tipo proporcionado debe implementar todas las interfaces en esta lista.  
  
    -   A lo sumo una clase.  El tipo proporcionado debe heredar de esa clase.  
  
    -   Palabra clave `New`.  El tipo proporcionado debe exponer un constructor sin parámetros al que el tipo genérico pueda tener acceso.  Esto es útil si restringe un parámetro de tipo a una o varias interfaces.  Un tipo que implementa interfaces no expone necesariamente un constructor, y en función del nivel de acceso de un constructor, es posible que el código dentro del tipo genérico no pueda tener acceso a él.  
  
    -   Palabra clave `Class` o `Structure`.  La palabra clave `Class` restringe un parámetro de tipo genérico para exigir que cualquier argumento de tipo que se le pase sea un tipo de referencia, por ejemplo una cadena, una matriz, un delegado o un objeto creado a partir de una clase.  La palabra clave `Structure` restringe un parámetro de tipo genérico para exigir que cualquier argumento de tipo que se le pase sea un tipo de valor, por ejemplo una estructura, una enumeración o un tipo de datos básico.  No es posible incluir `Class` y `Structure` en la misma `constraintlist`.  
  
     El tipo proporcionado debe satisfacer cada requisito que se incluya en `constraintlist`.  
  
     Las restricciones de cada parámetro de tipo son independientes de las restricciones de otros parámetros de tipo.  
  
## Comportamiento  
  
-   **Sustitución en tiempo de compilación** Cuando crea un tipo construido a partir de un elemento de programación genérico, proporciona un tipo definido para cada parámetro de tipo.  El compilador de Visual Basic sustituye cada aparición de `typename` por el tipo proporcionado dentro del elemento genérico.  
  
-   **Ausencia de restricciones.** Si no especifica ninguna restricción en un parámetro de tipo, el código está limitado a las operaciones y los miembros admitidos por [Object \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/object-data-type.md) para este parámetro de tipo.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra un esquema de definición de una clase de diccionario genérico, incluido un esquema de función para agregar una nueva entrada al diccionario.  
  
 [!code-vb[VbVbalrStatements#3](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_1.vb)]  
  
## Ejemplo  
 Como `dictionary` es genérico, el código que lo utiliza puede crear una variedad de objetos a partir de él, cada uno de los cuales tiene la misma funcionalidad pero que actúa en un tipo de datos diferente.  En el ejemplo siguiente se muestra una línea de código que crea un objeto `dictionary` con entradas `String` y claves `Integer`.  
  
 [!code-vb[VbVbalrStatements#4](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_2.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra el esquema de definición equivalente generado por el ejemplo anterior.  
  
 [!code-vb[VbVbalrStatements#5](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_3.vb)]  
  
## Vea también  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)   
 [New \(Operador\)](../../../visual-basic/language-reference/operators/new-operator.md)   
 [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Object \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Cómo: Utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Covarianza y contravarianza](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
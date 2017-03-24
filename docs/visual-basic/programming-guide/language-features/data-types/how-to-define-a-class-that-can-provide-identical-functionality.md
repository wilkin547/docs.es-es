---
title: "C&#243;mo: Definir una clase que pueda proporcionar la misma funcionalidad en tipos de datos diferentes (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "argumentos de tipo de datos, usar"
  - "parámetros de tipo, definir"
  - "argumentos de tipo de datos, definir"
  - "argumentos [Visual Basic], tipos de datos"
  - "Of (palabra clave), usar"
  - "restricciones, tipos genéricos de Visual Basic"
  - "parámetros genéricos"
  - "parámetros de tipo de datos"
  - "parámetros de tipo de datos, usar"
  - "genéricos [Visual Basic], definir clases con parámetros de tipo"
  - "tipos de datos [Visual Basic], como parámetros"
  - "tipos de datos [Visual Basic], como argumentos"
  - "parámetros, tipo"
  - "argumentos de tipo"
  - "tipos [Visual Basic], genéricos"
  - "parámetros, genéricos"
  - "parámetros de tipo"
  - "argumentos de tipo de datos"
  - "parámetros, tipo de datos"
  - "genéricos [Visual Basic], definir tipos genéricos"
  - "parámetros de tipo de datos, definir"
  - "argumentos de tipo, definir"
  - "argumentos [Visual Basic], tipo"
ms.assetid: a914adf8-e68f-4819-a6b1-200d1cf1c21c
caps.latest.revision: 29
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 29
---
# C&#243;mo: Definir una clase que pueda proporcionar la misma funcionalidad en tipos de datos diferentes (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Puede definir una clase desde la que se puedan crear objetos que proporcionen una funcionalidad idéntica en tipos de datos diferentes. Para ello, especifique uno o más *parámetros de tipo* en la definición. Posteriormente, la clase puede servir de plantilla para los objetos que usan distintos tipos de datos. Una clase definida de esta manera se denomina *clase genérica*.  
  
 La ventaja de definir una clase genérica es que se define una sola vez y, después, el código puede usarla para crear muchos objetos que emplean una gran variedad de tipos de datos. El resultado es rendimiento mayor que al definir la clase con el tipo `Object`.  
  
 Además de clases, también puede definir y usar estructuras genéricas, interfaces, procedimientos y delegados.  
  
### Para definir una clase con un parámetro de tipo  
  
1.  Defina la clase de la manera normal.  
  
2.  Agregue `(Of` *typeparameter*`)` inmediatamente después del nombre de clase para especificar un parámetro de tipo.  
  
3.  Si tiene más de un parámetro de tipo, realice una lista separada por comas entre paréntesis. No repita la palabra clave `Of`.  
  
4.  Si el código realiza operaciones en un parámetro de tipo distintas de la asignación simple, siga ese parámetro de tipo con una cláusula `As` para agregar una o más *restricciones*. Una restricción garantiza que el tipo proporcionado para ese parámetro de tipo satisfaga un requisito como el siguiente:  
  
    -   Admitir una operación, como `>`, que realice el código.  
  
    -   Admita a un miembro, como un método, al que accede el código.  
  
    -   Exponer un constructor sin parámetros.  
  
     Si no especifica ninguna restricción, las únicas operaciones y miembros que el código podrá usar son las que admite el [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md). Para obtener más información, consulta [Lista de tipos](../../../../visual-basic/language-reference/statements/type-list.md).  
  
5.  Identifique cada miembro de clase que deba declararse con un tipo suministrado y declárelo `As` `typeparameter`. Esto se aplica al almacenamiento interno, los parámetros de procedimiento y los valores devueltos.  
  
6.  Asegúrese de que el código solo usa operaciones y métodos admitidos por cualquier tipo de datos que pueda proporcionar a `itemType`.  
  
     En el ejemplo siguiente se define una clase que administra una lista muy simple. Contiene la lista de la matriz interna `items` y el código que la usa puede declarar el tipo de datos de los elementos de la lista. Un constructor con parámetros permite que el código que lo usa establezca el límite superior de `items`, y el constructor predeterminado lo establece en 9 \(para un total de 10 elementos\).  
  
     [!code-vb[VbVbalrDataTypes#7](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-define-a-class-that-can-provide-identical-functionality_1.vb)]  
  
     Puede declarar una clase de `simpleList` para que contenga una lista de valores `Integer`, otra para que contenga una lista de valores `String` y otra para que contenga valores `Date`. Excepto para el tipo de datos de los miembros de la lista, los objetos creados a partir de todas estas clases se comportan exactamente igual.  
  
     El argumento de tipo que el código que lo usa proporciona a `itemType` puede ser un tipo intrínseco como `Boolean` o `Double`, una estructura, una enumeración o cualquier tipo de clase, incluida una que defina la aplicación.  
  
     Puede probar la clase `simpleList` con el siguiente código.  
  
     [!code-vb[VbVbalrDataTypes#8](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-define-a-class-that-can-provide-identical-functionality_2.vb)]  
  
## Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Tipos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)   
 [Of](../../../../visual-basic/language-reference/statements/of-clause.md)   
 [Lista de tipos](../../../../visual-basic/language-reference/statements/type-list.md)   
 [Cómo: Utilizar una clase genérica](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md)
---
title: "Inicializadores de colecci&#243;n (Visual Basic) | Microsoft Docs"
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
  - "vb.CollectionInitializer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "inicializadores de colección [Visual Basic]"
ms.assetid: a9290329-77b0-4fdf-ae75-8fc17287f469
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Inicializadores de colecci&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Los *inicializadores de colección* proporcionan una sintaxis abreviada que permite crear una colección y rellenarla con un conjunto inicial de valores.  Este tipo de inicializadores son útiles cuando se crea una colección a partir de un conjunto de valores conocidos como, por ejemplo, una lista de opciones de menú o categorías, un conjunto inicial de valores numéricos, una lista estática de cadenas \(como nombres de día o mes\), o ubicaciones geográficas \(por ejemplo, una lista de estados que se usa con fines de validación\).  
  
 Para obtener más información sobre las colecciones, vea [Colecciones](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Un inicializador de colección se identifica mediante la palabra clave `From` seguida de llaves \(`{}`\).  Esta sintaxis es similar a la sintaxis de literales de matriz descrita en [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  En los siguientes ejemplos se muestran varias formas de usar los inicializadores de colección para crear colecciones.  
  
 [!code-vb[VbVbalrCollectionInitializers#1](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_1.vb)]  
  
> [!NOTE]
>  C\# también proporciona inicializadores de colección.  Los inicializadores de colección de C\# proporcionan la misma funcionalidad que los de Visual Basic.  Para obtener más información acerca de los inicializadores de colección de C\#, vea [Inicializadores de objeto y colección](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## Sintaxis  
 Un inicializador de colección está formado por una lista de valores separados por comas que se encierran entre llaves \(`{}`\) precedida por la palabra clave `From`, como se muestra en el código siguiente.  
  
 [!code-vb[VbVbalrCollectionInitializers#2](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_2.vb)]  
  
 Al crear una colección, como un objeto <xref:System.Collections.Generic.List%601> o <xref:System.Collections.Generic.Dictionary%602>, debe proporcionar el tipo de colección antes que el inicializador de colección, como se muestra en el código siguiente.  
  
 [!code-vb[VbVbalrCollectionInitializers#13](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_3.vb)]  
  
> [!NOTE]
>  No puede combinar un inicializador de colección y un inicializador de objeto para inicializar el mismo objeto de colección.  Puede utilizar los inicializadores de objeto para inicializar objetos en un inicializador de colección.  
  
## Crear una colección mediante un inicializador de colección  
 Al crear una colección mediante un inicializador de colección, cada uno de los valores que se proporciona en el inicializador de colección se pasa al método `Add` adecuado de la colección.  Por ejemplo, si se crea un objeto <xref:System.Collections.Generic.List%601> mediante un inicializador de colección, cada valor de cadena del inicializador de colección se pasa al método <xref:System.Collections.Generic.List%601.Add%2A>.  Si desea crear una colección mediante un inicializador de colección, se debe especificar un tipo de colección válido.  Entre los ejemplos de tipos de colección válidos se incluyen las clases que implementan la interfaz <xref:System.Collections.Generic.IEnumerable%601> o que heredan la clase <xref:System.Collections.CollectionBase>.  El tipo especificado también debe exponer un método `Add` que cumpla los siguientes criterios.  
  
-   El método `Add` debe estar disponible desde el ámbito en el que se llama al inicializador de colección.  El método `Add` no tiene que ser público si el inicializador de colección se usa en un escenario donde se puede tener acceso a los métodos no públicos de la colección.  
  
-   El método `Add` debe ser un miembro de instancia o un miembro `Shared` de la clase de colección o bien un método de extensión.  
  
-   Debe existir un método `Add` que se pueda corresponder con los tipos proporcionados en el inicializador de colección, en función de reglas de resolución de sobrecarga.  
  
 Así, en el ejemplo de código siguiente se muestra cómo crear una colección `List(Of Customer)` mediante un inicializador de colección.  Al ejecutar el código, cada uno de los objetos `Customer` se pasa al método `Add(Customer)` de la lista genérica.  
  
 [!code-vb[VbVbalrCollectionInitializers#9](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_4.vb)]  
  
 En el ejemplo de código siguiente se muestra código equivalente que no usa un inicializador de colección.  
  
 [!code-vb[VbVbalrCollectionInitializers#10](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_5.vb)]  
  
 Si la colección tiene un método `Add` con parámetros que coinciden con el constructor para el objeto `Customer`, se pueden anidar los valores de parámetro del método `Add` dentro de los inicializadores de colección, tal como se explica en la sección siguiente.  Si la colección no tiene este tipo de método `Add`, se puede crear uno como método de extensión.  Para obtener un ejemplo de cómo crear un método `Add` como método de extensión para una colección, vea [Cómo: Crear un método de extensión Add usado por un inicializador de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md).  Para obtener un ejemplo de cómo crear una colección personalizada que se pueda usar con un inicializador de colección, vea [Cómo: Crear una colección usada por un inicializador de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md).  
  
## Anidar inicializadores de colección  
 Se pueden anidar los valores en un inicializador de colección para identificar una sobrecarga específica de un método `Add` para la colección que se va a crear.  Los valores pasados al método `Add` deben estar separados por comas y encerrarse entre llaves \(`{}`\), tal y como se haría en un literal de matriz o un inicializador de colección.  
  
 Al crear una colección con valores anidados, cada uno de los elementos de la lista de valores anidados se pasa como argumento al método `Add` que coincide con los tipos de elemento.  Así, en el ejemplo de código siguiente se crea un objeto <xref:System.Collections.Generic.Dictionary%602> en el que las claves son de tipo `Integer` y los valores son de tipo `String`.  Cada una de las listas de valores anidados se corresponde con el método <xref:System.Collections.Generic.Dictionary%602.Add%2A> del objeto `Dictionary`.  
  
 [!code-vb[VbVbalrCollectionInitializers#5](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_6.vb)]  
  
 El ejemplo de código anterior es equivalente al código siguiente.  
  
 [!code-vb[VbVbalrCollectionInitializers#6](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_7.vb)]  
  
 Solo las listas de valores anidados del primer nivel de anidamiento se envían al método `Add` para el tipo de colección.  Los niveles más profundos de anidamiento se tratan como literales de matriz y las listas de valores anidados no se corresponden con el método `Add` de ninguna colección.  
  
## Temas relacionados  
  
|||  
|-|-|  
|Título|Descripción|  
|[Cómo: Crear un método de extensión Add usado por un inicializador de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)|Muestra cómo crear un método de extensión denominado `Add` que se puede utilizar para rellenar una colección con los valores de un inicializador de colección.|  
|[Cómo: Crear una colección usada por un inicializador de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)|Muestra cómo habilitar el uso de un inicializador de colección como un método de `Add` en una clase de colección que implementa `IEnumerable`.|  
  
## Vea también  
 [Colecciones](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [New \(Operador\)](../../../../visual-basic/language-reference/operators/new-operator.md)   
 [Propiedades autoimplementadas](../../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)   
 [Cómo: Inicializar una variable de matriz en Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)   
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
---
title: "Tipos an&#243;nimos (Visual Basic) | Microsoft Docs"
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
  - "vb.AnonymousType"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos anónimos [Visual Basic]"
  - "tipos anónimos [Visual Basic], acerca de los tipos anónimos"
  - "tipos [Visual Basic], anónimos"
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
caps.latest.revision: 46
caps.handback.revision: 46
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Tipos an&#243;nimos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Visual Basic admite tipos anónimos, que permiten crear objetos sin escribir ninguna definición de clase para el tipo de datos.  En su lugar, el compilador genera una clase.  La clase no tiene ningún nombre que se pueda usar, hereda directamente de <xref:System.Object> y contiene las propiedades especificadas al declarar el objeto.  Dado que no se especifica el nombre del tipo de datos, se hace referencia a él como *tipo anónimo*.  
  
 El ejemplo siguiente declara y crea la variable `product` como instancia de un tipo anónimo que tiene dos propiedades, `Name` y `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_1.vb)]  
  
 Una *expresión de consulta* utiliza los tipos anónimos para combinar las columnas de datos seleccionadas por una consulta.  No puede definir el tipo del resultado de antemano, ya que no puede predecir las columnas que podría seleccionar una consulta determinada.  Los tipos anónimos permiten escribir una consulta que selecciona cualquier número de columnas, en cualquier orden.  El compilador crea un tipo de datos que coincide con las propiedades y el orden especificados.  
  
 En los ejemplos siguientes, `products` es una lista de objetos de producto, cada uno de los cuales tiene muchas propiedades.  La variable `namePriceQuery` contiene la definición de una consulta que, cuando se ejecuta, devuelve una colección de instancias de un tipo anónimo con dos propiedades, `Name` y `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#2](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_2.vb)]  
  
 La variable `nameQuantityQuery` contiene la definición de una consulta que, cuando se ejecuta, devuelve una colección de instancias de un tipo anónimo con dos propiedades, `Name` y `OnHand`.  
  
 [!code-vb[VbVbalrAnonymousTypes#3](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_3.vb)]  
  
 Para obtener más información sobre el código creado por el compilador para un tipo anónimo, vea [Definición de tipo anónimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
> [!CAUTION]
>  El compilador genera el nombre del tipo anónimo y quizá cambie de una compilación a otra.  El código no debe usar ni depender del nombre de un tipo anónimo porque el nombre podría cambiar cuando se vuelva a compilar el proyecto.  
  
## Declarar un tipo anónimo  
 La declaración de una instancia de un tipo anónimo utiliza una lista de inicializadores para especificar las propiedades del tipo.  Sólo puede especificar las propiedades al declarar un tipo anónimo, y no otros elementos de clase como métodos o eventos.  En el ejemplo siguiente, `product1` es una instancia de un tipo anónimo que tiene dos propiedades: `Name` y `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#4](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_4.vb)]  
  
 Si designa las propiedades como propiedades de clave, puede utilizarlas con el fin de comparar dos instancias de tipo anónimas para comprobar la igualdad.  Sin embargo, los valores de las propiedades de clave no se pueden cambiar.  Para obtener más información, vea la sección Propiedades de clave más adelante en este tema.  
  
 Observe que declarar una instancia de un tipo anónimo es como declarar una instancia de un tipo con nombre utilizando un inicializador de objeto:  
  
 [!code-vb[VbVbalrAnonymousTypes#5](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_5.vb)]  
  
 Para obtener más información sobre otras maneras de especificar las propiedades de tipos anónimos, vea [Cómo: Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## Propiedades principales  
 Las propiedades de clave difieren de las propiedades no lo son de varias maneras básicas:  
  
-   Sólo los valores de las propiedades de clave se comparan para determinar si dos instancias son iguales.  
  
-   Los valores de las propiedades de clave son de sólo lectura y no se pueden cambiar.  
  
-   Solo los valores de propiedad de clave se incluyen en el algoritmo del código hash generado por compilador para un tipo anónimo.  
  
### Igualdad  
 Las instancias de tipos anónimos sólo pueden ser iguales si son instancias del mismo tipo anónimo.  El compilador trata las dos instancias como instancias del mismo tipo si cumplen las condiciones siguientes:  
  
-   Se declaran en el mismo ensamblado.  
  
-   Sus propiedades tienen los mismos nombres, los mismos tipos deducidos y se declaran en el mismo orden.  Las comparaciones de nombres no distinguen mayúsculas de minúsculas.  
  
-   Las mismas propiedades de cada una se marcan como propiedades de clave.  
  
-   Por lo menos una propiedad de cada declaración es una propiedad de clave.  
  
 Una instancia de un tipo anónimo que no tiene ninguna propiedad de clave sólo es igual a sí misma.  
  
 [!code-vb[VbVbalrAnonymousTypes#6](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_6.vb)]  
  
 Dos instancias del mismo tipo anónimo son iguales si los valores de sus propiedades de clave son iguales.  Los ejemplos siguientes muestran cómo se comprueba la igualdad.  
  
 [!code-vb[VbVbalrAnonymousTypes#7](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_7.vb)]  
  
### Valores de sólo lectura  
 Los valores de las propiedades de clave no se pueden cambiar.  Por ejemplo, en `prod8` del ejemplo anterior, los campos `Name` y `Price` son `read-only`, pero `OnHand` se puede cambiar.  
  
 [!code-vb[VbVbalrAnonymousTypes#8](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_8.vb)]  
  
## Tipos anónimos a partir de expresiones de consulta  
 Las expresiones de consulta no siempre requieren la creación de tipos anónimos.  Siempre que es posible, utilizan un tipo existente para contener los datos de la columna.  Esto se produce cuando la consulta devuelve los registros completos desde el origen de datos o sólo un campo de cada registro.  En los ejemplos de código siguientes, `customers` es una colección de objetos de una clase `Customer`.  La clase tiene muchas propiedades y puede incluir una o más en el resultado de la consulta, en cualquier orden.  En los dos primeros ejemplos, no se requiere ningún tipo anónimo porque las consultas seleccionan los elementos de tipos con nombre:  
  
-   `custs1` contiene una colección de cadenas, porque `cust.Name` es una cadena.  
  
     [!code-vb[VbVbalrAnonymousTypes#30](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_9.vb)]  
  
-   `custs2` contiene una colección de objetos `Customer`, porque cada elemento de `customers` es un objeto `Customer` y la consulta selecciona el elemento completo.  
  
     [!code-vb[VbVbalrAnonymousTypes#31](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_10.vb)]  
  
 Sin embargo, los tipos con nombre adecuados no siempre están disponibles.  Quizá desee seleccionar nombres y direcciones de clientes con una finalidad, números de identificador y ubicaciones de clientes con otra y nombres, direcciones e historiales de pedidos de clientes con una tercera.  Los tipos anónimos permiten seleccionar cualquier combinación de propiedades, en cualquier orden, sin declarar primero un nuevo tipo con nombre para contener el resultado.  En su lugar, el compilador crea un tipo anónimo para cada compilación de propiedades.  La consulta siguiente sólo selecciona el número de identificación del cliente desde cada objeto `Customer` de `customers`.  Por consiguiente, el compilador crea un tipo anónimo que contiene sólo esas dos propiedades.  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_11.vb)]  
  
 Tanto los nombres como los tipos de datos de las propiedades del tipo anónimo se toman de los argumentos de `Select`, `cust.Name` y `cust.ID`.  Las propiedades de un tipo anónimo creado por una consulta siempre son las propiedades de clave.  Cuando `custs3` se ejecuta en el bucle `For Each` siguiente, el resultado es una colección de instancias de un tipo anónimo con dos propiedades de clave, `Name` e `ID`.  
  
 [!code-vb[VbVbalrAnonymousTypes#33](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_12.vb)]  
  
 Los elementos de la colección representada por `custs3` están fuertemente tipados y se puede utilizar IntelliSense para navegar por las propiedades disponibles y comprobar sus tipos.  
  
 Para obtener más información, vea [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## Decidir si se usan tipos anónimos  
 Antes de crear un objeto como instancia de una clase anónima, tenga en cuenta si es la mejor opción.  Por ejemplo, si desea crear un objeto temporal para que contenga datos relacionados y no necesita el resto de los campos o métodos que pudiera contener una clase completa, un tipo anónimo es una buena solución.  Los tipos anónimos también son adecuados si desea una selección diferente de propiedades para cada declaración o si desea cambiar el orden de las propiedades.  Sin embargo, si el proyecto incluye varios objetos con las mismas propiedades, en un orden fijo, puede declararlas más fácilmente utilizando un tipo con nombre con un constructor de clase.  Por ejemplo, con un constructor adecuado es más fácil declarar varias instancias de una clase `Product` que declarar varias instancias de un tipo anónimo.  
  
 [!code-vb[VbVbalrAnonymousTypes#9](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_13.vb)]  
  
 Otra ventaja de los tipos con nombre es que el compilador puede detectar un error ortográfico accidental del nombre de una propiedad.  En los ejemplos anteriores, la finalidad de `firstProd2`, `secondProd2` y `thirdProd2` es ser instancias del mismo tipo anónimo.  Sin embargo, si fuera a declarar accidentalmente `thirdProd2` de una de las siguientes formas, su tipo sería diferente del de `firstProd2` y `secondProd2`.  
  
 [!code-vb[VbVbalrAnonymousTypes#10](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_14.vb)]  
  
 Mucho más importante es que existen limitaciones de uso de los tipos anónimos que no se aplican a las instancias de tipos con nombre.  `firstProd2`, `secondProd2` y `thirdProd2` son instancias del mismo tipo anónimo.  Sin embargo, el nombre del tipo anónimo compartido no está disponible y no puede aparecer en los lugares donde se espera un nombre de tipo en el código.  Por ejemplo, un tipo anónimo no se puede utilizar para definir una firma de método, declarar otra variable o campo ni en ninguna declaración de tipos.  Como resultado, los tipos anónimos no son adecuados cuando los métodos deben compartir información.  
  
## Definición de tipo anónimo  
 En respuesta a la declaración de una instancia de un tipo anónimo, el compilador crea una nueva definición de clase que contiene las propiedades especificadas.  
  
 Si el tipo anónimo contiene al menos una propiedad de clave, la definición invalida tres miembros heredados de <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A> y <xref:System.Object.ToString%2A>.  El código generado para comprobar la igualdad y determinar el valor de código hash tiene en cuenta sólo las propiedades de clave.  Si el tipo anónimo no contiene ninguna propiedad de clave, sólo se invalida <xref:System.Object.ToString%2A>.  Explícitamente las propiedades con nombre de un tipo anónimo no pueden estar en conflicto con estos métodos generados.  Es decir, no puede utilizar `.Equals`, `.GetHashCode`ni `.ToString` para asignar un nombre a una propiedad.  
  
 Las definiciones de tipo anónimas que tienen por lo menos una propiedad de clave también implementan la interfaz <xref:System.IEquatable%601?displayProperty=fullName>, donde `T` es el tipo del tipo anónimo.  
  
 Para obtener más información sobre el código creado por el compilador y la funcionalidad de los métodos invalidados, vea [Definición de tipo anónimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
## Vea también  
 [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Cómo: Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [Definición de tipo anónimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)   
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)
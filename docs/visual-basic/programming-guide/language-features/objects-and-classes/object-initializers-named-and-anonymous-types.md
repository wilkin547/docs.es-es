---
title: "Inicializadores de objeto: Tipos con nombre y an&#243;nimos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ObjectInitializer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos anónimos [Visual Basic], inicializadores de objeto"
  - "inicializadores [Visual Basic]"
  - "inicializar propiedades [Visual Basic]"
  - "tipos con nombre [Visual Basic]"
  - "inicializadores de objeto [Visual Basic]"
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Inicializadores de objeto: Tipos con nombre y an&#243;nimos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Los inicializadores de objeto permiten especificar las propiedades de un objeto complejo mediante una sola expresión.  Se pueden usar para crear instancias de tipos con nombre y tipos anónimos.  
  
## Declaraciones  
 Las declaraciones de instancias de tipos con nombre y anónimos pueden parecer casi idénticas, pero su aplicación no es la misma.  Cada categoría tiene funcionalidades y restricciones propias.  El ejemplo siguiente muestra una forma adecuada de declarar e inicializar una instancia de una clase con nombre, `Customer`, mediante un lista de inicializadores de objeto.  Observe que el nombre de la clase se especifica después de la palabra clave `New`.  
  
 [!code-vb[VbVbalrObjectInit#1](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]  
  
 Un tipo anónimo no tiene ningún nombre que se pueda usar.  Por consiguiente, una creación de instancias de un tipo anónimo no puede incluir un nombre de clase.  
  
 [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
 Los requisitos y resultados de las dos declaraciones no son los mismos.  En `namedCust`, ya debe existir una clase `Customer` con una propiedad `Name` y la declaración crea una instancia de la clase.  En `anonymousCust`, el compilador define una nueva clase que tiene una propiedad, una cadena denominada `Name` y crea una nueva instancia de esa clase.  
  
## Tipos con nombre  
 Los inicializadores de objeto proporcionan una forma sencilla de llamar al constructor de un tipo y, a continuación, establecer los valores de algunas o de todas las propiedades en una sola instrucción.  El compilador invoca al constructor adecuado de la instrucción: el constructor predeterminado si no hay argumentos o un constructor con parámetros si se envían uno o más argumentos.  Después, se inicializan las propiedades especificadas en el orden en que aparecen en la lista de inicializadores.  
  
 Cada inicialización de la lista de inicializadores está formada por la asignación de un valor inicial a un miembro de la clase.  Se determinan los nombres y los tipos de datos de los miembros cuando se define la clase.  En los ejemplos siguientes, la clase `Customer` debe existir y debe tener miembros denominados `Name` y `City` que pueden aceptar valores de cadena.  
  
 [!code-vb[VbVbalrObjectInit#3](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]  
  
 O bien, puede obtener el mismo resultado utilizando el código siguiente:  
  
 [!code-vb[VbVbalrObjectInit#4](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]  
  
 Cada una de estas declaraciones es equivalente al siguiente ejemplo, que crea un objeto `Customer` mediante el constructor predeterminado y, a continuación, especifica los valores iniciales de las propiedades `Name` y `City` mediante el uso de una instrucción `With`.  
  
 [!code-vb[VbVbalrObjectInit#5](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]  
  
 Si la clase `Customer` contiene un constructor con parámetros que permita enviar un valor de `Name`, por ejemplo, también puede declarar e inicializar un objeto `Customer` de las siguientes formas:  
  
 [!code-vb[VbVbalrObjectInit#6](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]  
  
 No debe inicializar todas las propiedades, como muestra el código siguiente.  
  
 [!code-vb[VbVbalrObjectInit#7](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]  
  
 Sin embargo, la lista de inicializaciones no puede estar vacía.  Las propiedades sin inicializar conservan sus valores predeterminados.  
  
### Inferencia de tipo con tipos con nombre  
 Puede acortar el código de la declaración de `cust1` combinando los inicializadores de objeto y la inferencia de tipo de variable local.  De esta forma, puede pasar por alto la cláusula `As` en la declaración de variable.  El tipo de datos de la variable se deduce del tipo del objeto que se crea mediante la asignación.  En el ejemplo siguiente, el tipo de `cust6` es `Customer`.  
  
 [!code-vb[VbVbalrObjectInit#8](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]  
  
### Comentarios sobre los tipos con nombre  
  
-   Un miembro de clase sólo se puede inicializar una vez en la lista de inicializadores de objeto.  La declaración de `cust7` provoca un error.  
  
     [!code-vb[VbVbalrObjectInit#9](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]  
  
-   Un miembro se puede usar para inicializarse a sí mismo o a otro campo.  Si se tiene acceso a un miembro antes de haberse inicializado, como ocurre en la declaración siguiente de `cust8`, se usará el valor predeterminado.  Recuerde que cuando se procesa una declaración con un inicializador de objeto, lo primero que ocurre es que se invoca el constructor adecuado.  Después, se inicializan los campos individuales de la lista de inicializadores.  En los ejemplos siguientes, el valor predeterminado de `Name` se asigna para `cust8` y se asigna un valor inicializado de `cust9`.  
  
     [!code-vb[VbVbalrObjectInit#10](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]  
  
     El ejemplo siguiente utiliza el constructor con parámetros de `cust3` y `cust4` para declarar e inicializar `cust10` y `cust11`.  
  
     [!code-vb[VbVbalrObjectInit#11](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]  
  
-   Los inicializadores de objeto pueden estar anidados.  En el ejemplo siguiente, `AddressClass` es una clase que tiene dos propiedades, `City` y `State`, y la clase `Customer` tiene una propiedad `Address` que es una instancia de `AddressClass`.  
  
     [!code-vb[VbVbalrObjectInit#12](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]  
  
-   La lista de inicializaciones no puede estar vacía.  
  
-   La instancia que se inicializa no puede ser de tipo Object.  
  
-   Los miembros de clase que se inicializan no pueden ser miembros compartidos, miembros de sólo lectura, constantes ni llamadas a métodos.  
  
-   Los miembros de clase que se inicializan no se pueden indizar ni calificar.  Los ejemplos siguientes provocan errores del compilador:  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## Tipos anónimos  
 Los tipos anónimos usan inicializadores de objetos para crear instancias de tipos nuevos que el usuario no define ni a los que les asigna nombres explícitamente.  En su lugar, el compilador genera un tipo según las propiedades designadas en la lista de inicializadores de objeto.  Puesto que no se especifica el nombre del tipo, se hace referencia a él como *tipo anónimo*.  Por ejemplo, compare la declaración siguiente con la anterior de `cust6`.  
  
 [!code-vb[VbVbalrObjectInit#13](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]  
  
 La única diferencia sintácticamente es que no se especifica ningún nombre detrás de `New` para el tipo de datos.  Sin embargo, lo que ocurre es muy diferente.  El compilador define un nuevo tipo anónimo con dos propiedades, `Name` y `City`, y crea una instancia de él con los valores especificados.  La inferencia de tipo determina los tipos de `Name` y `City` del ejemplo para que sean cadenas.  
  
> [!CAUTION]
>  El compilador genera el nombre del tipo anónimo y quizá cambie de una compilación a otra.  El código no debe usar el nombre de un tipo anónimo ni depender de él.  
  
 Dado que el nombre del tipo no está disponible, no puede utilizar una cláusula `As` para declarar `cust13`.  Se debe deducir su tipo.  Si no se usa el enlace en tiempo de ejecución, se limita el uso de tipos anónimos en variables locales.  
  
 Los tipos anónimos proporcionan la compatibilidad crítica de las consultas [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  Para obtener más información sobre el uso de tipos anónimos en consultas, vea [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) e [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
### Comentarios sobre tipos anónimos  
  
-   Normalmente, todas o la mayoría de las propiedades de una declaración de tipos anónimos serán propiedades de clave, lo que se indica escribiendo la palabra clave `Key` delante del nombre de la propiedad.  
  
     [!code-vb[VbVbalrObjectInit#14](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]  
  
     Para obtener más información sobre propiedades de clave, vea [Key](../../../../visual-basic/language-reference/modifiers/key.md).  
  
-   Como ocurre con los tipos con nombre, las listas de inicializadores de las definiciones de tipo anónimo debe declarar al menos una propiedad.  
  
     [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
-   Cuando se declara una instancia de un tipo anónimo, el compilador genera una definición de tipo anónimo coincidente.  Los nombres y tipos de datos de las propiedades se toman de la declaración de la instancia y el compilador los incluye en la definición.  A las propiedades no se les asigna nombre ni se definen de antemano, como ocurriría con un tipo con nombre.  Se deducen sus tipos.  No puede especificar los tipos de datos de las propiedades utilizando una cláusula `As`.  
  
-   Los tipos anónimos también pueden establecer los nombres y valores de sus propiedades de otras maneras distintas.  Por ejemplo, una propiedad de tipo anónimo puede tomar tanto el nombre como el valor de una variable o el nombre y valor de una propiedad de otro objeto.  
  
     [!code-vb[VbVbalrObjectInit#15](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]  
  
     Para obtener más información sobre las opciones para definir propiedades de tipos anónimos, vea [Cómo: Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## Vea también  
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Cómo: Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)   
 [Cómo: Declarar un objeto usando un inicializador de objeto](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
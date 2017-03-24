---
title: "Inicializadores de objeto: Con nombre y anónimos tipos (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ObjectInitializer
dev_langs:
- VB
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
caps.latest.revision: 27
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d684ad4f3dd47dc7400ea401a94660af832ef866
ms.lasthandoff: 03/13/2017

---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>Inicializadores de objeto: Tipos con nombre y anónimos (Visual Basic)
Inicializadores de objeto permiten especificar las propiedades de un objeto complejo mediante una sola expresión. Que pueden utilizarse para crear instancias de tipos con nombre y de tipos anónimos.  
  
## <a name="declarations"></a>Declaraciones  
 Las declaraciones de instancias de tipos con nombre y anónimos pueden parecer casi idénticas, pero sus efectos no son iguales. Cada categoría tiene funcionalidades y restricciones propias. En el ejemplo siguiente se muestra una manera conveniente de declarar e inicializar una instancia de una clase con nombre, `Customer`, mediante el uso de una lista de inicializadores de objeto. Observe que el nombre de la clase se especifica después de la palabra clave `New`.  
  
 [!code-vb[1 VbVbalrObjectInit](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]  
  
 Un tipo anónimo no tiene ningún nombre utilizable. Por lo tanto, una instancia de un tipo anónimo no puede incluir un nombre de clase.  
  
 [!code-vb[VbVbalrObjectInit&#2;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
 Los requisitos y los resultados de las dos declaraciones no son iguales. Para `namedCust`, `Customer` clase que tiene un `Name` propiedad ya debe existir y la declaración crea una instancia de esa clase. Para `anonymousCust`, el compilador define una nueva clase que tiene una propiedad, una cadena denominada `Name`y crea una nueva instancia de esa clase.  
  
## <a name="named-types"></a>Tipos con nombre  
 Inicializadores de objeto proporcionan una manera sencilla de llamar al constructor de un tipo y, a continuación, establezca los valores de algunas o todas las propiedades en una única instrucción. El compilador invoca al constructor adecuado de la instrucción: el constructor predeterminado si no hay argumentos o un constructor con parámetros si se envían uno o más argumentos. Después, se inicializan las propiedades especificadas en el orden en que se presentan en la lista de inicializadores.  
  
 Cada inicialización de la lista de inicializadores está formada por la asignación de un valor inicial a un miembro de la clase. Los nombres y tipos de datos de los miembros se determinan cuando se define la clase. En los ejemplos siguientes, el `Customer` clase debe existir y deben tienen miembros con nombre `Name` y `City` que puede aceptar valores de cadena.  
  
 [!code-vb[VbVbalrObjectInit&3;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]  
  
 Como alternativa, puede obtener el mismo resultado utilizando el código siguiente:  
  
 [!code-vb[VbVbalrObjectInit Nº&4;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]  
  
 Cada una de estas declaraciones es equivalente al ejemplo siguiente se crea un `Customer` de objetos mediante el constructor predeterminado y, a continuación, especifica los valores iniciales de la `Name` y `City` propiedades mediante el uso de un `With` instrucción.  
  
 [!code-vb[VbVbalrObjectInit&#5;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]  
  
 Si el `Customer` clase contiene un constructor con parámetros que le permite enviar un valor para `Name`, por ejemplo, también puede declarar e inicializar un `Customer` objeto de las maneras siguientes:  
  
 [!code-vb[VbVbalrObjectInit Nº&6;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]  
  
 No es necesario inicializar todas las propiedades, como se muestra en el código siguiente.  
  
 [!code-vb[VbVbalrObjectInit&#7;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]  
  
 Sin embargo, la lista de inicializaciones no puede estar vacía. Las propiedades sin inicializar conservan sus valores predeterminados.  
  
### <a name="type-inference-with-named-types"></a>Inferencia de tipo con tipos con nombre  
 Puede reducir el código para la declaración de `cust1` combinando los inicializadores de objeto y la inferencia de tipo local. Esto permite omitir el `As` cláusula en la declaración de variable. El tipo de datos de la variable se deduce del tipo del objeto que se crea la asignación. En el ejemplo siguiente, el tipo de `cust6` es `Customer`.  
  
 [!code-vb[VbVbalrObjectInit Nº&8;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]  
  
### <a name="remarks-about-named-types"></a>Comentarios acerca de los tipos con nombre  
  
-   Un miembro de clase no se puede inicializar más de una vez en la lista de inicializadores de objeto. La declaración de `cust7` se produce un error.  
  
     [!code-vb[VbVbalrObjectInit&#9;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]  
  
-   Un miembro puede utilizarse para inicializar u otro campo. Si se tiene acceso a un miembro antes de que se ha inicializado, como se muestra en la siguiente declaración para `cust8`, se usará el valor predeterminado. Recuerde que cuando se procesa una declaración que usa a un inicializador de objeto, lo primero que ocurre es que se invoca el constructor correspondiente. Después, se inicializan los campos individuales de la lista de inicializadores. En los ejemplos siguientes, el valor predeterminado para `Name` se asigna para `cust8`, y se asigna un valor inicializado en `cust9`.  
  
     [!code-vb[VbVbalrObjectInit&#10;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]  
  
     En el ejemplo siguiente se utiliza el constructor parametrizado de `cust3` y `cust4` para declarar e inicializar `cust10` y `cust11`.  
  
     [!code-vb[VbVbalrObjectInit&#11;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]  
  
-   Inicializadores de objeto pueden anidarse. En el ejemplo siguiente, `AddressClass` es una clase que tiene dos propiedades, `City` y `State`y el `Customer` clase tiene un `Address` propiedad que es una instancia de `AddressClass`.  
  
     [!code-vb[VbVbalrObjectInit&#12;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]  
  
-   La lista de inicializaciones no puede estar vacía.  
  
-   La instancia que se está inicializarla no puede ser de tipo Object.  
  
-   No pueden ser miembros de clase que se inicializan los miembros compartidos, miembros de sólo lectura, constantes o llamadas a métodos.  
  
-   Miembros de clase que se inicializan no completo o indizados. Los ejemplos siguientes provocan errores del compilador:  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>Tipos anónimos  
 Tipos anónimos utilizan a inicializadores de objeto para crear instancias de los nuevos tipos que no se define explícitamente y nombre. En su lugar, el compilador genera un tipo según las propiedades designadas en la lista de inicializadores de objeto. Dado que no se especifica el nombre del tipo, se conoce como un *tipo anónimo*. Por ejemplo, compare la declaración siguiente a la anterior para `cust6`.  
  
 [!code-vb[VbVbalrObjectInit&#13;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]  
  
 La única diferencia sintácticamente es que no se especifica nombre después de `New` para el tipo de datos. Sin embargo, lo que sucede es bastante diferente. El compilador define un nuevo tipo anónimo con dos propiedades `Name` y `City`y crea una instancia de él con los valores especificados. Inferencia de tipo determina los tipos de `Name` y `City` en el ejemplo de cadenas.  
  
> [!CAUTION]
>  El nombre del tipo anónimo es generado por el compilador y puede variar de una compilación a otra. El código no debe utilizar o se basan en el nombre de un tipo anónimo.  
  
 Dado que el nombre del tipo no está disponible, puede usar un `As` cláusula declarar `cust13`. Debe deducir su tipo. Sin utilizar el enlace, se limita el uso de tipos anónimos a variables locales.  
  
 Los tipos anónimos proporcionan la compatibilidad crítica para [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consultas. Para obtener más información sobre el uso de tipos anónimos en consultas, consulte [tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) y [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
### <a name="remarks-about-anonymous-types"></a>Comentarios sobre tipos anónimos  
  
-   Normalmente, todas o la mayoría de las propiedades de una declaración de tipos anónimos serán propiedades de clave, que se indican escribiendo la palabra clave `Key` delante del nombre de propiedad.  
  
     [!code-vb[VbVbalrObjectInit&#14;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]  
  
     Para obtener más información sobre propiedades de clave, consulte [clave](../../../../visual-basic/language-reference/modifiers/key.md).  
  
-   Denominado como tipos de listas de inicializadores de las definiciones de tipo anónimo deben declarar al menos una propiedad.  
  
     [!code-vb[VbVbalrObjectInit&#2;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
-   Cuando se declara una instancia de un tipo anónimo, el compilador genera una definición de tipo anónimo coincidente. Los nombres y tipos de datos de las propiedades se toman de la declaración de instancia y se incluyen el compilador en la definición. Las propiedades no son denominadas y definir por adelantado, como se haría para un tipo con nombre. Se deducen sus tipos. No se puede especificar los tipos de datos de las propiedades mediante un `As` cláusula.  
  
-   Tipos anónimos también pueden establecer los valores de sus propiedades y nombres de otras maneras. Por ejemplo, una propiedad de tipo anónimo puede tomar el nombre y el valor de una variable, o el nombre y valor de una propiedad de otro objeto.  
  
     [!code-vb[VbVbalrObjectInit&#15;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]  
  
     Para obtener más información acerca de las opciones para definir propiedades en tipos anónimos, vea [Cómo: deducir los nombres de propiedad y los tipos en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="see-also"></a>Vea también  
 [Inferencia de tipo local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Cómo: deducir tipos y nombres de propiedad en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [Clave](../../../../visual-basic/language-reference/modifiers/key.md)   
 [Declarar un objeto usando un inicializador de objeto](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)

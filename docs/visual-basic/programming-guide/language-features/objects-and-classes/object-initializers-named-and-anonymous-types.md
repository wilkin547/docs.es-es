---
title: 'Inicializadores de objeto: Tipos con nombre y anónimos (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.ObjectInitializer
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
ms.openlocfilehash: e1f461cc98fb104f78a6c83a207cff7f4eda9227
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046462"
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>Inicializadores de objeto: Tipos con nombre y anónimos (Visual Basic)
Los inicializadores de objeto permiten especificar propiedades para un objeto complejo mediante el uso de una sola expresión. Se pueden usar para crear instancias de tipos con nombre y de tipos anónimos.  
  
## <a name="declarations"></a>Declaraciones  
 Las declaraciones de instancias de tipos con nombre y anónimos pueden ser prácticamente idénticas, pero sus efectos no son los mismos. Cada categoría tiene capacidades y restricciones propias. En el ejemplo siguiente se muestra una manera cómoda de declarar e inicializar una instancia de una `Customer`clase con nombre,, mediante una lista de inicializadores de objeto. Observe que el nombre de la clase se especifica después de la `New`palabra clave.  
  
 [!code-vb[VbVbalrObjectInit#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#1)]  
  
 Un tipo anónimo no tiene ningún nombre utilizable. Por lo tanto, una creación de instancias de un tipo anónimo no puede incluir un nombre de clase.  
  
 [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
 Los requisitos y los resultados de las dos declaraciones no son los mismos. Para `namedCust`, una `Customer` clase que tiene una `Name` propiedad ya debe existir y la declaración crea una instancia de esa clase. Para `anonymousCust`, el compilador define una nueva clase que tiene una propiedad, una `Name`cadena denominada y crea una nueva instancia de esa clase.  
  
## <a name="named-types"></a>Tipos con nombre  
 Los inicializadores de objeto proporcionan una manera sencilla de llamar al constructor de un tipo y, a continuación, establecer los valores de algunas o todas las propiedades en una única instrucción. El compilador invoca el constructor adecuado para la instrucción: el constructor sin parámetros si no se presentan argumentos, o un constructor con parámetros si se envían uno o más argumentos. Después, las propiedades especificadas se inicializan en el orden en que se presentan en la lista de inicializadores.  
  
 Cada inicialización en la lista de inicializadores consta de la asignación de un valor inicial a un miembro de la clase. Los nombres y los tipos de datos de los miembros se determinan cuando se define la clase. En los ejemplos siguientes, la `Customer` clase debe existir y debe tener miembros denominados `Name` y `City` que puedan aceptar valores de cadena.  
  
 [!code-vb[VbVbalrObjectInit#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#3)]  
  
 Como alternativa, puede obtener el mismo resultado mediante el código siguiente:  
  
 [!code-vb[VbVbalrObjectInit#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#4)]  
  
 Cada una de estas declaraciones es equivalente al ejemplo siguiente, que crea un `Customer` objeto mediante el constructor sin parámetros y, a continuación, especifica los valores iniciales de las `City` `Name` propiedades y mediante un `With` privacidad.  
  
 [!code-vb[VbVbalrObjectInit#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#5)]  
  
 Si la `Customer` clase contiene un constructor con parámetros que le permite enviar un valor para `Name`, por ejemplo, también puede declarar e inicializar un `Customer` objeto de las maneras siguientes:  
  
 [!code-vb[VbVbalrObjectInit#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#6)]  
  
 No es necesario inicializar todas las propiedades, como se muestra en el código siguiente.  
  
 [!code-vb[VbVbalrObjectInit#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#7)]  
  
 Sin embargo, la lista de inicialización no puede estar vacía. Las propiedades sin inicializar conservan sus valores predeterminados.  
  
### <a name="type-inference-with-named-types"></a>Inferencia de tipos con tipos con nombre  
 Puede acortar el código para la declaración de `cust1` combinando los inicializadores de objeto y la inferencia de tipo local. Esto le permite omitir la `As` cláusula en la declaración de variable. El tipo de datos de la variable se deduce del tipo del objeto creado por la asignación. En el ejemplo siguiente, el tipo de `cust6` es `Customer`.  
  
 [!code-vb[VbVbalrObjectInit#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#8)]  
  
### <a name="remarks-about-named-types"></a>Comentarios acerca de los tipos con nombre  
  
- No se puede inicializar un miembro de clase más de una vez en la lista de inicializadores de objeto. La declaración de `cust7` provoca un error.  
  
     [!code-vb[VbVbalrObjectInit#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#9)]  
  
- Un miembro se puede usar para inicializarse a sí mismo o a otro campo. Si se tiene acceso a un miembro antes de que se haya inicializado, como en la siguiente `cust8`declaración de, se usará el valor predeterminado. Recuerde que cuando se procesa una declaración que usa un inicializador de objeto, lo primero que ocurre es que se invoca el constructor adecuado. Después, se inicializan los campos individuales en la lista de inicializadores. En los ejemplos siguientes, se `Name` `cust8`asigna el valor predeterminado para y se asigna un valor inicializado en `cust9`.  
  
     [!code-vb[VbVbalrObjectInit#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#10)]  
  
     En el ejemplo siguiente se usa el constructor con `cust3` parámetros `cust4` de y para declarar `cust10` e `cust11`inicializar y.  
  
     [!code-vb[VbVbalrObjectInit#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#11)]  
  
- Los inicializadores de objeto se pueden anidar. En el ejemplo siguiente, `AddressClass` es una clase que tiene dos propiedades, `City` y `State`, y la `Customer` clase tiene una `Address` propiedad que es una instancia de `AddressClass`.  
  
     [!code-vb[VbVbalrObjectInit#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#12)]  
  
- La lista de inicialización no puede estar vacía.  
  
- La instancia que se está inicializando no puede ser de tipo Object.  
  
- Los miembros de clase que se van a inicializar no pueden ser miembros compartidos, miembros de solo lectura, constantes o llamadas a métodos.  
  
- Los miembros de clase que se van a inicializar no se pueden indizar ni calificar. En los siguientes ejemplos se producen errores del compilador:  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>Tipos anónimos  
 Los tipos anónimos usan inicializadores de objeto para crear instancias de nuevos tipos que no se definen explícitamente ni se denominan. En su lugar, el compilador genera un tipo de acuerdo con las propiedades que se designan en la lista de inicializadores de objeto. Dado que no se especifica el nombre del tipo, se hace referencia a él como un *tipo anónimo*. Por ejemplo, compare la siguiente declaración con la anterior para `cust6`.  
  
 [!code-vb[VbVbalrObjectInit#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#13)]  
  
 La única diferencia sintácticamente es que no se especifica ningún `New` nombre después del tipo de datos. Sin embargo, lo que sucede es bastante diferente. El compilador define un nuevo tipo anónimo que tiene dos `Name` propiedades `City`, y, y crea una instancia de ella con los valores especificados. La inferencia de tipos determina los `Name` tipos `City` de y en el ejemplo que son cadenas.  
  
> [!CAUTION]
> El compilador genera el nombre del tipo anónimo y puede variar de la compilación a la compilación. El código no debe utilizar ni basarse en el nombre de un tipo anónimo.  
  
 Dado que el nombre del tipo no está disponible, no se puede usar `As` una cláusula para `cust13`declarar. Se debe inferir su tipo. Sin usar el enlace en tiempo de ejecución, esto limita el uso de tipos anónimos a variables locales.  
  
 Los tipos anónimos proporcionan compatibilidad [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] crítica con las consultas. Para obtener más información sobre el uso de tipos anónimos en las consultas, vea [tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) e [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
### <a name="remarks-about-anonymous-types"></a>Comentarios acerca de los tipos anónimos  
  
- Normalmente, todas o la mayoría de las propiedades de una declaración de tipo anónimo serán propiedades de clave, que se indican escribiendo la `Key` palabra clave delante del nombre de la propiedad.  
  
     [!code-vb[VbVbalrObjectInit#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#14)]  
  
     Para obtener más información acerca de las propiedades de clave, consulte [key](../../../../visual-basic/language-reference/modifiers/key.md).  
  
- Al igual que los tipos con nombre, las listas de inicializadores para definiciones de tipos anónimos deben declarar al menos una propiedad.  
  
     [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
- Cuando se declara una instancia de un tipo anónimo, el compilador genera una definición de tipo anónimo coincidente. Los nombres y los tipos de datos de las propiedades se toman de la declaración de instancia y se incluyen en el compilador en la definición. Las propiedades no tienen nombre y se definen de antemano, como serían para un tipo con nombre. Se deducen sus tipos. No se pueden especificar los tipos de datos de las propiedades mediante `As` el uso de una cláusula.  
  
- Los tipos anónimos también pueden establecer los nombres y valores de sus propiedades de varias maneras. Por ejemplo, una propiedad de tipo anónimo puede tomar el nombre y el valor de una variable, o el nombre y el valor de una propiedad de otro objeto.  
  
     [!code-vb[VbVbalrObjectInit#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#15)]  
  
     Para obtener más información sobre las opciones para definir propiedades en tipos anónimos [, consulte How to: Inferir nombres y tipos de propiedades en declaraciones](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)de tipos anónimos.  
  
## <a name="see-also"></a>Vea también

- [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Cómo: Inferir nombres y tipos de propiedades en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Key](../../../../visual-basic/language-reference/modifiers/key.md)
- [Procedimientos: Declarar un objeto usando un inicializador de objeto](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)

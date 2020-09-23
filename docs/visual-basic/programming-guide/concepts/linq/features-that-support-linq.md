---
title: Características compatibles con LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: bd63cd36c1f85fd89349293a71ecc5b281165380
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078311"
---
# <a name="visual-basic-features-that-support-linq"></a>Características de Visual Basic que admiten LINQ

El nombre Language-Integrated Query (LINQ) hace referencia a la tecnología de Visual Basic que admite la sintaxis de consulta y otras construcciones de lenguaje directamente en el lenguaje. Con LINQ, no tiene que aprender un nuevo lenguaje para realizar consultas en un origen de datos externo. Puede realizar consultas en los datos de bases de datos relacionales, almacenes XML u objetos mediante Visual Basic. Esta integración de funcionalidades de consulta en el lenguaje habilita la comprobación en tiempo de compilación para detectar errores de sintaxis y seguridad de tipos. Esta integración también garantiza que ya conoce la mayor parte de lo que tiene que saber para escribir consultas enriquecidas y variadas en Visual Basic.  
  
 En las secciones siguientes se describen las construcciones del lenguaje que admiten LINQ con suficiente detalle para que pueda empezar a leer la documentación introductoria, ejemplos de código y aplicaciones de ejemplo. También puede hacer clic en los vínculos para buscar explicaciones más detalladas sobre cómo se unen las características del lenguaje para habilitar la consulta integrada en el lenguaje. Un buen punto de partida es [Tutorial: escribir consultas en Visual Basic](walkthrough-writing-queries.md).  
  
## <a name="query-expressions"></a>Expresiones de consulta  

 Las expresiones de consulta de Visual Basic se pueden expresar en una sintaxis declarativa similar a la de SQL o XQuery. En tiempo de compilación, la sintaxis de la consulta se convierte en llamadas de método a la implementación de un proveedor LINQ de los métodos de extensión del operador de consulta estándar. Las aplicaciones controlan qué operadores de consulta estándar se encuentran en el ámbito especificando el espacio de nombres adecuado con una `Imports` instrucción. La sintaxis de una expresión de consulta de Visual Basic tiene el siguiente aspecto:  
  
 [!code-vb[VbLINQVbFeatures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#1)]  
  
 Para más información, vea [Introducción a LINQ en Visual Basic](../../language-features/linq/introduction-to-linq.md).  
  
## <a name="implicitly-typed-variables"></a>Variables con tipo implícito  

 En lugar de especificar explícitamente un tipo al declarar e inicializar una variable, puede permitir que el compilador deduzca y asigne el tipo. Esto se conoce como *inferencia de tipo local*.  
  
 Las variables cuyos tipos se deducen están fuertemente tipadas, al igual que las variables cuyo tipo se especifica explícitamente. La inferencia de tipo local solo funciona cuando se define una variable local dentro de un cuerpo de método. Para obtener más información, vea [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md) e [inferencia de tipo local](../../language-features/variables/local-type-inference.md).  
  
 En el ejemplo siguiente se muestra la inferencia de tipo local. Para usar este ejemplo, debe establecer `Option Infer` en `On` .  
  
 [!code-vb[VbLINQVbFeatures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#2)]  
  
 La inferencia de tipo local también hace posible la creación de tipos anónimos, que se describen más adelante en esta sección y son necesarios para las consultas LINQ.  
  
 En el siguiente ejemplo de LINQ, la inferencia de tipos se produce si `Option Infer` es `On` o `Off` . Se produce un error en tiempo de compilación si `Option Infer` es `Off` y `Option Strict` es `On` .  
  
 [!code-vb[VbLINQVbFeatures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#3)]  
  
## <a name="object-initializers"></a>Inicializadores de objeto  

 Los inicializadores de objeto se usan en expresiones de consulta cuando tiene que crear un tipo anónimo para contener los resultados de una consulta. También se pueden usar para inicializar objetos de tipos con nombre fuera de las consultas. Mediante el uso de un inicializador de objeto, puede inicializar un objeto en una sola línea sin llamar explícitamente a un constructor. Suponiendo que tiene una clase denominada `Customer` que tiene público `Name` y `Phone` propiedades, junto con otras propiedades, se puede usar un inicializador de objeto de esta manera:  
  
 [!code-vb[VbLINQVbFeatures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#4)]  
  
 Para obtener más información, vea [inicializadores de objeto: tipos con nombre y anónimos](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="anonymous-types"></a>Tipos anónimos  

 Los tipos anónimos proporcionan una manera cómoda de agrupar temporalmente un conjunto de propiedades en un elemento que se desea incluir en el resultado de una consulta. Esto le permite elegir cualquier combinación de campos disponibles en la consulta, en cualquier orden, sin definir un tipo de datos con nombre para el elemento.  
  
 El compilador crea dinámicamente un *tipo anónimo* . El compilador asigna el nombre del tipo y puede cambiar con cada nueva compilación. Por lo tanto, el nombre no se puede usar directamente. Los tipos anónimos se inicializan de la siguiente manera:  
  
 [!code-vb[VbLINQVbFeatures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#5)]  
  
 Para obtener más información, vea [Tipos anónimos](../../language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="extension-methods"></a>Métodos de extensión.  

 Los métodos de extensión permiten agregar métodos a un tipo de datos o una interfaz desde fuera de la definición. Esta característica permite, de hecho, agregar nuevos métodos a un tipo existente sin modificar realmente el tipo. Los operadores de consulta estándar son un conjunto de métodos de extensión que proporcionan la funcionalidad de consulta LINQ para cualquier tipo que implemente <xref:System.Collections.Generic.IEnumerable%601> . Otras extensiones para <xref:System.Collections.Generic.IEnumerable%601> incluir <xref:System.Linq.Enumerable.Count%2A> , <xref:System.Linq.Enumerable.Union%2A> y <xref:System.Linq.Enumerable.Intersect%2A> .  
  
 El método de extensión siguiente agrega un método de impresión a la <xref:System.String> clase.  
  
 [!code-vb[VbLINQVbFeatures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#6)]  
  
 Se llama al método como un método de instancia normal de <xref:System.String> :  
  
 [!code-vb[VbLINQVbFeatures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#7)]  
  
 Para obtener más información, vea [Métodos de extensión](../../language-features/procedures/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Expresiones lambda  

 Una expresión lambda es una función sin un nombre que calcula y devuelve un valor único. A diferencia de las funciones con nombre, una expresión lambda se puede definir y ejecutar al mismo tiempo. En el ejemplo siguiente se muestra 4.  
  
 [!code-vb[VbLINQVbFeatures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#8)]  
  
 Puede asignar la definición de la expresión lambda a un nombre de variable y, a continuación, utilizar el nombre para llamar a la función. En el ejemplo siguiente también se muestra 4.  
  
 [!code-vb[VbLINQVbFeatures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#12)]  
  
 En LINQ, las expresiones lambda subyacen a muchos de los operadores de consulta estándar. El compilador crea expresiones lambda para capturar los cálculos definidos en métodos de consulta fundamentales, como `Where` , `Select` , `Order By` , `Take While` y otros.  
  
 Por ejemplo, el código siguiente define una consulta que devuelve todos los estudiantes senior de una lista de estudiantes.  
  
 [!code-vb[VbLINQVbFeatures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#9)]  
  
 La definición de la consulta se compila en código similar al ejemplo siguiente, que usa dos expresiones lambda para especificar los argumentos para `Where` y `Select` .  
  
 [!code-vb[VbLINQVbFeatures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#10)]  
  
 Cualquier versión se puede ejecutar mediante un `For Each` bucle:  
  
 [!code-vb[VbLINQVbFeatures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#11)]  
  
 Para obtener más información, vea [Expresiones lambda](../../language-features/procedures/lambda-expressions.md).  
  
## <a name="see-also"></a>Vea también

- [Language-Integrated Query (LINQ) (Visual Basic)](index.md)
- [Introducción a LINQ en Visual Basic](getting-started-with-linq.md)
- [LINQ y cadenas (Visual Basic)](linq-and-strings.md)
- [Option Infer (instrucción)](../../../language-reference/statements/option-infer-statement.md)
- [Option Strict (instrucción)](../../../language-reference/statements/option-strict-statement.md)

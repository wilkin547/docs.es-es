---
title: Características de Visual Basic que admiten LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: 155d5c36483accc12d066a5530fea20a563e1498
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814502"
---
# <a name="visual-basic-features-that-support-linq"></a>Características de Visual Basic que admiten LINQ
El nombre [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] hace referencia a la tecnología en Visual Basic que admite la sintaxis de consulta y otras construcciones directamente en el lenguaje. Con [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], no es necesario aprender un nuevo lenguaje de consulta en un origen de datos externo. Puede consultar con los datos en bases de datos relacionales, los almacenes XML u objetos mediante Visual Basic. Esta integración de capacidades de consulta en el lenguaje habilita la comprobación de tiempo de compilación para los errores de sintaxis y seguridad de tipos. Esta integración también garantiza que ya conoce la mayoría de lo que tiene que saber para escribir consultas complejas y variadas en Visual Basic.  
  
 Las secciones siguientes describen las construcciones de lenguaje que son compatibles con LINQ en detalle suficiente para que pueda empezar a leer la documentación introductoria, ejemplos de código y aplicaciones de ejemplo. También puede hacer clic en los vínculos para encontrar una explicación más detallada de cómo se reúnen las características del lenguaje para habilitar language integrated query. Es un buen lugar para comenzar [Tutorial: Escribir consultas en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).  
  
## <a name="query-expressions"></a>Expresiones de consulta  
 Las expresiones de consulta en Visual Basic se pueden expresar en una sintaxis declarativa similar a la de SQL o XQuery. En tiempo de compilación, la sintaxis de consulta se convierte en llamadas de método a la implementación de un proveedor LINQ de los métodos de extensión de operador de consulta estándar. Control de aplicaciones que son operadores de consulta estándar en el ámbito mediante la especificación del espacio de nombres adecuado con una `Imports` instrucción. Sintaxis de una expresión de consulta de Visual Basic tiene este aspecto:  
  
 [!code-vb[VbLINQVbFeatures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#1)]  
  
 Para obtener más información, consulte [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="implicitly-typed-variables"></a>Variables con tipo implícito  
 En lugar de especificar explícitamente un tipo al declarar e inicializar una variable, puede permitir que el compilador deduzca y asigne al tipo. Esto se conoce como *inferencia de tipos local*.  
  
 Las variables cuyos tipos se deducen están fuertemente tipadas, al igual que las variables cuyo tipo se especifican explícitamente. Inferencia de tipos local sólo funciona si está definiendo una variable local dentro de un cuerpo de método. Para obtener más información, consulte [instrucción Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) y [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 En el ejemplo siguiente se ilustra la inferencia de tipo local. Para usar este ejemplo, debe establecer `Option Infer` a `On`.  
  
 [!code-vb[VbLINQVbFeatures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#2)]  
  
 Inferencia de tipos local también permite crear tipos anónimos, que se describen más adelante en esta sección y son necesarios para las consultas LINQ.  
  
 En el siguiente ejemplo LINQ, inferencia de tipos se produce si `Option Infer` sea `On` o `Off`. Se produce un error de tiempo de compilación si `Option Infer` es `Off` y `Option Strict` es `On`.  
  
 [!code-vb[VbLINQVbFeatures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#3)]  
  
## <a name="object-initializers"></a>Inicializadores de objeto  
 Los inicializadores de objeto se utilizan en expresiones de consulta cuando tiene que crear un tipo anónimo para contener los resultados de una consulta. También puede usarse para inicializar los objetos de tipos con nombre fuera de las consultas. Mediante el uso de un inicializador de objeto, puede inicializar un objeto en una sola línea sin llamar explícitamente a un constructor. Suponiendo que tiene una clase denominada `Customer` cuya pública `Name` y `Phone` propiedades, junto con otras propiedades, se puede usar un inicializador de objeto de esta manera:  
  
 [!code-vb[VbLINQVbFeatures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#4)]  
  
 Para obtener más información, consulte [inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="anonymous-types"></a>Tipos anónimos  
 Los tipos anónimos son una manera cómoda de agrupar temporalmente un conjunto de propiedades en un elemento que se va a incluir en un resultado de la consulta. Esto le permite elegir cualquier combinación de campos disponibles en la consulta, en cualquier orden, sin definir un tipo de datos con nombre para el elemento.  
  
 Un *tipo anónimo* se construye dinámicamente por el compilador. El nombre del tipo es asignado por el compilador, y podría cambiar con cada nueva compilación. Por lo tanto, el nombre no se puede usar directamente. Tipos anónimos se inicializan en la siguiente manera:  
  
 [!code-vb[VbLINQVbFeatures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#5)]  
  
 Para más información, vea [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="extension-methods"></a>Métodos de extensión.  
 Métodos de extensión permiten agregar métodos a un tipo de datos o la interfaz desde fuera de la definición. Esta característica permite, de hecho, agregar nuevos métodos a un tipo existente sin modificar el tipo. Los operadores de consulta estándar son un conjunto de métodos de extensión que proporcionan [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] funcionalidad de consulta para cualquier tipo que implemente <xref:System.Collections.Generic.IEnumerable%601>. Otras extensiones de <xref:System.Collections.Generic.IEnumerable%601> incluyen <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, y <xref:System.Linq.Enumerable.Intersect%2A>.  
  
 El siguiente método de extensión agrega un método de impresión a la <xref:System.String> clase.  
  
 [!code-vb[VbLINQVbFeatures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#6)]  
  
 Se llama al método como un método de instancia normal de <xref:System.String>:  
  
 [!code-vb[VbLINQVbFeatures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#7)]  
  
 Para obtener más información, vea [Métodos de extensión](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Expresiones lambda  
 Una expresión lambda es una función sin un nombre que se calcula y devuelve un valor único. A diferencia de las funciones con nombre, una expresión lambda se puede definir y ejecutar al mismo tiempo. El ejemplo siguiente muestra 4.  
  
 [!code-vb[VbLINQVbFeatures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#8)]  
  
 Puede asignar la definición de la expresión lambda a un nombre de variable y, a continuación, use el nombre para llamar a la función. El ejemplo siguiente también muestra 4.  
  
 [!code-vb[VbLINQVbFeatures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#12)]  
  
 En [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], las expresiones lambda subyacen a muchos de los operadores de consulta estándar. El compilador crea expresiones lambda para capturar los cálculos que se definen en los métodos de consulta fundamentales como `Where`, `Select`, `Order By`, `Take While`y otros.  
  
 Por ejemplo, el código siguiente define una consulta que devuelve todos los estudiantes senior de una lista de alumnos.  
  
 [!code-vb[VbLINQVbFeatures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#9)]  
  
 La definición de consulta se compila en código similar al ejemplo siguiente, que utiliza dos expresiones lambda para especificar los argumentos para `Where` y `Select`.  
  
 [!code-vb[VbLINQVbFeatures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#10)]  
  
 Una de las versiones se pueden ejecutar mediante el uso de un `For Each` bucle:  
  
 [!code-vb[VbLINQVbFeatures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#11)]  
  
 Para obtener más información, vea [Expresiones lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="see-also"></a>Vea también

- [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [LINQ y cadenas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [Option Infer (instrucción)](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)

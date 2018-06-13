---
title: Características de Visual Basic que admiten LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: db2eff2f7c19a3c510e7b212f5bb406d7a885439
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643905"
---
# <a name="visual-basic-features-that-support-linq"></a>Características de Visual Basic que admiten LINQ
El nombre [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] hace referencia a la tecnología en Visual Basic que admite la sintaxis de consulta y crea otro lenguaje directamente en el idioma. Con [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], no tienes que volver a aprender un nuevo lenguaje de consulta en un origen de datos externo. Puede consultar con los datos de bases de datos relacionales, los almacenes XML u objetos utilizando Visual Basic. Esta integración de capacidades de consulta en el lenguaje habilita la comprobación de tiempo de compilación para errores de sintaxis y seguridad de tipos. Esta integración también garantiza que ya conoce la mayor parte de lo que es preciso conocer para escribir consultas complejas y variadas en Visual Basic.  
  
 Las siguientes secciones describen las construcciones de lenguaje que admiten LINQ en el nivel de detalle suficiente para que pueda empezar a leer la documentación de introducción, ejemplos de código y aplicaciones de ejemplo. También puede hacer clic en los vínculos para obtener una explicación más detallada de cómo las características de lenguaje se unificación para habilitar language integrated query. Es un buen lugar para comenzar [Tutorial: escribir consultas en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).  
  
## <a name="query-expressions"></a>Expresiones de consulta  
 Las expresiones de consulta en Visual Basic se pueden expresar en una sintaxis declarativa similar a la de SQL o XQuery. En tiempo de compilación, la sintaxis de consulta se convierte en llamadas de método a la implementación de un proveedor LINQ de los métodos de extensión de operador de consulta estándar. Control de aplicaciones que son operadores de consulta estándar en el ámbito especificando el espacio de nombres adecuado con una `Imports` instrucción. Sintaxis para una expresión de consulta de Visual Basic tiene el siguiente aspecto:  
  
 [!code-vb[VbLINQVbFeatures#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]  
  
 Para obtener más información, consulte [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="implicitly-typed-variables"></a>Variables con tipo implícito  
 En lugar de especificar explícitamente un tipo al declarar e inicializar una variable, puede habilitar al compilador que deduzca y asigne al tipo. Esto se conoce como *inferencia de tipo local*.  
  
 Las variables cuyos tipos se deduzcan están fuertemente tipadas, al igual que las variables cuyo tipo se especifican explícitamente. Inferencia de tipo local sólo funciona cuando se define una variable local dentro de un cuerpo de método. Para obtener más información, consulte [Option Infer instrucción](../../../../visual-basic/language-reference/statements/option-infer-statement.md) y [inferencia de tipo Local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 En el ejemplo siguiente se ilustra la inferencia de tipo local. Para usar este ejemplo, debe establecer `Option Infer` a `On`.  
  
 [!code-vb[VbLINQVbFeatures#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]  
  
 Inferencia de tipo local también permite crear tipos anónimos, que se describen más adelante en esta sección y son necesarios para las consultas LINQ.  
  
 En el siguiente ejemplo LINQ, inferencia de tipos se produce si `Option Infer` sea `On` o `Off`. Se produce un error en tiempo de compilación si `Option Infer` es `Off` y `Option Strict` es `On`.  
  
 [!code-vb[VbLINQVbFeatures#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]  
  
## <a name="object-initializers"></a>Inicializadores de objeto  
 Inicializadores de objeto se utilizan en expresiones de consulta una vez crear un tipo anónimo que contenga los resultados de una consulta. También puede usarse para inicializar objetos de tipos con nombre fuera de las consultas. Mediante el uso de un inicializador de objeto, puede inicializar un objeto en una sola línea sin llamar explícitamente a un constructor. Suponiendo que tiene una clase denominada `Customer` cuya pública `Name` y `Phone` propiedades, junto con otras propiedades, se puede utilizar un inicializador de objeto de esta manera:  
  
 [!code-vb[VbLINQVbFeatures#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]  
  
 Para obtener más información, consulte [inicializadores de objeto: tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="anonymous-types"></a>Tipos anónimos  
 Tipos anónimos proporcionan una manera cómoda de agrupar temporalmente un conjunto de propiedades en un elemento que se va a incluir en un resultado de consulta. Esto le permite elegir cualquier combinación de los campos disponibles en la consulta, en cualquier orden, sin tener que definir un tipo de datos con nombre para el elemento.  
  
 Un *tipo anónimo* se genera dinámicamente por el compilador. El nombre del tipo es asignado por el compilador, y podría cambiar con cada nueva compilación. Por lo tanto, el nombre no se puede usar directamente. Tipos anónimos se inicializan de la manera siguiente:  
  
 [!code-vb[VbLINQVbFeatures#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]  
  
 Para más información, vea [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="extension-methods"></a>métodos de extensión.  
 Métodos de extensión permiten agregar métodos a un tipo de datos o una interfaz desde fuera de la definición. Esta característica permite, de hecho, agregar nuevos métodos a un tipo existente sin modificar el tipo. Los operadores de consulta estándar son un conjunto de métodos de extensión que proporcionan [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] funcionalidad de consulta para cualquier tipo que implemente <xref:System.Collections.Generic.IEnumerable%601>. Otras extensiones de <xref:System.Collections.Generic.IEnumerable%601> incluyen <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, y <xref:System.Linq.Enumerable.Intersect%2A>.  
  
 El siguiente método de extensión agrega un método de impresión a la <xref:System.String> clase.  
  
 [!code-vb[VbLINQVbFeatures#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]  
  
 Se llama al método como un método de instancia normal de <xref:System.String>:  
  
 [!code-vb[VbLINQVbFeatures#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]  
  
 Para más información, vea [Métodos de extensión](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Expresiones lambda  
 Una expresión lambda es una función sin un nombre que se calcula y devuelve un valor único. A diferencia de las funciones con nombre, una expresión lambda se puede definir y ejecutar al mismo tiempo. En el ejemplo siguiente se muestra 4.  
  
 [!code-vb[VbLINQVbFeatures#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]  
  
 Puede asignar la definición de la expresión lambda a un nombre de variable y, a continuación, usar el nombre para llamar a la función. En el ejemplo siguiente también muestra 4.  
  
 [!code-vb[VbLINQVbFeatures#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]  
  
 En [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], las expresiones lambda subyacen a muchos de los operadores de consulta estándar. El compilador crea expresiones lambda para capturar los cálculos definidos en los métodos de consulta fundamentales como `Where`, `Select`, `Order By`, `Take While`y otros.  
  
 Por ejemplo, el código siguiente define una consulta que devuelve todos los alumnos senior de una lista de estudiantes.  
  
 [!code-vb[VbLINQVbFeatures#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]  
  
 La definición de consulta se compila en código similar al ejemplo siguiente, que utiliza dos expresiones lambda para especificar los argumentos para `Where` y `Select`.  
  
 [!code-vb[VbLINQVbFeatures#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]  
  
 Cualquiera de las versiones se puede ejecutar mediante una `For Each` bucle:  
  
 [!code-vb[VbLINQVbFeatures#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]  
  
 Para obtener más información, vea [Expresiones lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="see-also"></a>Vea también  
 [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [LINQ y cadenas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 [Option Infer (instrucción)](../../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)

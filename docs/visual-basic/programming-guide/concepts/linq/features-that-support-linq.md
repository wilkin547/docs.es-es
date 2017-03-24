---
title: "Características de Visual Basic que admiten LINQ | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
caps.latest.revision: 51
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3bca15a07a88195589b9c9de5f9842eea42912f1
ms.lasthandoff: 03/13/2017

---
# <a name="visual-basic-features-that-support-linq"></a>Características de Visual Basic que admiten LINQ
El nombre [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] hace referencia a la tecnología en Visual Basic otras construcciones directamente en el lenguaje y admite la sintaxis de consulta. Con [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], no tiene que aprender un nuevo lenguaje de consulta en un origen de datos externo. Puede consultar con los datos en bases de datos relacionales, los almacenes XML u objetos utilizando Visual Basic. Esta integración de capacidades de consulta en el lenguaje permite la comprobación en tiempo de compilación para los errores de sintaxis y seguridad de tipos. Esta integración también garantiza que ya conoce la mayoría de lo que tiene que saber para escribir consultas complejas y variadas en Visual Basic.  
  
 Las secciones siguientes describen las construcciones del lenguaje que admiten LINQ en el nivel de detalle suficiente para que pueda empezar a leer la documentación introductoria, ejemplos de código y aplicaciones de ejemplo. También puede hacer clic en los vínculos para encontrar una explicación más detallada de cómo las características de lenguaje se reúnen para habilitar la consulta integrada de lenguaje. Es un buen lugar para comenzar [Tutorial: escribir consultas en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).  
  
## <a name="query-expressions"></a>Expresiones de consulta  
 Expresiones de consulta en Visual Basic se pueden expresar en una sintaxis declarativa similar a la de SQL o XQuery. En tiempo de compilación, la sintaxis de consulta se convierte en llamadas de método a la implementación de un proveedor LINQ de los métodos de extensión de operador de consulta estándar. Control de aplicaciones que los operadores de consulta estándar se encuentran dentro del ámbito especificando el espacio de nombres adecuado con una `Imports` instrucción. Sintaxis de una expresión de consulta de Visual Basic tiene el siguiente aspecto:  
  
 [!code-vb[1 VbLINQVbFeatures](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]  
  
 Para obtener más información, consulte [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="implicitly-typed-variables"></a>Variables con tipo implícito  
 En lugar de especificar explícitamente un tipo al declarar e inicializar una variable, puede habilitar al compilador que deduzca y asigne al tipo. Esto se conoce como *inferencia del tipo local*.  
  
 Variables cuyos tipos se deducen están fuertemente tipadas, igual que las variables cuyo tipo se especifican explícitamente. Inferencia de tipo local sólo funciona cuando se define una variable local dentro de un cuerpo de método. Para obtener más información, consulte [Option Infer instrucción](../../../../visual-basic/language-reference/statements/option-infer-statement.md) y [inferencia de tipo Local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 En el ejemplo siguiente se ilustra la inferencia de tipo local. Para utilizar este ejemplo, debe establecer `Option Infer` a `On`.  
  
 [!code-vb[VbLINQVbFeatures&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]  
  
 Inferencia de tipo local también permite crear tipos anónimos, que se describen más adelante en esta sección y son necesarios para las consultas LINQ.  
  
 En el siguiente ejemplo LINQ, se produce la inferencia de tipo si `Option Infer` sea `On` o `Off`. Se produce un error en tiempo de compilación si `Option Infer` es `Off` y `Option Strict` es `On`.  
  
 [!code-vb[VbLINQVbFeatures&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]  
  
## <a name="object-initializers"></a>Inicializadores de objeto  
 Inicializadores de objeto se utilizan en expresiones de consulta cuando tiene que crear un tipo anónimo que contenga los resultados de una consulta. También puede utilizarse para inicializar los objetos de tipos con nombre fuera de las consultas. Usando un inicializador de objeto, puede inicializar un objeto en una sola línea sin llamar explícitamente a un constructor. Suponiendo que tiene una clase denominada `Customer` cuya pública `Name` y `Phone` propiedades, junto con otras propiedades, se puede utilizar un inicializador de objeto de esta manera:  
  
 [!code-vb[VbLINQVbFeatures Nº&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]  
  
 Para obtener más información, consulte [inicializadores de objeto: tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="anonymous-types"></a>Tipos anónimos  
 Los tipos anónimos son una manera cómoda de agrupar temporalmente un conjunto de propiedades en un elemento que se va a incluir en el resultado de una consulta. Esto le permite elegir cualquier combinación de campos disponibles en la consulta, en cualquier orden, sin definir un tipo de datos con nombre para el elemento.  
  
 Un *tipo anónimo* se construye dinámicamente el compilador. El nombre del tipo es asignado por el compilador, y podría cambiar con cada nueva compilación. Por lo tanto, el nombre no puede utilizarse directamente. Los tipos anónimos se inicializan de la siguiente manera:  
  
 [!code-vb[VbLINQVbFeatures&#5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]  
  
 Para obtener más información, consulte [tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="extension-methods"></a>métodos de extensión.  
 Métodos de extensión permiten agregar métodos a una interfaz desde fuera de la definición o el tipo de datos. Esta característica permite, en efecto, agregar nuevos métodos a un tipo existente sin modificar el tipo. Los operadores de consulta estándar son un conjunto de métodos de extensión que proporcionan [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] funcionalidad de consulta para cualquier tipo que implemente <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> Otras extensiones de <xref:System.Collections.Generic.IEnumerable%601>incluyen <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>y <xref:System.Linq.Enumerable.Intersect%2A>.</xref:System.Linq.Enumerable.Intersect%2A> </xref:System.Linq.Enumerable.Union%2A> </xref:System.Linq.Enumerable.Count%2A> </xref:System.Collections.Generic.IEnumerable%601>  
  
 El siguiente método de extensión agrega un método de impresión a la <xref:System.String>clase.</xref:System.String>  
  
 [!code-vb[VbLINQVbFeatures Nº&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]  
  
 Se llama al método como un método de instancia normal de <xref:System.String>:</xref:System.String>  
  
 [!code-vb[VbLINQVbFeatures&#7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]  
  
 Para obtener más información, consulte [métodos de extensión](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Expresiones lambda  
 Una expresión lambda es una función sin nombre que se calcula y devuelve un valor único. A diferencia de las funciones con nombre, una expresión lambda se puede definir y ejecutar al mismo tiempo. El ejemplo siguiente muestra 4.  
  
 [!code-vb[VbLINQVbFeatures Nº&8;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]  
  
 Puede asignar la definición de la expresión lambda a un nombre de variable y, a continuación, utilice el nombre para llamar a la función. El ejemplo siguiente también muestra 4.  
  
 [!code-vb[VbLINQVbFeatures&#12;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]  
  
 En [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], las expresiones lambda subyacen a muchos de los operadores de consulta estándar. El compilador crea expresiones lambda para capturar los cálculos definidos en los métodos de consulta básicos como `Where`, `Select`, `Order By`, `Take While`y otros.  
  
 Por ejemplo, el código siguiente define una consulta que devuelve todos los estudiantes senior de una lista de los estudiantes.  
  
 [!code-vb[VbLINQVbFeatures&#9;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]  
  
 La definición de consulta se compila en código similar al ejemplo siguiente, que utiliza dos expresiones lambda para especificar los argumentos de `Where` y `Select`.  
  
 [!code-vb[VbLINQVbFeatures&#10;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]  
  
 Ambas versiones se pueden ejecutar mediante una `For Each` bucle:  
  
 [!code-vb[VbLINQVbFeatures&#11;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]  
  
 Para obtener más información, consulte [expresiones Lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="see-also"></a>Vea también  
 [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [LINQ y cadenas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)   
 [Opción Infer (instrucción)](../../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)

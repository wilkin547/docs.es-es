---
title: Conceptos y terminología (Transformación funcional)
ms.date: 07/20/2015
ms.assetid: 24fd244d-ebae-4721-8858-89bb544aea0b
ms.openlocfilehash: efc1fc5bb738e3d5d9d3fa2a8226c37da69c045c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345705"
---
# <a name="concepts-and-terminology-functional-transformation-visual-basic"></a>Concepts and Terminology (Functional Transformation) (Visual Basic)
Este tema presenta los conceptos y la terminología en relación con las transformaciones funcionales. La aproximación que utiliza la transformación funcional para transformar datos permite obtener un código que normalmente se escribe más rápido, es más expresivo y fácil de mantener y depurar, si lo comparamos con la programación imperativa, que es más tradicional.

Observe que los temas incluidos en esta lección no pretenden explicar con detalle cómo es la programación funcional. En su lugar, pretenden resaltar algunas de las características de la programación funcional que facilitan el proceso de transformar un XML de una forma a otra.

## <a name="what-is-pure-functional-transformation"></a>¿En qué consiste la transformación funcional pura?

En la *transformación funcional pura*, existe un conjunto de funciones, llamadas *funciones puras*, que definen cómo transformar un conjunto de datos estructurados de su forma original a otra forma. La palabra "pura" indica que las funciones *admiten composición*, lo que significa que son:

- *Autocontenidas*, de forma que se pueden ordenar o reorganizar libremente sin preocuparse por las dependencias que puedan tener con el resto del programa. Las transformaciones puras no tienen conocimiento sobre su entorno ni ningún efecto sobre éste. Es decir, las funciones que se usan en la transformación no tienen *efectos secundarios*.

- *Sin estado*, lo que significa que si se ejecuta la misma función o un conjunto específico de funciones en los mismos datos de entrada, el resultado siempre será el mismo. Las transformaciones puras no recuerdan sus ejecuciones anteriores.

> [!IMPORTANT]
> Para el resto de este tutorial, el término "función pura" se utilizará en sentido general para señalar una técnica de programación y no una característica específica del lenguaje.
>
> Note that pure functions must be implemented as functions in Visual Basic.
>
> Además, no debería confundir las funciones puras con los métodos virtuales puros de C++. Estos últimos indican que la clase contenedora es abstracta y que no incluye ningún cuerpo de método.

### <a name="functional-programming"></a>Programación funcional

La *programación funcional* es una técnica de programación que permite el uso de transformaciones funcionales puras directamente.

Tradicionalmente, los lenguajes de programación funcionales de uso general, como ML, Scheme, Haskell y F#, han atraído principalmente la atención de la comunidad académica. Although it has always been possible to write pure functional transformations in Visual Basic, the difficulty of doing so has not made it an attractive option to most programmers. With later versions of Visual Basic, however, new language constructs such as lambda expressions and type inference make it functional programming much easier and more productive.

For more information about functional programming, see [Functional Programming vs. Imperative Programming (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md).

#### <a name="domain-specific-fp-languages"></a>Lenguajes de programación funcionales para ciertos campos

Aunque todavía no se han adoptado mayoritariamente los lenguajes de programación funcionales, sí han tenido más éxito los lenguajes de programación funcionales específicos para ciertos campos. Por ejemplo, las hojas de estilos en cascada (CSS) se utilizan para definir la apariencia de numerosas paginas web y las hojas de estilos del Lenguaje de transformación basado en hojas de estilo (XSLT) se utilizan muy a menudo para la manipulación de datos XML. Para obtener más información sobre XSLT, consulte [XSLT Transformations](../../../../standard/data/xml/xslt-transformations.md) (Transformaciones XSLT).

## <a name="terminology"></a>Terminología

La siguiente tabla define algunos términos relacionados con las transformaciones funcionales.

Función de orden superior (primera clase) \
Función que se puede tratar como un objeto de programación. Por ejemplo, es posible pasar una función de orden superior como argumento de otra función, así como ser devuelta por otra función. In Visual Basic, delegates and lambda expressions are language features that support higher-order functions. Si desea escribir una función de orden superior, deberá declarar uno o más argumentos para recibir delegados, y a menudo utilizará expresiones lambda cuando llame a dichas funciones. La mayoría de operadores estándar de consulta son funciones de orden superior.

For more information, see [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).

Expresión lambda \
En esencia, es posible utilizar una función anónima alineada siempre que se espere como argumento un tipo delegado. Esta es una definición simplificada de las expresiones lambda, pero resulta adecuada para los objetivos de este tutorial.

Para obtener más información, consulte [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) (Expresiones lambda).

Colección \
Conjunto de datos estructurados, normalmente del mismo tipo. Para que una colección sea compatible con LINQ, ésta debe implementar la interfaz <xref:System.Collections.IEnumerable> o la interfaz <xref:System.Linq.IQueryable> (o una de sus equivalentes genéricas), <xref:System.Collections.Generic.IEnumerator%601> o <xref:System.Linq.IQueryable%601>).

Tupla (tipos anónimos) \
Se trata de un concepto matemático: una tupa es una secuencia finita de objetos, cada uno de los cuales es de un tipo específico. A las tuplas también se las conoce como listas ordenadas. Los tipos anónimos son una implementación del lenguaje para este concepto, lo que permite declarar un tipo de clase sin nombre e instanciar un objeto de este tipo al mismo tiempo.

For more information, see  [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).

Inferencia de tipos (tipos implícitos) \
Consiste en la capacidad del compilador para determinar el tipo de una variable en caso de que no exista una declaración de tipos explícita.

For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).

Ejecución aplazada y evaluación diferida \
Es posible retrasar la evaluación de una expresión hasta que se requiera el valor resultante. Las colecciones admiten la ejecución aplazada.

For more information, see [Basic Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md) and [Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).

Estas características del lenguaje se utilizarán en códigos de ejemplo a lo largo de esta sección.

## <a name="see-also"></a>Vea también

- [Introduction to Pure Functional Transformations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [Functional Programming vs. Imperative Programming (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)

---
title: Conceptos y terminología (transformación funcional)
ms.date: 07/20/2015
ms.assetid: 24fd244d-ebae-4721-8858-89bb544aea0b
ms.openlocfilehash: 4a63630d431a0972fb1a61981306a41e6f4926e3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410869"
---
# <a name="concepts-and-terminology-functional-transformation-visual-basic"></a>Conceptos y terminología (transformación funcional) (Visual Basic)
Este tema presenta los conceptos y la terminología en relación con las transformaciones funcionales. La aproximación que utiliza la transformación funcional para transformar datos permite obtener un código que normalmente se escribe más rápido, es más expresivo y fácil de mantener y depurar, si lo comparamos con la programación imperativa, que es más tradicional.

Observe que los temas incluidos en esta lección no pretenden explicar con detalle cómo es la programación funcional. En su lugar, pretenden resaltar algunas de las características de la programación funcional que facilitan el proceso de transformar un XML de una forma a otra.

## <a name="what-is-pure-functional-transformation"></a>¿En qué consiste la transformación funcional pura?

En la *transformación funcional pura*, existe un conjunto de funciones, llamadas *funciones puras*, que definen cómo transformar un conjunto de datos estructurados de su forma original a otra forma. La palabra "pura" indica que las funciones *admiten composición*, lo que significa que son:

- *Autocontenidas*, de forma que se pueden ordenar o reorganizar libremente sin preocuparse por las dependencias que puedan tener con el resto del programa. Las transformaciones puras no tienen conocimiento sobre su entorno ni ningún efecto sobre éste. Es decir, las funciones que se usan en la transformación no tienen *efectos secundarios*.

- *Sin estado*, lo que significa que si se ejecuta la misma función o un conjunto específico de funciones en los mismos datos de entrada, el resultado siempre será el mismo. Las transformaciones puras no recuerdan sus ejecuciones anteriores.

> [!IMPORTANT]
> Para el resto de este tutorial, el término "función pura" se utilizará en sentido general para señalar una técnica de programación y no una característica específica del lenguaje.
>
> Tenga en cuenta que las funciones puras deben implementarse como funciones en Visual Basic.
>
> Además, no debería confundir las funciones puras con los métodos virtuales puros de C++. Estos últimos indican que la clase contenedora es abstracta y que no incluye ningún cuerpo de método.

### <a name="functional-programming"></a>Programación funcional

La *programación funcional* es una técnica de programación que permite el uso de transformaciones funcionales puras directamente.

Tradicionalmente, los lenguajes de programación funcionales de uso general, como ML, Scheme, Haskell y F#, han atraído principalmente la atención de la comunidad académica. Aunque siempre ha sido posible escribir transformaciones funcionales puras en Visual Basic, la dificultad de hacerlo no la ha convertido en una opción atractiva para la mayoría de los programadores. Sin embargo, con versiones posteriores de Visual Basic, las nuevas construcciones del lenguaje, como las expresiones lambda y la inferencia de tipos, hacen que la programación funcional sea mucho más sencilla y productiva.

Para obtener más información sobre la programación funcional, vea programación [funcional frente a programación imperativa (Visual Basic)](functional-programming-vs-imperative-programming.md).

#### <a name="domain-specific-fp-languages"></a>Lenguajes de programación funcionales para ciertos campos

Aunque todavía no se han adoptado mayoritariamente los lenguajes de programación funcionales, sí han tenido más éxito los lenguajes de programación funcionales específicos para ciertos campos. Por ejemplo, las hojas de estilos en cascada (CSS) se utilizan para definir la apariencia de numerosas paginas web y las hojas de estilos del Lenguaje de transformación basado en hojas de estilo (XSLT) se utilizan muy a menudo para la manipulación de datos XML. Para obtener más información sobre XSLT, consulte [Transformaciones XSLT](../../../../standard/data/xml/xslt-transformations.md).

## <a name="terminology"></a>Terminología

La siguiente tabla define algunos términos relacionados con las transformaciones funcionales.

Función de orden superior (primera clase) \
Función que se puede tratar como un objeto de programación. Por ejemplo, es posible pasar una función de orden superior como argumento de otra función, así como ser devuelta por otra función. En Visual Basic, los delegados y las expresiones lambda son características del lenguaje que admiten funciones de orden superior. Si desea escribir una función de orden superior, deberá declarar uno o más argumentos para recibir delegados, y a menudo utilizará expresiones lambda cuando llame a dichas funciones. La mayoría de operadores estándar de consulta son funciones de orden superior.

Para obtener más información, vea [información general sobre operadores de consulta estándar (Visual Basic)](standard-query-operators-overview.md).

Expresión lambda \
En esencia, es posible utilizar una función anónima alineada siempre que se espere como argumento un tipo delegado. Esta es una definición simplificada de las expresiones lambda, pero resulta adecuada para los objetivos de este tutorial.

Para obtener más información, consulte [Expresiones lambda](../../language-features/procedures/lambda-expressions.md).

Colección \
Conjunto de datos estructurados, normalmente del mismo tipo. Para que una colección sea compatible con LINQ, ésta debe implementar la interfaz <xref:System.Collections.IEnumerable> o la interfaz <xref:System.Linq.IQueryable> (o una de sus equivalentes genéricas), <xref:System.Collections.Generic.IEnumerator%601> o <xref:System.Linq.IQueryable%601>).

Tupla (tipos anónimos) \
Se trata de un concepto matemático: una tupa es una secuencia finita de objetos, cada uno de los cuales es de un tipo específico. A las tuplas también se las conoce como listas ordenadas. Los tipos anónimos son una implementación del lenguaje para este concepto, lo que permite declarar un tipo de clase sin nombre e instanciar un objeto de este tipo al mismo tiempo.

Para obtener más información, vea [tipos anónimos](../../language-features/objects-and-classes/anonymous-types.md).

Inferencia de tipos (tipos implícitos) \
Consiste en la capacidad del compilador para determinar el tipo de una variable en caso de que no exista una declaración de tipos explícita.

Para obtener más información, vea [inferencia de tipo local](../../language-features/variables/local-type-inference.md).

Ejecución aplazada y evaluación diferida \
Es posible retrasar la evaluación de una expresión hasta que se requiera el valor resultante. Las colecciones admiten la ejecución aplazada.

Para obtener más información, vea [operaciones básicas de consulta (Visual Basic)](basic-query-operations.md) y [ejecución aplazada y evaluación diferida en LINQ to XML (Visual Basic)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).

Estas características del lenguaje se utilizarán en códigos de ejemplo a lo largo de esta sección.

## <a name="see-also"></a>Vea también

- [Introducción a las transformaciones funcionales puras (Visual Basic)](introduction-to-pure-functional-transformations.md)
- [Programación funcional frente a programación imperativa (Visual Basic)](functional-programming-vs-imperative-programming.md)

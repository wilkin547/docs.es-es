---
title: Conceptos y terminología (transformación funcional) (C#)
ms.date: 07/20/2015
ms.assetid: 03defb3a-7e17-4ab1-8efa-4dd66621e860
ms.openlocfilehash: df8abe5b6815e2b9f1a9a1693944ddaa1c7c84cb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921949"
---
# <a name="concepts-and-terminology-functional-transformation-c"></a>Conceptos y terminología (transformación funcional) (C#)
Este tema presenta los conceptos y la terminología en relación con las transformaciones funcionales. La aproximación que utiliza la transformación funcional para transformar datos permite obtener un código que normalmente se escribe más rápido, es más expresivo y fácil de mantener y depurar, si lo comparamos con la programación imperativa, que es más tradicional.  
  
 Observe que los temas incluidos en esta lección no pretenden explicar con detalle cómo es la programación funcional. En su lugar, pretenden resaltar algunas de las características de la programación funcional que facilitan el proceso de transformar un XML de una forma a otra.  
  
## <a name="what-is-pure-functional-transformation"></a>¿En qué consiste la transformación funcional pura?  
 En la *transformación funcional pura*, existe un conjunto de funciones, llamadas *funciones puras*, que definen cómo transformar un conjunto de datos estructurados de su forma original a otra forma. La palabra "pura" indica que las funciones *admiten composición*, lo que significa que son:  
  
- *Autocontenidas*, de forma que se pueden ordenar o reorganizar libremente sin preocuparse por las dependencias que puedan tener con el resto del programa. Las transformaciones puras no tienen conocimiento sobre su entorno ni ningún efecto sobre éste. Es decir, las funciones que se usan en la transformación no tienen *efectos secundarios*.  
  
- *Sin estado*, lo que significa que si se ejecuta la misma función o un conjunto específico de funciones en los mismos datos de entrada, el resultado siempre será el mismo. Las transformaciones puras no recuerdan sus ejecuciones anteriores.  
  
> [!IMPORTANT]
> Para el resto de este tutorial, el término "función pura" se utilizará en sentido general para señalar una técnica de programación y no una característica específica del lenguaje.  
>   
>  Tenga en cuenta que las funciones puras deben implementarse como métodos en C#.  
>   
>  Además, no debería confundir las funciones puras con los métodos virtuales puros de C++. Estos últimos indican que la clase contenedora es abstracta y que no incluye ningún cuerpo de método.  
  
### <a name="functional-programming"></a>Programación funcional  
 La *programación funcional* es una técnica de programación que permite el uso de transformaciones funcionales puras directamente.  
  
 Tradicionalmente, los lenguajes de programación funcionales de uso general, como ML, Scheme, Haskell y F#, han atraído principalmente la atención de la comunidad académica. Aunque siempre ha sido posible escribir transformaciones funcionales puras en C#, la dificultad para hacerlo no la ha convertido en una opción atractiva de cara a los programadores. No obstante, en las versiones recientes de C# se han incorporado nuevos constructores del lenguaje, como son las expresiones lambda o la inferencia de tipos, que simplifican enormemente la programación funcional y permiten aumentar la productividad.  
  
 Para obtener más información sobre la programación funcional, consulte [Functional Programming vs. Imperative Programming (C#)](./functional-programming-vs-imperative-programming.md) (Diferencias entre la programación funcional y la programación imperativa [C#]).  
  
#### <a name="domain-specific-fp-languages"></a>Lenguajes de programación funcionales para ciertos campos  
 Aunque todavía no se han adoptado mayoritariamente los lenguajes de programación funcionales, sí han tenido más éxito los lenguajes de programación funcionales específicos para ciertos campos. Por ejemplo, las hojas de estilos en cascada (CSS) se utilizan para definir la apariencia de numerosas paginas web y las hojas de estilos del Lenguaje de transformación basado en hojas de estilo (XSLT) se utilizan muy a menudo para la manipulación de datos XML. Para obtener más información sobre XSLT, consulte [XSLT Transformations](../../../../standard/data/xml/xslt-transformations.md) (Transformaciones XSLT).  
  
## <a name="terminology"></a>Terminología  
 La siguiente tabla define algunos términos relacionados con las transformaciones funcionales.  
  
 Función de orden superior (primera clase)  
 Función que se puede tratar como un objeto de programación. Por ejemplo, es posible pasar una función de orden superior como argumento de otra función, así como ser devuelta por otra función. En C#, los delegados y las expresiones lambda son características del lenguaje que admiten el uso de funciones de orden superior. Si desea escribir una función de orden superior, deberá declarar uno o más argumentos para recibir delegados, y a menudo utilizará expresiones lambda cuando llame a dichas funciones. La mayoría de operadores estándar de consulta son funciones de orden superior.  
  
 Para obtener más información, consulte [Información general sobre operadores de consulta estándar (C#)](./standard-query-operators-overview.md).  
  
 Expresión lambda  
 En esencia, es posible utilizar una función anónima alineada siempre que se espere como argumento un tipo delegado. Esta es una definición simplificada de las expresiones lambda, pero resulta adecuada para los objetivos de este tutorial.  
  
 Para obtener más información, consulte [Lambda Expressions](../../statements-expressions-operators/lambda-expressions.md) (Expresiones lambda).  
  
 colección  
 Conjunto de datos estructurados, normalmente del mismo tipo. Para que una colección sea compatible con LINQ, ésta debe implementar la interfaz <xref:System.Collections.IEnumerable> o la interfaz <xref:System.Linq.IQueryable> (o una de sus equivalentes genéricas), <xref:System.Collections.Generic.IEnumerator%601> o <xref:System.Linq.IQueryable%601>).  
  
 Tupla (tipos anónimos)  
 Se trata de un concepto matemático: una tupa es una secuencia finita de objetos, cada uno de los cuales es de un tipo específico. A las tuplas también se las conoce como listas ordenadas. Los tipos anónimos son una implementación del lenguaje para este concepto, lo que permite declarar un tipo de clase sin nombre e instanciar un objeto de este tipo al mismo tiempo.  
  
 Para más información, vea [Tipos anónimos](../../classes-and-structs/anonymous-types.md).  
  
 Inferencia de tipos (tipos implícitos)  
 Consiste en la capacidad del compilador para determinar el tipo de una variable en caso de que no exista una declaración de tipos explícita.  
  
 Para obtener más información, consulte [Variables locales con asignación implícita de tipos](../../classes-and-structs/implicitly-typed-local-variables.md).  
  
 Ejecución aplazada y evaluación diferida  
 Es posible retrasar la evaluación de una expresión hasta que se requiera el valor resultante. Las colecciones admiten la ejecución aplazada.  
  
 Para obtener más información, consulte [Introduction to LINQ Queries (C#)](./introduction-to-linq-queries.md) (Introducción a las consultas LINQ [C#]) y [Deferred Execution and Lazy Evaluation in LINQ to XML (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md) (Ejecución aplazada y evaluación diferida en LINQ to XML [C#]).  
  
 Estas características del lenguaje se utilizarán en códigos de ejemplo a lo largo de esta sección.  
  
## <a name="see-also"></a>Vea también

- [Introducción a las transformaciones funcionales puras (C#)](./introduction-to-pure-functional-transformations.md)
- [Diferencias entre la programación funcional y la programación imperativa (C#)](./functional-programming-vs-imperative-programming.md)

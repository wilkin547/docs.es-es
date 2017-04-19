---
title: "Conceptos y terminología (transformación funcional) (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: 24fd244d-ebae-4721-8858-89bb544aea0b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9c4716765199798e50c4318b290f8a2d76ef5841
ms.lasthandoff: 03/13/2017


---
# <a name="concepts-and-terminology-functional-transformation-visual-basic"></a>Conceptos y terminología (transformación funcional) (Visual Basic)
Este tema presenta los conceptos y la terminología en relación con las transformaciones funcionales. La aproximación que utiliza la transformación funcional para transformar datos permite obtener un código que normalmente se escribe más rápido, es más expresivo y fácil de mantener y depurar, si lo comparamos con la programación imperativa, que es más tradicional.  
  
 Observe que los temas incluidos en esta lección no pretenden explicar con detalle cómo es la programación funcional. En su lugar, pretenden resaltar algunas de las características de la programación funcional que facilitan el proceso de transformar un XML de una forma a otra.  
  
## <a name="what-is-pure-functional-transformation"></a>¿En qué consiste la transformación funcional pura?  
 En *transformación funcional pura*, un conjunto de funciones, denominadas *funciones puras*, definir cómo transformar un conjunto de datos estructurados de su forma original a otra forma. La palabra "pura" indica que las funciones son *admite composición*, lo que significa son:  
  
-   *Autónoma*, de modo que puedan libremente ordenadas y reorganizar sin preocuparse o interdependencias con el resto del programa. Las transformaciones puras no tienen conocimiento sobre su entorno ni ningún efecto sobre éste. Es decir, las funciones utilizadas en la transformación no tienen *efectos secundarios*.  
  
-   *Sin estado*, de modo que se ejecuta la misma función o un conjunto específico de funciones de la misma entrada siempre resultado será el mismo resultado. Las transformaciones puras no recuerdan sus ejecuciones anteriores.  
  
> [!IMPORTANT]
>  Para el resto de este tutorial, el término "función pura" se utilizará en sentido general para señalar una técnica de programación y no una característica específica del lenguaje.  
>   
>  Tenga en cuenta que las funciones puras deben implementarse como funciones en Visual Basic.  
>   
>  Además, no debería confundir las funciones puras con los métodos virtuales puros de C++. Estos últimos indican que la clase contenedora es abstracta y que no incluye ningún cuerpo de método.  
  
### <a name="functional-programming"></a>Programación funcional  
 *Programación funcional* es una técnica de programación que admite directamente la transformación funcional pura.  
  
 Históricamente, el uso generales lenguajes de programación funcionales, como ML, combinación, Haskell y F #, han sido principalmente de interés para la Comunidad académica. Aunque siempre ha sido posible escribir transformaciones funcionales puras en Visual Basic, la dificultad para hacerlo no la ha convertido, una opción atractiva a los programadores. Con las versiones posteriores de Visual Basic, no obstante, nuevos constructores del lenguaje, como las expresiones lambda e inferencia de tipo que la programación funcional sea más fácil y más productivo.  
  
 Para obtener más información acerca de la programación funcional, vea [frente a la programación funcional. Programación imperativa (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md).  
  
#### <a name="domain-specific-fp-languages"></a>Lenguajes de programación funcionales para ciertos campos  
 Aunque todavía no se han adoptado mayoritariamente los lenguajes de programación funcionales, sí han tenido más éxito los lenguajes de programación funcionales específicos para ciertos campos. Por ejemplo, las hojas de estilos en cascada (CSS) se utilizan para definir la apariencia de numerosas paginas web y las hojas de estilos del Lenguaje de transformación basado en hojas de estilo (XSLT) se utilizan muy a menudo para la manipulación de datos XML. Para obtener más información acerca de XSLT, consulte [transformaciones XSLT](http://msdn.microsoft.com/library/202f8820-224c-494f-b61e-cd127eac6e03).  
  
## <a name="terminology"></a>Terminología  
 La siguiente tabla define algunos términos relacionados con las transformaciones funcionales.  
  
 Función de orden superior (primera clase)  
 Función que se puede tratar como un objeto de programación. Por ejemplo, es posible pasar una función de orden superior como argumento de otra función, así como ser devuelta por otra función. En Visual Basic, delegados y las expresiones lambda son características del lenguaje que admiten funciones de orden superior. Si desea escribir una función de orden superior, deberá declarar uno o más argumentos para recibir delegados, y a menudo utilizará expresiones lambda cuando llame a dichas funciones. La mayoría de operadores estándar de consulta son funciones de orden superior.  
  
 Para obtener más información, consulte [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
 Expresión lambda  
 En esencia, es posible utilizar una función anónima alineada siempre que se espere como argumento un tipo delegado. Esta es una definición simplificada de las expresiones lambda, pero resulta adecuada para los objetivos de este tutorial.  
  
 Para obtener más información, consulte [expresiones Lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 colección  
 Conjunto de datos estructurados, normalmente del mismo tipo. Para ser compatible con LINQ, una colección debe implementar la <xref:System.Collections.IEnumerable>interfaz o <xref:System.Linq.IQueryable>interfaz (o uno de sus equivalentes genéricas, <xref:System.Collections.Generic.IEnumerator%601>o <xref:System.Linq.IQueryable%601>).</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerator%601> </xref:System.Linq.IQueryable> </xref:System.Collections.IEnumerable>  
  
 Tupla (tipos anónimos)  
 Se trata de un concepto matemático: una tupa es una secuencia finita de objetos, cada uno de los cuales es de un tipo específico. A las tuplas también se las conoce como listas ordenadas. Los tipos anónimos son una implementación del lenguaje para este concepto, lo que permite declarar un tipo de clase sin nombre e instanciar un objeto de este tipo al mismo tiempo.  
  
 Para obtener más información, consulte [tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
 Inferencia de tipos (tipos implícitos)  
 Consiste en la capacidad del compilador para determinar el tipo de una variable en caso de que no exista una declaración de tipos explícita.  
  
 Para obtener más información, consulte [inferencia de tipo Local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 Ejecución aplazada y evaluación diferida  
 Es posible retrasar la evaluación de una expresión hasta que se requiera el valor resultante. Las colecciones admiten la ejecución aplazada.  
  
 Para obtener más información, consulte [operaciones básicas de consulta (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md) y [ejecución diferida y evaluación diferida en LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).  
  
 Estas características del lenguaje se utilizarán en códigos de ejemplo a lo largo de esta sección.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las transformaciones funcionales puras (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)   
 [Diferencias entre la programación funcional y Programación imperativa (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)

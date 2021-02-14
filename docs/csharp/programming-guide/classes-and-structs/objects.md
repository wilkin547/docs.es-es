---
title: 'Objetos: Guía de programación de C#'
description: C# usa una definición de clase o estructura para definir tipos de objetos. En un lenguaje orientado a objetos como C#, un programa consta de objetos que interactúan de forma dinámica.
ms.date: 02/03/2021
helpviewer_keywords:
- objects [C#], about objects
- variables [C#]
ms.assetid: af4a5230-fbf3-4eea-95e1-8b883c2f845c
ms.openlocfilehash: df549b76c5bd49fa91424915928527ec14d7689c
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585719"
---
# <a name="objects-c-programming-guide"></a>Objetos (Guía de programación de C#)

Una definición de clase o estructura es como un plano que especifica qué puede hacer el tipo. Un objeto es básicamente un bloque de memoria que se ha asignado y configurado de acuerdo con el plano. Un programa puede crear muchos objetos de la misma clase. Los objetos también se denominan instancias y pueden almacenarse en una variable con nombre, o en una matriz o colección. El código de cliente es el código que usa estas variables para llamar a los métodos y acceder a las propiedades públicas del objeto. En un lenguaje orientado a objetos, como C#, un programa típico consta de varios objetos que interactúan dinámicamente.  
  
> [!NOTE]
> Los tipos estáticos se comportan de forma diferente a lo que se describe aquí. Para más información, vea [Clases estáticas y sus miembros](./static-classes-and-static-class-members.md).
  
## <a name="struct-instances-vs-class-instances"></a>Instancias de estructura frente a Instancias de clase  

 Puesto que las clases son tipos de referencia, una variable de un objeto de clase contiene una referencia a la dirección del objeto del montón administrado. Si se asigna un segundo objeto del mismo tipo al primer objeto, ambas variables hacen referencia al objeto de esa dirección. Este punto se analiza con más detalle más adelante en este tema.  
  
 Las instancias de clases se crean mediante el [operador new](../../language-reference/operators/new-operator.md). En el ejemplo siguiente, `Person` es el tipo, y `person1` y `person2` son instancias u objetos de ese tipo.  
  
 [!code-csharp[csProgGuideStatements#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#30)]  
  
 Dado que las estructuras son tipos de valor, una variable de un objeto de estructura contiene una copia de todo el objeto. También se pueden crear instancias de estructuras usando el operador `new`, pero esto no resulta necesario, como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideStatements#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#31)]  
  
 La memoria para `p1` y `p2` se asigna en la pila de subprocesos. Esta memoria se reclama junto con el tipo o método en el que se declara. Este es uno de los motivos por los que se copian las estructuras en la asignación. Por el contrario, la memoria que se asigna a una instancia de clase la reclama automáticamente (recolección de elementos no utilizados) Common Language Runtime cuando todas las referencias al objeto se han salido del ámbito. No es posible destruir de forma determinante un objeto de clase como en C++. Para obtener más información sobre la recolección de elementos no utilizados en .NET, vea [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md).  
  
> [!NOTE]
> La asignación y desasignación de memoria en el montón administrado están muy optimizadas en Common Language Runtime. En la mayoría de los casos, no existe ninguna diferencia significativa en el costo de rendimiento entre asignar una instancia de clase en el montón y asignar una instancia de estructura en la pila.
  
## <a name="object-identity-vs-value-equality"></a>Identidad de objeto frente a igualdad de valores  

 Cuando se comparan dos objetos para comprobar si son iguales, primero debe determinar si quiere saber si las dos variables representan el mismo objeto en la memoria o si los valores de uno o varios de sus campos son equivalentes. Si tiene previsto comparar valores, debe tener en cuenta si los objetos son instancias de tipos de valor (estructuras) o tipos de referencia (clases, delegados y matrices).  
  
- Para determinar si dos instancias de clase hacen referencia a la misma ubicación en la memoria (lo que significa que tienen la misma *identidad*), use el método estático <xref:System.Object.Equals%2A>. (<xref:System.Object?displayProperty=nameWithType> es la clase base implícita para todos los tipos de valor y tipos de referencia, incluidas las clases y estructuras definidas por el usuario).  
  
- Para determinar si los campos de instancia de dos instancias de estructura presentan los mismos valores, use el método <xref:System.ValueType.Equals%2A?displayProperty=nameWithType>. Dado que todas las estructuras heredan implícitamente de <xref:System.ValueType?displayProperty=nameWithType>, se llama al método directamente en el objeto, como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideStatements#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#32)]  
  
 En algunos casos, la implementación de <xref:System.ValueType?displayProperty=nameWithType> de `Equals` utiliza la conversión boxing y la reflexión. Para obtener información sobre cómo proporcionar un algoritmo de igualdad eficaz que sea específico del tipo, consulte [cómo definir la igualdad de valores para un tipo](../statements-expressions-operators/how-to-define-value-equality-for-a-type.md).

- Para determinar si los valores de los campos de dos instancias de clase son iguales, puede usar el método <xref:System.Object.Equals%2A> o el [operador ==](../../language-reference/operators/equality-operators.md#equality-operator-). En cambio, úselos solo si la clase los ha invalidado o sobrecargado para proporcionar una definición personalizada de lo que significa "igualdad" para los objetos de ese tipo. La clase también puede implementar la interfaz <xref:System.IEquatable%601> o la interfaz <xref:System.Collections.Generic.IEqualityComparer%601>. Ambas interfaces proporcionan métodos que pueden servir para comprobar la igualdad de valores. Al diseñar sus propias clases que invaliden `Equals`, asegúrese de seguir las instrucciones descritas en [Procedimiento: Definición de la igualdad de valores para un tipo](../statements-expressions-operators/how-to-define-value-equality-for-a-type.md) y <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>.
  
## <a name="related-sections"></a>Secciones relacionadas  

 Para obtener más información:  
  
- [Clases](./classes.md)  
  
- [Constructores](./constructors.md)  
  
- [Finalizadores](./destructors.md)  
  
- [Eventos](../events/index.md)  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [object](../../language-reference/builtin-types/reference-types.md)
- [Herencia](./inheritance.md)
- [class](../../language-reference/keywords/class.md)
- [Tipos de estructura](../../language-reference/builtin-types/struct.md)
- [new (operador)](../../language-reference/operators/new-operator.md)
- [Sistema de tipos comunes](../../../standard/base-types/common-type-system.md)

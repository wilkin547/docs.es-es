---
title: Elementos genéricos en .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generic methods, type inference
- generics [.NET Framework], collections
- generic interfaces [.NET Framework]
- constructed generic types
- nested generic types
- generic type definitions
- generic classes [.NET Framework]
- generics [.NET Framework], interfaces
- generics [.NET Framework], about
- generics [.NET Framework]
- generic collections [.NET Framework]
- generic delegates [.NET Framework]
- generic type arguments
- generics [.NET Framework], delegates
- generics [.NET Framework], features
- constraints [.NET Framework]
- generic types
- generic type parameters
ms.assetid: 2994d786-c5c7-4666-ab23-4c83129fe39c
ms.openlocfilehash: 7f20e5108ad8bff602f5b761e65f093d987f2608
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78156314"
---
# <a name="generics-in-net"></a>Elementos genéricos en .NET

Los genéricos permiten personalizar un método, clase, estructura o interfaz con respecto a los datos precisos sobre los que se actúa. Por ejemplo, en lugar de utilizar la clase <xref:System.Collections.Hashtable> , que permite cualquier tipo de clave y valor, puede utilizar la clase genérica <xref:System.Collections.Generic.Dictionary%602> y especificar el tipo permitido para la clave y el tipo permitido para el valor. Entre las ventajas de los genéricos están una mayor reutilización del código y la seguridad de tipos.  

## <a name="defining-and-using-generics"></a>Definición y uso de genéricos
 Los genéricos son clases, estructuras, interfaces y métodos que tienen marcadores de posición (parámetros de tipo) para uno o varios de los tipos que almacenan o utilizan. Una clase de colección genérica puede usar un parámetro de tipo como marcador de posición para el tipo de objetos que almacena; los parámetros de tipo aparecen como los tipos de sus campos y los tipos de parámetros de sus métodos. Un método genérico puede usar su parámetro de tipo como el tipo de su valor devuelto o como el tipo de uno de sus parámetros formales. El código siguiente ilustra una definición de clase genérica simple.  
  
 [!code-cpp[Conceptual.Generics.Overview#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#2)]
 [!code-csharp[Conceptual.Generics.Overview#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#2)]
 [!code-vb[Conceptual.Generics.Overview#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#2)]  
  
 Cuando cree una instancia de una clase genérica, especifique los tipos reales que hay que sustituir para los parámetros de tipo. Esto establece una nueva clase genérica, a la que se hace referencia como clase genérica construida, con los tipos que elija sustituidos en todas partes en la que aparecen los parámetros de tipo. El resultado es una clase con seguridad de tipos que se adapta a su elección de tipos, como se muestra en el código siguiente.  
  
 [!code-cpp[Conceptual.Generics.Overview#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#3)]
 [!code-csharp[Conceptual.Generics.Overview#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#3)]
 [!code-vb[Conceptual.Generics.Overview#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#3)]  

### <a name="generics-terminology"></a>Terminología de los genéricos  
 Los siguientes términos se utilizan para explicar los genéricos en .NET:  
  
- Una *definición de tipo genérico* es una clase, estructura o declaración de interfaz que funciona como una plantilla, con marcadores de posición para los tipos que puede contener o utilizar. Por ejemplo, la clase <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> puede contener dos tipos: claves y valores. Dado que una definición de tipo genérico es solo una plantilla, no se pueden crear instancias de una clase, estructura o interfaz que sea una definición de tipo genérico.  
  
- Los*parámetros de tipo genérico*, o *parámetros de tipo*, son los marcadores de posición en una definición de método o tipo genérico. El tipo genérico <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> tiene dos parámetros de tipo, `TKey` y `TValue`, que representan los tipos de sus claves y valores.  
  
- Un *tipo genérico construido*, o *tipo construido*, es el resultado de especificar los tipos para los parámetros de tipo genérico de una definición de tipo genérico.  
  
- Un *argumento de tipo genérico* es cualquier tipo que se sustituye por un parámetro de tipo genérico.  
  
- El término general *tipo genérico* incluye tanto tipos construidos como definiciones de tipo genérico.  
  
- La *covarianza* y *contravarianza* de parámetros de tipo genérico permite usar tipos genéricos construidos, cuyos argumentos de tipo están más derivados (covarianza) o menos derivados (contravarianza) que un tipo construido de destino. La covarianza y la contravarianza se denominan colectivamente *varianza*. Para obtener más información, vea [Covariance and Contravariance](../../../docs/standard/generics/covariance-and-contravariance.md) (Covarianza y contravarianza).  
  
- Las*restricciones* son límites colocados en parámetros de tipo genérico. Por ejemplo, puede limitar un parámetro de tipo a tipos que implementan la interfaz genérica <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> para asegurarse de que se pueden ordenar las instancias del tipo. También puede restringir los parámetros de tipo a tipos que tienen una clase base concreta, un constructor sin parámetros o que son tipos de referencia o tipos de valor. Los usuarios del tipo genérico no pueden sustituir los argumentos de tipo que no cumplen con las restricciones.  
  
- Una *definición de método genérico* es un método con dos listas de parámetros: una lista de parámetros de tipo genérico y una lista de parámetros formales. Los parámetros de tipo pueden aparecer como el tipo de valor devuelto o como los tipos de los parámetros formales, como se muestra en el siguiente código.  
  
 [!code-cpp[Conceptual.Generics.Overview#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#4)]
 [!code-csharp[Conceptual.Generics.Overview#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#4)]
 [!code-vb[Conceptual.Generics.Overview#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#4)]  
  
 Los métodos genéricos pueden aparecer en tipos genéricos o no genéricos. Es importante tener en cuenta que un método no es genérico solo porque pertenezca a un tipo genérico, ni siquiera porque tenga parámetros formales cuyos tipos sean los parámetros genéricos del tipo envolvente. Un método solo es genérico si tiene su propia lista de parámetros de tipo. En el siguiente código, solo es genérico el método `G` .  
  
 [!code-cpp[Conceptual.Generics.Overview#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#5)]
 [!code-csharp[Conceptual.Generics.Overview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#5)]
 [!code-vb[Conceptual.Generics.Overview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#5)]  
  
## <a name="advantages-and-disadvantages-of-generics"></a>Ventajas y desventajas de los genéricos
 Usar delegados y colecciones genéricas ofrece muchas ventajas:  
  
- Seguridad de tipos. Los genéricos trasladan al compilador la carga de la seguridad de tipos. No es necesario escribir código para comprobar el tipo de datos correcto porque se hace en tiempo de compilación. Se reduce la necesidad de conversión de tipos y la posibilidad de errores en tiempo de ejecución.  
  
- Menos código que, además, se reutiliza más fácilmente. No es necesario heredar de un tipo base y reemplazar a los miembros. Por ejemplo, <xref:System.Collections.Generic.LinkedList%601> está listo para su uso inmediato. Por ejemplo, puede crear una lista vinculada de cadenas con la siguiente declaración de variable:  
  
     [!code-cpp[HowToGeneric#24](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/source2.cpp#24)]
     [!code-csharp[HowToGeneric#24](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/source2.cs#24)]
     [!code-vb[HowToGeneric#24](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/source2.vb#24)]  
  
- Mejor rendimiento. Los tipos de colección genéricos suelen comportarse mejor en el almacenamiento y manipulación de tipos de valor porque no es necesario realizar una conversión boxing de los tipos de valor.  
  
- Los delegados genéricos permiten devoluciones de llamada con seguridad de tipos sin necesidad de crear varias clases de delegado. Por ejemplo, el delegado genérico <xref:System.Predicate%601> le permite crear un método que implementa sus propios criterios de búsqueda para un tipo concreto y utilizar su método con métodos del tipo <xref:System.Array> , como <xref:System.Array.Find%2A>, <xref:System.Array.FindLast%2A>y <xref:System.Array.FindAll%2A>.  
  
- Los genéricos optimizan el código generado dinámicamente. Cuando se utilizan genéricos con código generado dinámicamente, no es necesario generar el tipo. Esto aumenta el número de escenarios en los que puede utilizar métodos dinámicos ligeros en lugar de generar ensamblados completos. Para obtener más información, vea [Cómo: Definir y ejecutar métodos dinámicos](../../../docs/framework/reflection-and-codedom/how-to-define-and-execute-dynamic-methods.md) y <xref:System.Reflection.Emit.DynamicMethod>.  
  
 Las siguientes son algunas limitaciones de los genéricos:  
  
- Los tipos genéricos pueden derivarse de la mayoría de las clases base, como <xref:System.MarshalByRefObject> (y pueden utilizarse restricciones para exigir que los parámetros de tipo genérico se deriven de clases base como <xref:System.MarshalByRefObject>). Sin embargo, .NET Framework no admite los tipos genéricos enlazados a un contexto. Un tipo genérico puede derivarse de <xref:System.ContextBoundObject>, pero al intentar crear una instancia de dicho tipo, se genera una <xref:System.TypeLoadException>.  
  
- Las enumeraciones no pueden tener parámetros de tipo genérico. Una enumeración solo puede ser genérica a propósito (por ejemplo, porque está anidada en un tipo genérico definido mediante Visual Basic, C# o C++). Para más información, vea "Enumeraciones" en [Common Type System](../../../docs/standard/base-types/common-type-system.md).  
  
- Los métodos dinámicos ligeros no pueden ser genéricos.  
  
- En Visual Basic, C# y C++, no se pueden crear instancias de un tipo anidado incluido en un tipo genérico, a menos que los tipos se hayan asignado a los parámetros de tipo de todos los tipos envolventes. Dicho de otro modo: en la reflexión, un tipo anidado definido mediante estos lenguajes incluye los parámetros de tipo de todos sus tipos envolventes. Esto permite que los parámetros de tipo de tipos envolventes se usen en las definiciones de miembro de un tipo anidado. Para obtener más información, vea “Tipos anidados” en <xref:System.Type.MakeGenericType%2A>.  
  
    > [!NOTE]
    > Un tipo anidado definido mediante la emisión de código en un ensamblado dinámico o mediante el uso de [Ilasm.exe (Ensamblado de IL)](../../../docs/framework/tools/ilasm-exe-il-assembler.md) no necesita incluir los parámetros de tipo de sus tipos envolventes. Sin embargo, si no los incluye, los parámetros de tipo no estarán en el ámbito de la clase anidada.  
  
     Para obtener más información, vea “Tipos anidados” en <xref:System.Type.MakeGenericType%2A>.  

## <a name="class-library-and-language-support"></a>Biblioteca de clases y lenguajes compatibles  
 .NET ofrece una serie de clases de colección genérica en los espacios de nombres siguientes:  
  
- El espacio de nombres <xref:System.Collections.Generic> contiene la mayoría de los tipos de colección genéricos proporcionados por .NET, como las clases genéricas <xref:System.Collections.Generic.List%601> y <xref:System.Collections.Generic.Dictionary%602>.  
  
- El espacio de nombres <xref:System.Collections.ObjectModel> contiene tipos de colección genéricos adicionales, como la clase genérica <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, que son útiles para exponer modelos de objetos a los usuarios de las clases.  
  
 Las interfaces genéricas para implementar comparaciones de orden e igualdad se proporcionan en el espacio de nombres <xref:System> , junto con los tipos de delegado genérico para controladores de eventos, conversiones y predicados de búsqueda.  
  
 Se ha agregado compatibilidad con genéricos a los siguientes espacios de nombres: a <xref:System.Reflection> para examinar tipos y métodos genéricos; a <xref:System.Reflection.Emit> para emitir ensamblados dinámicos que contengan tipos y métodos genéricos; y a <xref:System.CodeDom> para generar gráficos de origen que incluyan genéricos.  
  
 Common language runtime proporciona nuevos opcode y prefijos para admitir tipos genéricos en el lenguaje intermedio de Microsoft (MSIL), incluidos <xref:System.Reflection.Emit.OpCodes.Stelem>, <xref:System.Reflection.Emit.OpCodes.Ldelem>, <xref:System.Reflection.Emit.OpCodes.Unbox_Any>, <xref:System.Reflection.Emit.OpCodes.Constrained>y <xref:System.Reflection.Emit.OpCodes.Readonly>.  
  
 Visual C++, C# y Visual Basic proporcionan compatibilidad completa para definir y utilizar genéricos. Para más información sobre la compatibilidad de lenguaje, consulte [Tipos genéricos en Visual Basic](../../visual-basic/programming-guide/language-features/data-types/generic-types.md), [Introducción a los genéricos](../../csharp/programming-guide/generics/index.md) e [Información general sobre genéricos en Visual C++](/cpp/windows/overview-of-generics-in-visual-cpp).

## <a name="nested-types-and-generics"></a>Genéricos y tipos anidados  
 Un tipo que está anidado en un tipo genérico puede depender de los parámetros de tipo del tipo genérico envolvente. Common language runtime considera que los tipos anidados son genéricos, aunque no tengan sus propios parámetros de tipo genérico. Cuando cree una instancia de un tipo anidado, especifique los argumentos de tipo para todos los tipos genéricos envolventes.  

## <a name="related-topics"></a>Temas relacionados  
  
|Título|Description|  
|-----------|-----------------|  
|[Colecciones genéricas en .NET](../../../docs/standard/generics/collections.md)|Describe las clases de colección genérica y otros tipos genéricos en .NET.|  
|[Delegados genéricos para manipular matrices y listas](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)|Describe los delegados genéricos para conversiones, predicados de búsqueda y acciones realizadas en los elementos de una matriz o colección.|  
|[Interfaces genéricas](../../../docs/standard/generics/interfaces.md)|Describe las interfaces genéricas que proporcionan funcionalidad común entre las familias de tipos genéricos.|  
|[Covarianza y contravarianza](../../../docs/standard/generics/covariance-and-contravariance.md)|Describe la covarianza y la contravarianza en los parámetros de tipo genérico.|  
|[Tipos de colección utilizados normalmente](../../../docs/standard/collections/commonly-used-collection-types.md)|Proporciona información de resumen sobre las características y escenarios de uso de los tipos de colección en .NET, incluidos los tipos genéricos.|  
|[Cuándo utilizar colecciones genéricas](../../../docs/standard/collections/when-to-use-generic-collections.md)|Describe las reglas generales para determinar cuándo utilizar los tipos de colección genéricos.|  
|[Definición de un tipo genérico con emisión de reflexión](../../../docs/framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md)|Explica cómo generar ensamblados dinámicos que incluyan métodos y tipos genéricos.|  
|[Tipos genéricos en Visual Basic](../../visual-basic/programming-guide/language-features/data-types/generic-types.md)|Describe los genéricos a los usuarios de Visual Basic e incluye temas sobre el uso y la definición de tipos genéricos.|  
|[Introducción a los genéricos](../../csharp/programming-guide/generics/index.md)|Proporciona información general sobre la definición y uso de tipos genéricos para usuarios de C#.|  
|[Información general sobre genéricos en Visual C++](/cpp/windows/overview-of-generics-in-visual-cpp)|Describe los genéricos a los usuarios de C++ e incluye las diferencias entre genéricos y plantillas.|  

## <a name="reference"></a>Referencia  
 <xref:System.Collections.Generic>  
  
 <xref:System.Collections.ObjectModel>  
  
 <xref:System.Reflection.Emit.OpCodes?displayProperty=nameWithType>  

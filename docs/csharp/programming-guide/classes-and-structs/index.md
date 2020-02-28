---
title: 'Clases y estructuras: Guía de programación de C#'
description: Describe el uso de clases y estructuras (struct) en C#.
ms.date: 01/17/2016
helpviewer_keywords:
- structs [C#], about structs
- classes [C#], overview
- C# language, structs
- C# language, objects
- objects [C#]
- C# language, classes
ms.assetid: cc39dbda-8754-423e-b5b1-16a1db0734c0
ms.openlocfilehash: afd9e688bd716375bafb370fad4af082a9498411
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "77673425"
---
# <a name="classes-and-structs-c-programming-guide"></a>Clases y estructuras (Guía de programación de C#)
Las clases (class) y estructuras (struct) son dos de las construcciones básicas de Common Type System en .NET Framework. Cada una de ellas es básicamente una estructura de datos que encapsula un conjunto de datos y comportamientos que forman un conjunto como una unidad lógica. Los datos y comportamientos son los *miembros* de la clase o estructura, e incluyen sus métodos, propiedades y eventos, entre otros elementos, como se muestra más adelante en este tema.  
  
 Una declaración de clase o estructura es como un plano que se utiliza para crear instancias u objetos en tiempo de ejecución. Si define una clase o estructura llamada `Person`, `Person` es el nombre del tipo. Si declara e inicializa una variable `p` de tipo `Person`, se dice que `p` es un objeto o instancia de `Person`. Se pueden crear varias instancias del mismo tipo `Person`, y cada instancia tiene diferentes valores en sus propiedades y campos.  
  
 Una clase es un tipo de referencia. Cuando se crea un objeto de la clase, la variable a la que se asigna el objeto contiene solo una referencia a esa memoria. Cuando la referencia de objeto se asigna a una nueva variable, la nueva variable hace referencia al objeto original. Los cambios realizados en una variable se reflejan en la otra variable porque ambas hacen referencia a los mismos datos.  
  
 Una estructura es un tipo de valor. Cuando se crea una estructura, la variable a la que se asigna la estructura contiene los datos reales de ella. Cuando la estructura se asigna a una nueva variable, se copia. Por lo tanto, la nueva variable y la variable original contienen dos copias independientes de los mismos datos. Los cambios realizados en una copia no afectan a la otra copia.  
  
 En general, las clases se utilizan para modelar comportamientos más complejos, o datos que se prevén modificar después de haber creado un objeto de clase. Las estructuras son más adecuadas para las estructuras de datos pequeñas que contienen principalmente datos que no se prevén modificar después de haber creado la estructura.  
  
 Para más información, vea [Clases](./classes.md), [Objectos](./objects.md) y [Tipos de estructura](../../language-reference/builtin-types/struct.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, `CustomClass` en el espacio de nombres `ProgrammingGuide` tiene tres miembros: un constructor de instancia, una propiedad denominada `Number` y un método denominado `Multiply`. El método `Main` de la clase `Program` crea una instancia (objeto) de `CustomClass`, y se puede acceder a la propiedad y al método del objeto mediante una notación de puntos.
  
 [!code-csharp[csProgGuideObjects#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/class1.cs#1)]  
  
## <a name="encapsulation"></a>Encapsulación  
 A veces se hace referencia a la *encapsulación* como el primer pilar o principio de la programación orientada a objetos. Según el principio de encapsulación, una clase o una estructura pueden especificar hasta qué punto se puede acceder a sus miembros para codificar fuera de la clase o la estructura. No se prevé el uso de los métodos y las variables fuera de la clase, o el ensamblado puede ocultarse para limitar el potencial de los errores de codificación o de los ataques malintencionados.  
  
 Para más información sobre las clases, vea [Clases](./classes.md) y [Objetos](./objects.md).  
  
### <a name="members"></a>Miembros  
 Todos los métodos, campos, constantes, propiedades y eventos deben declararse dentro de un tipo; se les denomina *miembros* del tipo. En C#, no hay métodos ni variables globales como en otros lenguajes. Incluso un punto de entrada del programa, el método `Main`, debe declararse dentro de una clase o estructura. La lista siguiente incluye los diversos tipos de miembros que se pueden declarar en una clase o estructura.  
  
- [Campos](./fields.md)  
  
- [Constantes](./constants.md)  
  
- [Propiedades](./properties.md)  
  
- [Métodos](./methods.md)  
  
- [Constructores](./constructors.md)  
  
- [Eventos](../events/index.md)  
  
- [Finalizadores](./destructors.md)  
  
- [Indizadores](../indexers/index.md)  
  
- [Operadores](../../language-reference/operators/index.md)  
  
- [Tipos anidados](./nested-types.md)  
  
### <a name="accessibility"></a>Accesibilidad  
 Algunos métodos y propiedades están diseñados para ser invocables y accesibles desde el código fuera de la clase o la estructura, lo que se conoce como *código de cliente*. Otros métodos y propiedades pueden estar indicados exclusivamente para utilizarse en la propia clase o estructura. Es importante limitar la accesibilidad del código, a fin de que solo el código de cliente previsto pueda acceder a él. Puede usar los modificadores de acceso [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) y [private protected](../../language-reference/keywords/private-protected.md) para especificar hasta qué punto los tipos y sus miembros son accesibles para el código de cliente. La accesibilidad predeterminada es `private`. Para obtener más información, consulte [Modificadores de acceso](./access-modifiers.md).  
  
### <a name="inheritance"></a>Herencia  
 Las clases (pero no las estructuras) admiten el concepto de herencia. Una clase que deriva de otra clase (la *clase base*) contiene automáticamente todos los miembros públicos, protegidos e internos de la clase base, salvo sus constructores y finalizadores. Para más información, vea [Herencia](./inheritance.md) y [Polimorfismo](./polymorphism.md).  
  
 Las clases pueden declararse como [abstract](../../language-reference/keywords/abstract.md), lo que significa que uno o varios de sus métodos no tienen ninguna implementación. Aunque no se pueden crear instancias de clases abstractas directamente, pueden servir como clases base para otras clases que proporcionan la implementación que falta. Las clases también pueden declararse como [sealed](../../language-reference/keywords/sealed.md) para evitar que otras clases hereden de ellas. Para más información, vea [Clases y miembros de clase abstractos y sellados](./abstract-and-sealed-classes-and-class-members.md).  
  
### <a name="interfaces"></a>Interfaces  
 Las clases y las estructuras pueden heredar varias interfaces. Heredar de una interfaz significa que el tipo implementa todos los métodos definidos en la interfaz. Para más información, vea [Interfaces](../interfaces/index.md).  
  
### <a name="generic-types"></a>Tipos genéricos  
 Las clases y estructuras pueden definirse con uno o varios parámetros de tipo. El código de cliente proporciona el tipo cuando crea una instancia del tipo. Por ejemplo, la clase <xref:System.Collections.Generic.List%601> del espacio de nombres <xref:System.Collections.Generic> se define con un parámetro de tipo. El código de cliente crea una instancia de `List<string>` o `List<int>` para especificar el tipo que contendrá la lista. Para más información, vea [Genéricos](../generics/index.md).  
  
### <a name="static-types"></a>Tipos estáticos  
 Las clases (pero no las estructuras) pueden declararse como [static](../../language-reference/keywords/static.md). Una clase estática puede contener solo miembros estáticos y no se puede crear una instancia de ellos con la palabra clave new. Una copia de la clase se carga en memoria cuando se carga el programa, y sus miembros son accesibles a través del nombre de clase. Las clases y estructuras pueden contener miembros estáticos. Para más información, vea [Clases estáticas y sus miembros](./static-classes-and-static-class-members.md).  
  
### <a name="nested-types"></a>Tipos anidados  
 Una clase o estructura se puede anidar dentro de otra clase o estructura. Para obtener más información, consulte [Tipos anidados](./nested-types.md).  
  
### <a name="partial-types"></a>Tipos parciales  
 Puede definir parte de una clase, estructura o método en un archivo de código y otra parte en un archivo de código independiente. Para más información, vea [Clases y métodos parciales](./partial-classes-and-methods.md).  
  
### <a name="object-initializers"></a>Inicializadores de objeto  
 Puede crear instancias de objetos de clase o estructura y de colecciones de objetos e iniciarlizarlos, sin llamar de forma explícita a su constructor. Para más información, vea [Inicializadores de objeto y de colección](./object-and-collection-initializers.md).  
  
### <a name="anonymous-types"></a>Tipos anónimos  
 En situaciones donde no es conveniente o necesario crear una clase con nombre, por ejemplo al rellenar una lista con estructuras de datos que no tiene que conservar o pasar a otro método, utilice los tipos anónimos. Para más información, vea [Tipos anónimos](./anonymous-types.md).  
  
### <a name="extension-methods"></a>Métodos de extensión.  
 Puede "extender" una clase sin crear una clase derivada mediante la creación de un tipo independiente cuyos métodos pueden llamarse como si pertenecieran al tipo original. Para más información, vea [Métodos de extensión](./extension-methods.md).  
  
### <a name="implicitly-typed-local-variables"></a>Variables locales con asignación implícita de tipos  
 Dentro de un método de clase o estructura, puede utilizar tipos implícitos para indicar al compilador que determine el tipo correcto en tiempo de compilación. Para más información, vea [Variables locales con asignación implícita de tipos](./implicitly-typed-local-variables.md).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)

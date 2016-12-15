---
title: "Clases y structs (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, clases"
  - "lenguaje C#, objetos"
  - "lenguaje C#, estructuras"
  - "clases [C#], información general"
  - "objetos [C#]"
  - "structs [C#], acerca de las estructuras"
ms.assetid: cc39dbda-8754-423e-b5b1-16a1db0734c0
caps.latest.revision: 48
caps.handback.revision: 48
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Clases y structs (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Las clases y structs son dos de las construcciones básicas del Common Type System \(CTS\) en .NET Framework.  Ambas son esencialmente un struct de datos que encapsula un conjunto de datos y comportamientos relacionados como una unidad lógica.  Los datos y comportamientos son los *miembros* de la clase o struct e incluyen sus métodos, propiedades, eventos, etc., tal como se enumeran más adelante en este tema.  
  
 Una declaración de clase o struct es como un plano que se utiliza para crear instancias u objetos en tiempo de ejecución.  Si define una clase o un struct llamado `Person`, `Person` es el nombre del tipo.  Si declara e inicializa una variable `p` de tipo `Person`, se dice que `p` es un objeto o una instancia de `Person`.  Se pueden crear varias instancias del mismo tipo `Person` y cada instancia puede tener diferentes valores en sus propiedades y campos.  
  
 Una clase es un tipo de referencia.  Cuando se crea un objeto de la clase, la variable a la que se asigna el objeto solo incluye una referencia a dicha memoria.  Cuando la referencia a objeto se asigna a una nueva variable, la nueva variable hace referencia al objeto original.  Los cambios realizados en una variable se reflejan en la otra variable porque ambas hacen referencia a los mismos datos.  
  
 Un struct es un tipo de valor.  Cuando se crea un struct, la variable a la que se asigna incluye los datos reales del struct.  Cuando el struct se asigna a una nueva variable, se copia.  La nueva variable y la variable original contienen por tanto dos copias independientes de los mismos datos.  Los cambios realizados en una copia no afectan a la otra copia.  
  
 En general, las clases se utilizan para modelar comportamiento más complejo o datos que se piensan modificar una vez creado un objeto de clase.  Los structs son más adecuadas para pequeñas estructuras de datos que contienen principalmente datos que no se piensan modificar una vez creado el struct.  
  
 Para obtener más información, vea [Clases](../../../csharp/programming-guide/classes-and-structs/classes.md), [Objetos](../../../csharp/programming-guide/classes-and-structs/objects.md) y [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).  
  
## Ejemplo  
 En el ejemplo siguiente, se define `MyCustomClass` con tres miembros en el nivel superior del espacio de nombres `ProgrammingGuide`.  Se crea una instancia \(objeto\) de `MyCustomClass` en el método `Main` de la clase `Program`. Para obtener acceso a los métodos y propiedades del objeto se utiliza la notación de punto.  
  
 [!code-cs[csProgGuideObjects#88](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/index_1.cs)]  
  
## Encapsulación  
 En ocasiones se hace referencia a la *encapsulación* como el primer pilar o principio de la programación orientada a objetos.  Según el principio de encapsulación, una clase o un struct puede especificar el nivel posible de acceso a cada uno de sus miembros en el código fuera de la clase o el struct.  Los métodos y variables que no se van a utilizar fuera de la clase o el ensamblado se pueden ocultar para limitar la posibilidad de errores de codificación o ataques malintencionadas.  
  
 Para obtener más información sobre las clases, vea [Clases](../../../csharp/programming-guide/classes-and-structs/classes.md) y [Objetos](../../../csharp/programming-guide/classes-and-structs/objects.md).  
  
### Members  
 Todos los métodos, campos, constantes, propiedades y eventos se deben declarar dentro de un tipo; estos elementos se denominan *miembros* del tipo.  En C\#, no existen variables ni métodos globales como en otros lenguajes.  Incluso el punto de entrada de un programa, el método `Main`, se debe declarar dentro de una clase o struct.  En la lista siguiente se incluyen los diversos tipos de miembros que pueden declararse en una clase o en un struct.  
  
-   [Campos](../../../csharp/programming-guide/classes-and-structs/fields.md)  
  
-   [Constantes](../../../csharp/programming-guide/classes-and-structs/constants.md)  
  
-   [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)  
  
-   [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Destructores](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
  
-   [Eventos](../../../csharp/programming-guide/events/index.md)  
  
-   [Indizadores](../../../csharp/programming-guide/indexers/index.md)  
  
-   [Operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
-   [Tipos anidados](../../../csharp/programming-guide/classes-and-structs/nested-types.md)  
  
### Accesibilidad  
 A algunos métodos y propiedades se les llama o se accede a ellos desde código fuera de su clase o struct, conocido como *código de cliente*.  Puede que otros métodos y propiedades solo se utilicen en la propia clase o struct.  Es importante limitar la accesibilidad del código para que solo el código de cliente previsto pueda llegar a él.  La accesibilidad del código de cliente a los tipos y sus miembros se especifica mediante los modificadores de acceso [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), `protected internal` y [private](../../../csharp/language-reference/keywords/private.md).  La accesibilidad predeterminada es `private`.  Para obtener más información, vea [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
### Herencia  
 Las clases \(pero no los structs\) admiten el concepto de herencia.  Una clase que deriva de otra clase \(la *clase base*\) contiene automáticamente todos los miembros públicos, protegidos e internos de la clase base, excepto sus constructores y destructores.  Para obtener más información, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md) y [Polimorfismo](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).  
  
 Las clases pueden declararse como [abstract](../../../csharp/language-reference/keywords/abstract.md), lo que significa que uno o varios de sus métodos no tienen ninguna implementación.  Aunque no se pueden crear instancias de las clases abstractas directamente, éstas pueden actuar como clases base de otras clases que proporcionan la implementación que falta.  Las clases también pueden declararse como [sealed](../../../csharp/language-reference/keywords/sealed.md) para impedir que otras clases hereden de ellas.  Para obtener más información, vea [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
### Interfaces  
 Las clases y los structs pueden heredar varias interfaces.  Heredar de una interfaz significa que el tipo implementa todos los métodos definidos en la interfaz.  Para obtener más información, vea [Interfaces](../../../csharp/programming-guide/interfaces/index.md).  
  
### Tipos genéricos  
 Las clases y los structs pueden definirse con uno o más parámetros de tipo.  El código cliente proporciona el tipo cuando crea una instancia del tipo.  Por ejemplo, la clase <xref:System.Collections.Generic.List%601> del espacio de nombres <xref:System.Collections.Generic> se define con un parámetro de tipo.  El código cliente crea una instancia de `List<string>` o `List<int>` para especificar el tipo que contendrá la lista.  Para obtener más información, vea [Genéricos](../../../csharp/programming-guide/generics/index.md).  
  
### Tipos estáticos  
 Las clases \(pero no los structs\) se pueden declarar como [estáticas](../../../csharp/language-reference/keywords/static.md).  Una clase estática solo puede contener miembros estáticos y no se pueden crear instancias de ésta con la palabra clave new.  Al cargarse el programa se carga una copia de la clase en la memoria y se obtiene acceso a sus miembros a través del nombre de la clase.  Tanto las clases como los structs pueden contener miembros estáticos.  Para obtener más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
### Tipos anidados  
 Una clase o un struct se pueden anidar en otra clase o struct.  Para obtener más información, vea [Tipos anidados](../../../csharp/programming-guide/classes-and-structs/nested-types.md).  
  
### Tipos parciales  
 Puede definir parte de una clase, struct o método en un archivo de código y otra parte en un archivo de código independiente.  Para obtener más información, vea [Clases y métodos parciales](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
### Inicializadores de objeto  
 Puede crear instancias y colecciones de objetos de clase o struct, e inicializarlos, sin llamar a su constructor explícitamente.  Para obtener más información, consulte [Inicializadores de objeto y colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
### Tipos anónimos  
 En situaciones en las que no es conveniente o necesario crear una clase con nombre, por ejemplo al rellenar una lista con estructuras de datos que no tiene que conservar o pasar a otro método, utilice los tipos anónimos.  Para obtener más información, consulte [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
### Métodos de extensión.  
 Puede "extender" una clase sin crear una clase derivada. Para ello, cree un tipo independiente en el que se pueda llamar a sus métodos como si pertenecieran al tipo original.  Para obtener más información, consulte [Métodos de extensión](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
### Variables locales tipificadas implícitamente  
 En un método de clase o struct, puede utilizar tipos implícitos para indicar al compilador que determine el tipo correcto en tiempo de compilación.  Para obtener más información, consulte [Variables locales con asignación implícita de tipos](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)
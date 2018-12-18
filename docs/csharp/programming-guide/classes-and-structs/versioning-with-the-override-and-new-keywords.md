---
title: 'Control de versiones con las palabras clave Override y New: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, versioning
- C# language, override and new
ms.assetid: 88247d07-bd0d-49e9-a619-45ccbbfdf0c5
ms.openlocfilehash: ddb34fd32d13224faed92bd8ba01933ca19c04a9
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241540"
---
# <a name="versioning-with-the-override-and-new-keywords-c-programming-guide"></a>Control de versiones con las palabras clave Override y New (Guía de programación de C#)
El lenguaje C# está diseñado para que las versiones entre clases [base](../../../csharp/language-reference/keywords/base.md) y derivadas de diferentes bibliotecas puedan evolucionar y mantener la compatibilidad con versiones anteriores. Esto significa, por ejemplo, que la introducción de un nuevo miembro en una [clase](../../../csharp/language-reference/keywords/class.md) base con el mismo nombre que un miembro de una clase derivada es totalmente compatible con C# y no lleva a un comportamiento inesperado. Además, implica que una clase debe declarar explícitamente si un método está pensado para reemplazar un método heredado o si se trata de un nuevo método que oculta un método heredado de nombre similar.  
  
 En C#, las clases derivadas pueden contener métodos con el mismo nombre que los métodos de clase base.  
  
-   El método de clase base debe definirse como [virtual](../../../csharp/language-reference/keywords/virtual.md).  
  
-   Si el método de la clase derivada no va precedido por las palabras clave [new](../../../csharp/language-reference/keywords/new.md) u [override](../../../csharp/language-reference/keywords/override.md), el compilador emite una advertencia y el método se comporta como si la palabra clave `new` estuviese presente.  
  
-   Si el método de la clase derivada va precedido de la palabra clave `new`, el método se define como independiente del método de la clase base.  
  
-   Si el método de la clase derivada va precedido de la palabra clave `override`, los objetos de la clase derivada llamarán a ese método y no al método de la clase base.  
  
-   El método de clase base puede llamarse desde dentro de la clase derivada mediante la palabra clave `base`.  
  
-   Las palabras clave `override`, `virtual` y `new` también pueden aplicarse a propiedades, indexadores y eventos.  
  
 De forma predeterminada, los métodos de C# no son virtuales. Si se declara un método como virtual, toda clase que hereda el método puede implementar su propia versión Para que un método sea virtual, se usa el modificador `virtual` en la declaración del método de la clase base. La clase derivada puede luego reemplazar el método base virtual mediante la palabra clave `override` u ocultar el método virtual en la clase base mediante la palabra clave `new`. Si no se especifican las palabras clave `override` o `new`, el compilador emite una advertencia y el método de la clase derivada oculta el método de la clase base.  
  
 Para demostrar esto en la práctica, supongamos por un momento que la compañía A ha creado una clase denominada `GraphicsClass`, que su programa usa. La siguiente es `GraphicsClass`:  
  
 [!code-csharp[csProgGuideInheritance#27](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_1.cs)]  
  
 Su compañía usa esta clase y usted la usa para derivar su propia clase, agregando un nuevo método:  
  
 [!code-csharp[csProgGuideInheritance#28](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_2.cs)]  
  
 La aplicación se usa sin problemas, hasta que la compañía A lanza una nueva versión de `GraphicsClass`, que es similar al código siguiente:  
  
 [!code-csharp[csProgGuideInheritance#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_3.cs)]  
  
 La nueva versión de `GraphicsClass` contiene ahora un método denominado `DrawRectangle`. Inicialmente, no sucede nada. La nueva versión sigue siendo compatible a nivel binario con la versión anterior. Cualquier software que haya implementado seguirá funcionando, aunque la nueva clase se instale en esos sistemas informáticos. Cualquier llamada existente al método `DrawRectangle` seguirá haciendo referencia a su versión en la clase derivada.  
  
 Pero en cuanto vuelva a compilar la aplicación con la nueva versión de `GraphicsClass`, recibirá una advertencia del compilador, CS0108. Esta advertencia le informa de que debe plantearse cómo quiere que el método `DrawRectangle` se comporte en la aplicación.  
  
 Si quiere que su método reemplace al nuevo método de clase base, use la palabra clave `override`:  
  
 [!code-csharp[csProgGuideInheritance#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_4.cs)]  
  
 La palabra clave `override` se asegura de que los objetos derivados de `YourDerivedGraphicsClass` usen la versión de la clase derivada de `DrawRectangle`. Los objetos derivados de `YourDerivedGraphicsClass` todavía pueden acceder a la versión de clase base `DrawRectangle` mediante la palabra clave base:  
  
 [!code-csharp[csProgGuideInheritance#44](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_5.cs)]  
  
 Si no quiere que el método reemplace al nuevo método de clase base, se aplican las consideraciones siguientes. Para evitar la confusión entre los dos métodos, puede cambiarle el nombre a su método. Esto puede ser un proceso lento y propenso a errores y no resultar práctico en algunos casos. Pero si el proyecto es relativamente pequeño, puede usar opciones de refactorización de Visual Studio para cambiar el nombre del método. Para obtener más información, vea [Refactoring Classes and Types (Class Designer)](/visualstudio/ide/refactoring-classes-and-types-class-designer) (Refactorización de clases y tipos [Diseñador de clases]).  
  
 También puede evitar la advertencia mediante la palabra clave `new` en la definición de clase derivada:  
  
 [!code-csharp[csProgGuideInheritance#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_6.cs)]  
  
 Con la palabra clave `new` se indica al compilador que su definición oculta la definición contenida en la clase base. Éste es el comportamiento predeterminado.  
  
## <a name="override-and-method-selection"></a>Selección de método y reemplazo  
 Cuando se llama a un método en una clase, el compilador de C# selecciona el mejor método para llamar si hay más de uno compatible con la llamada, como cuando hay dos métodos con el mismo nombre y parámetros que son compatibles con el parámetro pasado. Los métodos siguientes serían compatibles:  
  
 [!code-csharp[csProgGuideInheritance#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_7.cs)]  
  
 Cuando se llama a `DoWork` en una instancia de `Derived`, el compilador de C# intentará en primer lugar que la llamada sea compatible con las versiones de `DoWork` declaradas originalmente en `Derived`. Los métodos de reemplazo no se consideran como declarados en una clase, son nuevas implementaciones de un método que se declara en una clase base. Solo si el compilador de C# no puede hacer coincidir la llamada al método con un método original en `Derived`, intentará hacer coincidir la llamada con un método reemplazado con el mismo nombre y parámetros compatibles. Por ejemplo:  
  
 [!code-csharp[csProgGuideInheritance#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_8.cs)]  
  
 Dado que la variable `val` se puede convertir implícitamente en un valor doble, el compilador de C# llama a `DoWork(double)` en lugar de a `DoWork(int)`. Hay dos maneras de evitarlo. En primer lugar, evite declarar nuevos métodos con el mismo nombre que los métodos virtuales. En segundo lugar, puede indicar al compilador de C# que llame al método virtual haciendo que busque la lista de métodos de clase base mediante la conversión de la instancia de `Derived` a `Base`. Como el método es virtual, se llamará a la implementación de `DoWork(int)` en `Derived`. Por ejemplo:  
  
 [!code-csharp[csProgGuideInheritance#34](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_9.cs)]  
  
 Para obtener otros ejemplos de `new` y `override`, vea [Knowing When to Use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md) (Saber cuándo usar las palabras clave override y new [Guía de programación de C#]).  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)  
- [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md)

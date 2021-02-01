---
title: 'Utilizar constructores: Guía de programación de C#'
description: En este ejemplo se muestra cómo crear una instancia de una clase mediante el operador new en C#. El constructor simple se invoca después de asignar memoria para el nuevo objeto.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: 161c243f16f6705fa8fcf79360f92a74e4d0b27b
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899261"
---
# <a name="using-constructors-c-programming-guide"></a>Utilizar constructores (Guía de programación de C#)

Cuando se crea una [class](../../language-reference/keywords/class.md) o un [struct](../../language-reference/builtin-types/struct.md), se llama a su constructor. Los constructores tienen el mismo nombre que la class o el struct y suelen inicializar los miembros de datos del nuevo objeto.  
  
 En el ejemplo siguiente, una clase denominada `Taxi` se define mediante un constructor simple. Luego, se crea una instancia de la clase con el operador [new](../../language-reference/operators/new-operator.md). El constructor `Taxi` se invoca con el operador `new` inmediatamente después de asignar memoria para el nuevo objeto.  
  
 [!code-csharp[TaxiExample#1](snippets/using-constructors/Program.cs#1)]
  
 Un constructor que no toma ningún parámetro se denomina *constructor sin parámetros*. Los constructores sin parámetros se invocan cada vez que se crea una instancia de un objeto mediante el operador `new` y no se especifica ningún argumento en `new`. Para obtener más información, vea [Instance Constructors](./instance-constructors.md) (Constructores de instancias [Guía de programación de C#]).  
  
 A menos que la clase sea [static](../../language-reference/keywords/static.md), las clases sin constructores tienen un constructor público sin parámetros por el compilador de C# con el fin de habilitar la creación de instancias de clase. Para más información, vea [Clases estáticas y sus miembros](./static-classes-and-static-class-members.md).  
  
 Puede impedir que se cree una instancia de una clase convirtiendo el constructor en privado, de la manera siguiente:  
  
 [!code-csharp[PrivateConstructor#2](snippets/using-constructors/Program.cs#2)]
  
 Para obtener más información, vea [Private Constructors](./private-constructors.md) (Constructores privados [Guía de programación de C#]).  
  
 Los constructores de tipos [struct](../../language-reference/builtin-types/struct.md) son similares a los constructores de clases, pero `structs` no puede contener un constructor sin parámetros explícito porque el compilador proporciona uno automáticamente. Este constructor inicializa cada campo del `struct` en los [valores predeterminados](../../language-reference/builtin-types/default-values.md). Pero este constructor sin parámetros solo se invoca si las instancias de `struct` se crean con `new`. Por ejemplo, este código usa el constructor sin parámetros para <xref:System.Int32>, por lo que se tiene la certeza de que el entero se inicializa:  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 Si bien, el siguiente código genera un error del compilador porque no usa `new` y porque intenta usar un objeto que no se ha inicializado:  
  
```csharp  
int i;  
Console.WriteLine(i);  
```  
  
 También puede inicializar o asignar los objetos basados en `structs` (incluidos todos los tipos numéricos integrados) y luego usarlos como en el ejemplo siguiente:  
  
```csharp  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 Por lo que no es necesario llamar al constructor sin parámetros para un tipo de valor.  
  
 Tanto las clases como los `structs` pueden definir constructores que toman parámetros. Los constructores que toman parámetros deben llamarse mediante una instrucción `new` o [base](../../language-reference/keywords/base.md). Las clases y `structs` también pueden definir varios constructores y no es necesario definir un constructor sin parámetros. Por ejemplo:  
  
 [!code-csharp[EmployeeExample#3](snippets/using-constructors/Program.cs#3)]
  
 Esta clase se puede crear mediante cualquiera de las siguientes instrucciones:  
  
 [!code-csharp[InstantiatingEmployeeConstructors#4](snippets/using-constructors/Program.cs#4)]
  
 Un constructor puede usar la palabra clave `base` para llamar al constructor de una clase base. Por ejemplo:  
  
 [!code-csharp[ManagerInheritingEmployee#5](snippets/using-constructors/Program.cs#5)]
  
 En este ejemplo, se llama al constructor de la clase base antes de ejecutar el bloque del constructor. La palabra clave `base` puede usarse con o sin parámetros. Los parámetros del constructor se pueden usar como parámetros en `base` o como parte de una expresión. Para obtener más información, vea [base](../../language-reference/keywords/base.md).  
  
 En una clase derivada, si un constructor de clase base no se llama explícitamente con la palabra clave `base`, se llama implícitamente al constructor sin parámetros, si hay alguno. Esto significa que las siguientes declaraciones del constructor son en efecto iguales:  
  
 [!code-csharp[ManagerImplicitlyCallingParameterlessBaseConstructor#6](snippets/using-constructors/Program.cs#6)]
  
 [!code-csharp[ManagerExplicitlyCallingParameterlessBaseConstructor#7](snippets/using-constructors/Program.cs#7)]
  
 Si una clase base no proporciona un constructor sin parámetros, la clase derivada debe realizar una llamada explícita a un constructor base mediante `base`.  
  
 Un constructor puede invocar otro constructor en el mismo objeto mediante la palabra clave [this](../../language-reference/keywords/this.md). Igual que `base`, `this` puede usarse con o sin parámetros. Además, los parámetros del constructor están disponibles como parámetros en `this` o como parte de una expresión. Por ejemplo, el segundo constructor del ejemplo anterior se puede reescribir con `this`:  
  
 [!code-csharp[EmployeeCallingConstructorInSameClass#8](snippets/using-constructors/Program.cs#8)]
  
 El uso de la palabra clave `this` en el ejemplo anterior llama a este constructor:  
  
 [!code-csharp[ConstructorBeingCalledByThisKeyword#9](snippets/using-constructors/Program.cs#9)]
  
 Los constructores se pueden marcar como [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) o [private protected](../../language-reference/keywords/private-protected.md). Estos modificadores de acceso definen cómo los usuarios de la clase pueden construir la clase. Para obtener más información, consulte [Modificadores de acceso](./access-modifiers.md).  
  
 Un constructor puede declararse estático mediante la palabra clave [static](../../language-reference/keywords/static.md). Los constructores estáticos se llaman automáticamente, inmediatamente antes de acceder a los campos estáticos y, por lo general, se usan para inicializar miembros de clase estática. Para obtener más información, vea [Static Constructors](./static-constructors.md) (Constructores estáticos [Guía de programación de C#]).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  

Para obtener más información, vea las secciones [Constructores de instancia](~/_csharplang/spec/classes.md#instance-constructors) y [Constructores estáticos](~/_csharplang/spec/classes.md#static-constructors) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [Constructores](./constructors.md)
- [Finalizadores](./destructors.md)

---
description: 'Restricciones en el uso de los niveles de accesibilidad: Referencia de C#'
title: 'Restricciones en el uso de los niveles de accesibilidad: Referencia de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: 542e463e41c70f2e8aed5c20dc1294e296a88518
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137009"
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a>Restricciones en el uso de los niveles de accesibilidad (Referencia de C#)

Cuando especifique un tipo en una declaración, compruebe si el nivel de accesibilidad de este depende del nivel de accesibilidad de un miembro o de otro tipo. Por ejemplo, la clase base directa debe ser al menos igual de accesible que la clase derivada. Las siguientes declaraciones producen un error del compilador porque la clase base `BaseClass` es menos accesible que `MyClass`:

```csharp
class BaseClass {...}
public class MyClass: BaseClass {...} // Error
```

En la tabla siguiente se resumen las restricciones en los niveles de accesibilidad declarados.

|Context|Observaciones|
|-------------|-------------|
|[Clases](../../programming-guide/classes-and-structs/classes.md)|La clase base directa de un tipo de clase debe ser al menos igual de accesible que el propio tipo de clase.|
|[Interfaces](../../programming-guide/interfaces/index.md)|Las interfaces base explícitas de un tipo de interfaz deben ser al menos igual de accesibles que el propio tipo de interfaz.|
|[Delegados](../../programming-guide/delegates/index.md)|El tipo de valor devuelto y los tipos de parámetros de un tipo de delegado deben ser al menos igual de accesibles que el propio tipo de delegado.|
|[Constantes](../../programming-guide/classes-and-structs/constants.md)|El tipo de una constante debe ser al menos igual de accesible que la propia constante.|
|[Campos](../../programming-guide/classes-and-structs/fields.md)|El tipo de un campo debe ser al menos igual de accesible que el propio campo.|
|[Métodos](../../programming-guide/classes-and-structs/methods.md)|El tipo de valor devuelto y los tipos de parámetros de un método deben ser al menos igual de accesibles que el propio método.|
|[Propiedades](../../programming-guide/classes-and-structs/properties.md)|El tipo de una propiedad debe ser al menos igual de accesible que la misma propiedad.|
|[Eventos](../../programming-guide/events/index.md)|El tipo de un evento debe ser al menos igual de accesible que el propio evento.|
|[Indizadores](../../programming-guide/indexers/index.md)|Los tipos de parámetro y el tipo de un indexador deben ser al menos igual de accesibles que el propio indexador.|
|[Operadores](../operators/index.md)|El tipo de valor devuelto y los tipos de parámetro de un operador deben ser al menos igual de accesibles que el propio operador.|
|[Constructores](../../programming-guide/classes-and-structs/constructors.md)|Los tipos de parámetro de un constructor deben ser al menos igual de accesibles que el propio constructor.|

## <a name="example"></a>Ejemplo

El siguiente ejemplo contiene declaraciones erróneas de diferentes tipos. El comentario que sigue a cada declaración indica el error del compilador previsto.

```csharp
// Restrictions on Using Accessibility Levels
// CS0052 expected as well as CS0053, CS0056, and CS0057
// To make the program work, change access level of both class B
// and MyPrivateMethod() to public.

using System;

// A delegate:
delegate int MyDelegate();

class B
{
    // A private method:
    static int MyPrivateMethod()
    {
        return 0;
    }
}

public class A
{
    // Error: The type B is less accessible than the field A.myField.
    public B myField = new B();

    // Error: The type B is less accessible
    // than the constant A.myConst.
    public readonly B myConst = new B();

    public B MyMethod()
    {
        // Error: The type B is less accessible
        // than the method A.MyMethod.
        return new B();
    }

    // Error: The type B is less accessible than the property A.MyProp
    public B MyProp
    {
        set
        {
        }
    }

    MyDelegate d = new MyDelegate(B.MyPrivateMethod);
    // Even when B is declared public, you still get the error:
    // "The parameter B.MyPrivateMethod is not accessible due to
    // protection level."

    public static B operator +(A m1, B m2)
    {
        // Error: The type B is less accessible
        // than the operator A.operator +(A,B)
        return new B();
    }

    static void Main()
    {
        Console.Write("Compiled successfully");
    }
}
```

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Modificadores de acceso](access-modifiers.md)
- [Dominio de accesibilidad](accessibility-domain.md)
- [Niveles de accesibilidad](accessibility-levels.md)
- [Modificadores de acceso](../../programming-guide/classes-and-structs/access-modifiers.md)
- [public](public.md)
- [private](private.md)
- [protected](protected.md)
- [internal](internal.md)

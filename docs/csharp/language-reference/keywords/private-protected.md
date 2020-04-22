---
title: 'private protected: Referencia de C#'
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 03fa90582d096919f2e6546fae2fde28e486fe41
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463051"
---
# <a name="private-protected-c-reference"></a>private protected (Referencia de C#)

La combinación de palabras claves `private protected` es un modificador de acceso de miembro. Los miembros private protected están accesibles para los tipos que se deriven de la clase contenedora, pero solo desde dentro del ensamblado correspondiente que lo contenga. Para obtener una comparación de `private protected` con los demás modificadores de acceso, vea [Niveles de accesibilidad](accessibility-levels.md).

> [!NOTE]
> El modificador de acceso `private protected` es válido en C# versión 7.2 y versiones posteriores.

## <a name="example"></a>Ejemplo

Se puede tener acceso a un miembro private protected de una clase base desde tipos derivados en el ensamblado que lo contiene solo si el tipo estático de la variable es el tipo de clase derivada. Por ejemplo, vea el siguiente segmento de código:

```csharp
public class BaseClass
{
    private protected int myValue = 0;
}

public class DerivedClass1 : BaseClass
{
    void Access()
    {
        var baseObject = new BaseClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 5;

        // OK, accessed through the current derived class instance
        myValue = 5;
    }
}
```

```csharp
// Assembly2.cs
// Compile with: /reference:Assembly1.dll
class DerivedClass2 : BaseClass
{
    void Access()
    {
        // Error CS0122, because myValue can only be
        // accessed by types in Assembly1
        // myValue = 10;
    }
}
```

Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly2.cs`.
El primer archivo contiene una clase base pública, `BaseClass`, y un tipo derivado de ella, `DerivedClass1`. `BaseClass` posee un miembro private protected, `myValue`, al que `DerivedClass1` intenta tener acceso de dos maneras. El primer intento de acceso a `myValue` a través de una instancia de `BaseClass` generará un error. En cambio, el intento de usarlo como un miembro heredado en `DerivedClass1` se realizará correctamente.

En el segundo archivo, un intento de tener acceso a `myValue` como un miembro heredado de `DerivedClass2` generará un error, ya que solo está accesible para los tipos derivados en Assembly1.

Si `Assembly1.cs` contiene un elemento <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> que asigna un nombre a `Assembly2`, la clase derivada `DerivedClass1` tendrá acceso a los miembros `private protected` declarados en `BaseClass`. `InternalsVisibleTo` hace que los miembros `private protected` sean visibles para las clases derivadas en otros ensamblados.

Los miembros de struct no pueden ser `private protected`, porque los structs no se heredan.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Modificadores de acceso](access-modifiers.md)
- [Niveles de accesibilidad](accessibility-levels.md)
- [Modificadores](index.md)
- [public](public.md)
- [private](private.md)
- [internal](internal.md)
- [Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100)) (Problemas de seguridad de palabras clave virtuales internas)

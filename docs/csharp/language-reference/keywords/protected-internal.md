---
title: 'protected internal: Referencia de C#'
ms.custom: seodec18
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: ddfefa2a0bb145aa49a60f06a40725d2706cecb5
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661656"
---
# <a name="protected-internal-c-reference"></a>protected internal (Referencia de C#)

La combinación de palabras claves `protected internal` es un modificador de acceso de miembro. Se puede obtener acceso a un miembro protected internal desde el ensamblado actual o desde tipos que se deriven de la clase contenedora. Para obtener una comparación de `protected internal` con los demás modificadores de acceso, vea [Niveles de accesibilidad](accessibility-levels.md).

## <a name="example"></a>Ejemplo

Se puede obtener acceso a un miembro protected internal de una clase base desde cualquier tipo de ensamblado que lo contenga. También estará accesible en una clase derivada ubicada en otro ensamblado, pero solo si el acceso se produce a través de una variable del tipo de clase derivada. Por ejemplo, vea el siguiente segmento de código:

```csharp
// Assembly1.cs
// Compile with: /target:library
public class BaseClass
{
   protected internal int myValue = 0;
}

class TestAccess
{
    void Access()
    {
        var baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}
```

```csharp
// Assembly2.cs
// Compile with: /reference:Assembly1.dll
class DerivedClass : BaseClass
{
    static void Main()
    {
        var baseObject = new BaseClass();
        var derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10;

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
}
```

Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly2.cs`.
El primer archivo contiene una clase base interna, `BaseClass`, y otra clase, `TestAccess`. `BaseClass` posee un miembro protected internal (`myValue`), al que se obtiene acceso por medio del tipo `TestAccess`.
En el segundo archivo, un intento de tener acceso a `myValue` a través de una instancia de `BaseClass` generará un error, mientras que un acceso a este miembro a través de una instancia de una clase derivada (`DerivedClass`) se realizará correctamente.

Los miembros de struct no pueden ser `protected internal`, porque los structs no se heredan.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Modificadores de acceso](access-modifiers.md)
- [Niveles de accesibilidad](accessibility-levels.md)
- [Modificadores](modifiers.md)
- [public](public.md)
- [private](private.md)
- [internal](internal.md)
- [Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100)) (Problemas de seguridad de palabras clave virtuales internas)

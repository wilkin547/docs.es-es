---
title: 'internal: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
ms.openlocfilehash: e5a5ca18828b689241abbb6d80c5adc51efb073c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173606"
---
# <a name="internal-c-reference"></a>internal (Referencia de C#)
La palabra clave `internal` es un [modificador de acceso](./access-modifiers.md) para tipos y miembros de tipo.
  
 > Esta página trata sobre el modificador de acceso `internal`. La palabra clave `internal` también forma parte del modificador de acceso [`protected internal`](./protected-internal.md).
  
Solo se puede tener acceso a los tipos internos o los miembros desde los archivos del mismo ensamblado, como en este ejemplo:  
  
```csharp  
public class BaseClass
{  
    // Only accessible within the same assembly.
    internal static int x = 0;
}  
```  

 Para obtener una comparación de `internal` con los demás modificadores de acceso, vea [Niveles de accesibilidad](./accessibility-levels.md) y [Modificadores de acceso](../../programming-guide/classes-and-structs/access-modifiers.md).  
  
 Para más información sobre los ensamblados, consulte [Ensamblados en .NET](../../../standard/assembly/index.md).  
  
 Un uso común del acceso interno se da en el desarrollo basado en componentes porque permite que un grupo de componentes cooperen de manera privada sin estar expuesto al resto del código de la aplicación. Por ejemplo, un marco para crear interfaces gráficas de usuario podría proporcionar las clases `Control` y `Form` que cooperan mediante miembros con acceso interno. Como estos miembros son internos, no se exponen al código que usa el marco de trabajo.  
  
 Es un error hacer referencia a un tipo o miembro con acceso interno fuera del ensamblado en el que se definió.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly1_a.cs`. El primer archivo contiene una clase base interna, `BaseClass`. En el segundo archivo, un intento de crear una instancia de `BaseClass` producirá un error.  
  
```csharp  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass
{  
   public static int intM = 0;  
}  
```  
  
```csharp  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess
{  
   static void Main()
   {  
      var myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, use los mismos archivos usados en el ejemplo 1 y cambie el nivel de accesibilidad de `BaseClass` a `public`. Cambie también el nivel de accesibilidad del miembro `intM` a `internal`. En este caso, se puede crear una instancia de la clase, pero no se puede tener acceso al miembro interno.  
  
```csharp  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass
{  
   internal static int intM = 0;  
}  
```  
  
```csharp  
// Assembly2_a.cs  
// Compile with: /reference:Assembly2.dll  
public class TestAccess
{  
   static void Main()
   {  
      var myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  

Para obtener más información, vea la sección [Accesibilidad declarada](~/_csharplang/spec/basic-concepts.md#declared-accessibility) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](./index.md)
- [Modificadores de acceso](./access-modifiers.md)
- [Niveles de accesibilidad](./accessibility-levels.md)
- [Modificadores](index.md)
- [public](./public.md)
- [private](./private.md)
- [protected](./protected.md)

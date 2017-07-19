---
title: internal (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- internal_CSharpKeyword
- internal
dev_langs:
- CSharp
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6b50c4c2a6e545e0313beb0450d9ca5ff170ad05
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="internal-c-reference"></a>internal (Referencia de C#)
La palabra clave `internal` es un [modificador de acceso](../../../csharp/language-reference/keywords/access-modifiers.md) para tipos y miembros de tipo. Solo se puede tener acceso a los tipos internos o los miembros desde los archivos del mismo ensamblado, como en este ejemplo:  
  
```  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  
  
 Se puede obtener acceso a los tipos o miembros que tienen el modificador de acceso `protected internal` desde el ensamblado actual o desde tipos que se derivan de la clase contenedora.  
  
 Para obtener una comparación de `internal` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) y [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Para más información sobre los ensamblados, vea [Ensamblados y caché global de ensamblados](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).  
  
 Un uso común del acceso interno se da en el desarrollo basado en componentes porque permite que un grupo de componentes cooperen de manera privada sin estar expuesto al resto del código de la aplicación. Por ejemplo, un marco para crear interfaces gráficas de usuario podría proporcionar las clases `Control` y `Form` que cooperan mediante miembros con acceso interno. Como estos miembros son internos, no se exponen al código que usa el marco de trabajo.  
  
 Es un error hacer referencia a un tipo o miembro con acceso interno fuera del ensamblado en el que se definió.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly1`_`a.cs`. El primer archivo contiene una clase base interna, `BaseClass`. En el segundo archivo, un intento de crear una instancia de `BaseClass` producirá un error.  
  
```  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass   
{  
   public static int intM = 0;  
}  
```  
  
```  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, use los mismos archivos usados en el ejemplo 1 y cambie el nivel de accesibilidad de `BaseClass` a `public`. Cambie también el nivel de accesibilidad del miembro `IntM` a `internal`. En este caso, se puede crear una instancia de la clase, pero no se puede tener acceso al miembro interno.  
  
```  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   internal static int intM = 0;  
}  
```  
  
```  
// Assembly2_a.cs  
// Compile with: /reference:Assembly1.dll  
public class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)

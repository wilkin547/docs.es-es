---
title: protected internal (referencia de C#)
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: f9004a5e8d65179c9ff2e30688e63c14c95ab431
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="protected-internal-c-reference"></a>protected internal (referencia de C#)
El `protected internal` combinación de palabra clave es un modificador de acceso de miembro. Un miembro protected internal es accesible desde el ensamblado actual o desde tipos que se derivan de la clase contenedora. Para obtener una comparación de `protected internal` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md). 
   
## <a name="example"></a>Ejemplo  
 Un miembro interno protegido de una clase base es accesible desde cualquier tipo de ensamblado que lo contiene. También es accesible en una clase derivada que se encuentra en otro ensamblado sólo si el acceso se produce a través de una variable del tipo de clase derivada. Por ejemplo, vea el siguiente segmento de código:  

```
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
        BaseClass baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}  
```  
  
```  
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass : BaseClass   
{  
    static void Main()
    {
        BaseClass baseObject = new BaseClass();
        DerivedClass derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10; 

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
} 
```  
 Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly2.cs`. El primer archivo contiene una clase base pública, `BaseClass`y otra clase, `TestAccess`. `BaseClass`posee un miembro protected internal, `myValue`, que se obtiene acceso a la `TestAccess` tipo. En el segundo archivo, un intento para tener acceso a `myValue` a través de una instancia de `BaseClass` generará un error, mientras que un acceso a este miembro a través de una instancia de una clase derivada, `DerivedClass` se realizará correctamente. 

 Los miembros de estructura no pueden ser `protected internal` porque el struct no puede heredarse.  
  
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
 [internal](../../../csharp/language-reference/keywords/internal.md)   
 [Cuestiones de seguridad para palabras clave virtuales internas](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))

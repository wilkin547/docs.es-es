---
title: privado protegido (referencia de C#)
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: 5f7abd2569d5bad5af64161042e4e5d21e741c8c
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="private-protected-c-reference"></a>privado protegido (referencia de C#)
El `private protected` combinación de palabra clave es un modificador de acceso de miembro. Un miembro protegido privado es accesible por tipos derivados de la clase contenedora, pero sólo dentro de su ensamblado que lo contiene. Para obtener una comparación de `private protected` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md). 
   
## <a name="example"></a>Ejemplo  
 Un miembro privado protegido de una clase base es accesible desde tipos derivados en su ensamblado de contenedor solo si el tipo estático de la variable es el tipo de clase derivada. Por ejemplo, vea el siguiente segmento de código:  
  
 ```
 // Assembly1.cs  
 // Compile with: /target:library  
 public class BaseClass
 {
     private protected int myValue = 0;
 }
 
 public class DerivedClass1 : BaseClass
 {
     void Access()
     {
         BaseClass baseObject = new BaseClass();
 
         // Error CS1540, because myValue can only be accessed by
         // classes derived from BaseClass.
         // baseObject.myValue = 5;  
 
         // OK, accessed through the current derived class instance
         myValue = 5;
     }
 }
```  
  
```  
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
 Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly2.cs`. El primer archivo contiene una clase base pública, `BaseClass`y un tipo derivado de éste, `DerivedClass1`. `BaseClass`posee un miembro privado protegido, `myValue`, que `DerivedClass1` intenta tener acceso a de dos maneras. El primer intento de obtener acceso a `myValue` a través de una instancia de `BaseClass` generará un error. Sin embargo, el intento de usar como un miembro heredado en `DerivedClass1` se realizará correctamente.
En el segundo archivo, un intento para tener acceso a `myValue` como un miembro heredado de `DerivedClass2` generará un error, ya que solo es accesible por tipos derivados en ensamblado1. 

 Los miembros de estructura no pueden ser `private protected` porque el struct no puede heredarse.  
  
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

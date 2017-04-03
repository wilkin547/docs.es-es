---
title: Restricciones en el uso de los niveles de accesibilidad (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
caps.latest.revision: 21
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 51b399993008a1a3ce61679cdccc3e5e7bf25354
ms.lasthandoff: 03/13/2017

---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a>Restricciones en el uso de los niveles de accesibilidad (Referencia de C#)
Cuando especifique un tipo en una declaración, compruebe si el nivel de accesibilidad de este depende del nivel de accesibilidad de un miembro o de otro tipo. Por ejemplo, la clase base directa debe ser al menos igual de accesible que la clase derivada. Las siguientes declaraciones producen un error del compilador porque la clase base `BaseClass` es menos accesible que `MyClass`:  
  
```  
class BaseClass {...}  
public class MyClass: BaseClass {...} // Error  
```  
  
 En la tabla siguiente se resumen las restricciones en los niveles de accesibilidad declarados.  
  
|Contexto|Comentarios|  
|-------------|-------------|  
|[Clases](../../../csharp/programming-guide/classes-and-structs/classes.md)|La clase base directa de un tipo de clase debe ser al menos igual de accesible que el propio tipo de clase.|  
|[Interfaces](../../../csharp/programming-guide/interfaces/index.md)|Las interfaces base explícitas de un tipo de interfaz deben ser al menos igual de accesibles que el propio tipo de interfaz.|  
|[Delegados](../../../csharp/programming-guide/delegates/index.md)|El tipo de valor devuelto y los tipos de parámetros de un tipo de delegado deben ser al menos igual de accesibles que el propio tipo de delegado.|  
|[Constantes](../../../csharp/programming-guide/classes-and-structs/constants.md)|El tipo de una constante debe ser al menos igual de accesible que la propia constante.|  
|[Campos](../../../csharp/programming-guide/classes-and-structs/fields.md)|El tipo de un campo debe ser al menos igual de accesible que el propio campo.|  
|[Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)|El tipo de valor devuelto y los tipos de parámetros de un método deben ser al menos igual de accesibles que el propio método.|  
|[Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)|El tipo de una propiedad debe ser al menos igual de accesible que la misma propiedad.|  
|[Eventos](../../../csharp/programming-guide/events/index.md)|El tipo de un evento debe ser al menos igual de accesible que el propio evento.|  
|[Indizadores](../../../csharp/programming-guide/indexers/index.md)|Los tipos de parámetro y el tipo de un indexador deben ser al menos igual de accesibles que el propio indexador.|  
|[Operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md)|El tipo de valor devuelto y los tipos de parámetro de un operador deben ser al menos igual de accesibles que el propio operador.|  
|[Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)|Los tipos de parámetro de un constructor deben ser al menos igual de accesibles que el propio constructor.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo contiene declaraciones erróneas de diferentes tipos. El comentario que sigue a cada declaración indica el error del compilador previsto.  
  
```  
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
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md)   
 [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)

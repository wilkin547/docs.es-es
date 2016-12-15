---
title: "Restricciones en el uso de los niveles de accesibilidad (Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "modificadores de acceso [C#], restricciones de nivel de accesibilidad"
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Restricciones en el uso de los niveles de accesibilidad (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Cuando se especifica un tipo en una declaración, compruebe si el nivel de accesibilidad del tipo es dependiente del nivel de accesibilidad de un miembro o de otro tipo.  Por ejemplo, la clase base directa debe ser al menos tan accesible como la clase derivada.  Las siguientes declaraciones producirán un error del compilador, ya que la clase base `BaseClass` es menos accesible que `MyClass`:  
  
```  
class BaseClass {...}  
public class MyClass: BaseClass {...} // Error  
```  
  
 La siguiente tabla resume las restricciones de uso de los niveles de accesibilidad declarados.  
  
|Contexto|Comentarios|  
|--------------|-----------------|  
|[Clases](../../../csharp/programming-guide/classes-and-structs/classes.md)|La clase base directa de un tipo de clase debe ser al menos tan accesible como el propio tipo de clase.|  
|[Interfaces](../../../csharp/programming-guide/interfaces/index.md)|Las interfaces base explícitas de un tipo de interfaz deben ser al menos tan accesibles como el propio tipo de interfaz.|  
|[Delegados](../../../csharp/programming-guide/delegates/index.md)|El tipo de valor devuelto y los tipos de los parámetros de un tipo delegado deben ser al menos tan accesibles como el propio tipo delegado.|  
|[Constantes](../../../csharp/programming-guide/classes-and-structs/constants.md)|El tipo de una constante debe ser al menos tan accesible como la propia constante.|  
|[Campos](../../../csharp/programming-guide/classes-and-structs/fields.md)|El tipo de un campo debe ser al menos tan accesible como el propio campo.|  
|[Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)|El tipo de valor devuelto y los tipos de parámetros de un método deben ser al menos tan accesibles como el propio método.|  
|[Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)|El tipo de una propiedad debe ser al menos tan accesible como la misma propiedad.|  
|[Eventos](../../../csharp/programming-guide/events/index.md)|El tipo de un evento debe ser al menos tan accesible como el propio evento.|  
|[Indizadores](../../../csharp/programming-guide/indexers/index.md)|El tipo y los tipos de parámetros de un indizador deben ser al menos tan accesibles como el propio indizador.|  
|[Operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md)|El tipo de valor devuelto y los tipos de parámetros de un operador deben ser al menos tan accesibles como el propio operador.|  
|[Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)|Los tipos de parámetros de un constructor deben ser al menos tan accesibles como el propio constructor.|  
  
## Ejemplo  
 El siguiente ejemplo contiene declaraciones erróneas de diferentes tipos.  El comentario que sigue a cada declaración indica el error esperado del compilador.  
  
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
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md)   
 [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)
---
title: "private (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "private_CSharpKeyword"
  - "private"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "private (palabra clave) [C#]"
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# private (Referencia de C#)
La palabra clave `private` es un modificador de acceso de miembros.  El acceso de tipo private corresponde al nivel de acceso más restrictivo.  Los miembros privados sólo son accesibles dentro del cuerpo de la clase o struct en los que se declaran, como en el siguiente ejemplo.  
  
```  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  
  
 Los tipos anidados del mismo cuerpo también pueden tener acceso a esos miembros privados.  
  
 Hacer referencia a un miembro privado fuera de la clase o struct en los que se declara produce un error de compilación.  
  
 Para obtener una comparación de `private` con el resto de los modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) y [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
## Ejemplo  
 En este ejemplo, la clase `Employee` contiene dos miembros de datos privados, `name` y `salary`.  Como miembros privados, sólo pueden tener acceso a ellos los métodos miembro.  Los métodos públicos denominados `GetName` y `Salary` se agregan para permitir un acceso controlado a los miembros privados.  Se obtiene acceso al miembro `name` a través de un método público y al miembro `salary` a través de una propiedad pública de sólo lectura.  \(Vea [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md) para obtener más información\).  
  
 [!code-cs[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#10)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)
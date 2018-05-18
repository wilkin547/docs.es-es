---
title: private (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: 26eab2912923c9fcae1ce930bd5b59a2740d500e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="private-c-reference"></a>private (Referencia de C#)
La palabra clave `private` es un modificador de acceso de miembro. 
   
 > Esta página trata sobre el modificador de acceso `private`. La palabra clave `private` también forma parte del modificador de acceso [`private protected`](./private-protected.md).
  
El acceso privado es el nivel de acceso menos permisivo. Los miembros privados solo son accesibles dentro del cuerpo de la clase o el struct en el que se declaran, como en este ejemplo:  
  
```  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  

 Los tipos anidados en el mismo cuerpo también pueden tener acceso a los miembros privados.  
  
 Hacer referencia a un miembro privado fuera de la clase o el struct en el que se declara es un error en tiempo de compilación.  
  
 Para obtener una comparación de `private` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) y [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la clase `Employee` contiene dos miembros de datos privados, `name` y `salary`. Como miembros privados, solo pueden tener acceso a ellos los métodos de miembro. Los métodos públicos denominados `GetName` y `Salary` se agregan para permitir un acceso controlado a los miembros privados. Se tiene acceso al miembro `name` a través de un método público, mientras que se tiene acceso al miembro `salary` a través de una propiedad pública de solo lectura. (Para obtener más información, vea [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)).  
  
 [!code-csharp[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]  
  
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
 [protected](../../../csharp/language-reference/keywords/protected.md)  
 [internal](../../../csharp/language-reference/keywords/internal.md)

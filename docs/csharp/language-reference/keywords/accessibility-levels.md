---
title: Niveles de accesibilidad (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: 19
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
ms.openlocfilehash: 30220e92e55ac6101cf8fedd8920755cd25978bd
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="accessibility-levels-c-reference"></a>Niveles de accesibilidad (Referencia de C#)
Use los modificadores de acceso [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md) para especificar uno de los siguientes niveles de accesibilidad declarada para miembros.  
  
|Accesibilidad declarada|Significado|  
|----------------------------|-------------|  
|`public`|El acceso no está restringido.|  
|`protected`|El acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora.|  
|`internal`|El acceso está limitado al ensamblado actual.|  
|`protected` `internal`|El acceso está limitado al ensamblado actual o a los tipos derivados de la clase contenedora.|  
|`private`|El acceso está limitado al tipo contenedor.|  
  
 Solo se permite un modificador de acceso para un miembro o tipo, excepto cuando se usa la combinación `protected` `internal`.  
  
 No se permiten modificadores de acceso en espacios de nombres. Los espacios de nombres no tienen restricciones de acceso.  
  
 En función del contexto en el que se produce una declaración de miembro, solo se permiten ciertas accesibilidades declaradas. Si no se especifica ningún modificador de acceso en una declaración de miembro, se usa una accesibilidad predeterminada.  
  
 Los tipos de nivel superior, que no están anidados en otros tipos, solo pueden tener una accesibilidad `internal` o `public`. La accesibilidad predeterminada para estos tipos es `internal`.  
  
 Los tipos anidados, que son miembros de otros tipos, pueden tener accesibilidades declaradas como se indica en la tabla siguiente.  
  
|Miembros de|Accesibilidad de miembro predeterminada|Accesibilidad declarada permitida del miembro|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|Ninguna|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected` `internal`|  
|`interface`|`public`|Ninguna|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 La accesibilidad de un tipo anidado depende de su [dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md), que viene determinado por la accesibilidad declarada del miembro y el dominio de accesibilidad del tipo contenedor inmediato. Sin embargo, el dominio de accesibilidad de un tipo anidado no puede superar al del tipo contenedor.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md)   
 [Restricciones en el uso de los niveles de accesibilidad](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)   
 [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)

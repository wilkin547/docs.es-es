---
title: Niveles de accesibilidad (Referencia de C#)
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: 4679fd2564454e7f1ade5cb4813729b65f433012
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44194764"
---
# <a name="accessibility-levels-c-reference"></a>Niveles de accesibilidad (Referencia de C#)

Use los modificadores de acceso `public`, `protected`, `internal` o `private` para especificar uno de los siguientes niveles de accesibilidad declarada para miembros.  
  
|Accesibilidad declarada|Significado|  
|----------------------------|-------------|  
|[`public`](public.md)|El acceso no está restringido.|  
|[`protected`](protected.md)|El acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora.|  
|[`internal`](internal.md)|El acceso está limitado al ensamblado actual.|  
|[`protected internal`](protected-internal.md)|El acceso está limitado al ensamblado actual o a los tipos derivados de la clase contenedora.|  
|[`private`](private.md)|El acceso está limitado al tipo contenedor.|  
|[`private protected`](private-protected.md)|El acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora que hay en el ensamblado actual. Disponible desde la versión C# 7.2. |  
  
 Solo se permite un modificador de acceso para un miembro o tipo, excepto cuando se usan las combinaciones `protected internal` o `private protected`.  
  
 No se permiten modificadores de acceso en espacios de nombres. Los espacios de nombres no tienen restricciones de acceso.  
  
 En función del contexto en el que se produce una declaración de miembro, solo se permiten ciertas accesibilidades declaradas. Si no se especifica ningún modificador de acceso en una declaración de miembro, se usa una accesibilidad predeterminada.  
  
 Los tipos de nivel superior, que no están anidados en otros tipos, solo pueden tener una accesibilidad `internal` o `public`. La accesibilidad predeterminada para estos tipos es `internal`.  
  
 Los tipos anidados, que son miembros de otros tipos, pueden tener accesibilidades declaradas como se indica en la tabla siguiente.  
  
|Miembros de|Accesibilidad de miembro predeterminada|Accesibilidad declarada permitida del miembro|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|Ninguna|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|Ninguna|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 La accesibilidad de un tipo anidado depende de su [dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md), que viene determinado por la accesibilidad declarada del miembro y el dominio de accesibilidad del tipo contenedor inmediato. Sin embargo, el dominio de accesibilidad de un tipo anidado no puede superar al del tipo contenedor.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
- [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md)  
- [Dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md)  
- [Restricciones en el uso de los niveles de accesibilidad](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
- [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [public](../../../csharp/language-reference/keywords/public.md)  
- [private](../../../csharp/language-reference/keywords/private.md)  
- [protected](../../../csharp/language-reference/keywords/protected.md)  
- [internal](../../../csharp/language-reference/keywords/internal.md)

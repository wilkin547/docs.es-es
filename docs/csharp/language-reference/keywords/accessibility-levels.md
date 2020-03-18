---
title: 'Niveles de accesibilidad: Referencia de C#'
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: 26fbc2a6d86aead537465c304146630f8bcd3ad4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713814"
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
  
 La accesibilidad de un tipo anidado depende de su [dominio de accesibilidad](./accessibility-domain.md), que viene determinado por la accesibilidad declarada del miembro y el dominio de accesibilidad del tipo contenedor inmediato. Sin embargo, el dominio de accesibilidad de un tipo anidado no puede superar al del tipo contenedor.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](./index.md)
- [Modificadores de acceso](./access-modifiers.md)
- [Dominio de accesibilidad](./accessibility-domain.md)
- [Restricciones en el uso de los niveles de accesibilidad](./restrictions-on-using-accessibility-levels.md)
- [Modificadores de acceso](../../programming-guide/classes-and-structs/access-modifiers.md)
- [public](./public.md)
- [private](./private.md)
- [protected](./protected.md)
- [internal](./internal.md)

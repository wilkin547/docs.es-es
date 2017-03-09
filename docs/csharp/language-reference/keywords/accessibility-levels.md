---
title: "Niveles de accesibilidad (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "modificadores de acceso [C#], niveles de accesibilidad"
  - "niveles de accesibilidad"
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Niveles de accesibilidad (Referencia de C#)
Utilice los modificadores de acceso, [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md) para especificar uno de los siguientes niveles de accesibilidad declarados para miembros.  
  
|Accesibilidad declarada|Significado|  
|-----------------------------|-----------------|  
|`public`|Acceso no restringido.|  
|`protected`|Acceso limitado a la clase contenedora o a los tipos derivados de esta clase.|  
|`internal`|Acceso limitado al ensamblado actual.|  
|`protected` `internal`|Acceso limitado al ensamblado actual o a los tipos derivados de la clase contenedora.|  
|`private`|Acceso limitado al tipo contenedor.|  
  
 Sólo se permite un modificador de acceso para un miembro o tipo, excepto cuando se utiliza la combinación `protected` `internal`.  
  
 Los modificadores de acceso no se pueden utilizar en espacios de nombres.  Los espacios de nombres no presentan restricciones de acceso.  
  
 Según el contexto en el que se produce una declaración de miembro, sólo se permite declarar ciertos tipos de acceso.  Si no se especifica ningún modificador de acceso en una declaración de miembro, se utiliza el tipo de acceso predeterminado.  
  
 Los tipos de nivel superior, que no están anidados en otros tipos, sólo pueden tener accesibilidad `internal` o `public`.  La accesibilidad predeterminada para estos tipos es `internal`.  
  
 Los tipos anidados, que son miembros de otros tipos, pueden tener un tipo de acceso declarado como el que se indica en la siguiente tabla.  
  
|Miembros de|Accesibilidad predeterminada|Accesibilidades declaradas permitidas|  
|-----------------|----------------------------------|-------------------------------------------|  
|`enum`|`public`|None|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected` `internal`|  
|`interface`|`public`|None|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 La accesibilidad de un tipo anidado depende de su [dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md), el cual se determina mediante la accesibilidad declarada para el miembro y el dominio de accesibilidad del tipo inmediato que lo contiene.  Sin embargo, el dominio de accesibilidad de un tipo anidado no puede superar al del tipo contenedor.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md)   
 [Restricciones en el uso de los niveles de accesibilidad](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)   
 [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)
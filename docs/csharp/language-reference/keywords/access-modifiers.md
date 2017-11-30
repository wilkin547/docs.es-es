---
title: Modificadores de acceso (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 23f99d0925aefde7ef43888d16e888a0943dfc21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="access-modifiers-c-reference"></a>Modificadores de acceso (Referencia de C#)
Los modificadores de acceso son palabras clave que se usan para especificar la accesibilidad declarada de un miembro o un tipo. En esta sección se presentan los cuatro modificadores de acceso:  
  
-   [public](../../../csharp/language-reference/keywords/public.md)  
  
-   [protected](../../../csharp/language-reference/keywords/protected.md)  
  
-   [internal](../../../csharp/language-reference/keywords/internal.md)  
  
-   [private](../../../csharp/language-reference/keywords/private.md)  
  
 Los siguientes seis niveles de accesibilidad pueden especificarse mediante los modificadores de acceso:  
  
 `public`: el acceso no está restringido.  
  
 `protected`: el acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora.  
  
 `internal`: el acceso está limitado al ensamblado actual.  
  
 [`protected internal`](../../../csharp/language-reference/keywords/protected-internal.md): Acceso está limitado al ensamblado actual o tipos derivados de la clase contenedora.  
  
 `private`: el acceso está limitado al tipo contenedor.  

 [`private protected`](../../../csharp/language-reference/keywords/private-protected.md): Acceso está limitado a la clase contenedora o tipos derivados de la clase contenedora dentro del ensamblado actual.  
  
 En esta sección también se presenta lo siguiente:  
  
-   [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md): mediante los modificadores de cuatro acceso para declarar los seis niveles de accesibilidad.  
  
-   [Dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md): especifica en qué secciones del programa se puede hacer referencia a dicho miembro.  
  
-   [Restricciones en el uso de niveles de accesibilidad](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): un resumen de las restricciones sobre usar niveles de accesibilidad declarados.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [Palabras clave de acceso](../../../csharp/language-reference/keywords/access-keywords.md)  
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)

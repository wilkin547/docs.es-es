---
title: Modificadores de acceso (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: 15
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3ad46580561500d9f011da4997007023a3bc844
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="d5731-102">Modificadores de acceso (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d5731-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="d5731-103">Los modificadores de acceso son palabras clave que se usan para especificar la accesibilidad declarada de un miembro o un tipo.</span><span class="sxs-lookup"><span data-stu-id="d5731-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="d5731-104">En esta sección se presentan los cuatro modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="d5731-104">This section introduces the four access modifiers:</span></span>  
  
-   [<span data-ttu-id="d5731-105">public</span><span class="sxs-lookup"><span data-stu-id="d5731-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
-   [<span data-ttu-id="d5731-106">protected</span><span class="sxs-lookup"><span data-stu-id="d5731-106">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
-   [<span data-ttu-id="d5731-107">internal</span><span class="sxs-lookup"><span data-stu-id="d5731-107">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
-   [<span data-ttu-id="d5731-108">private</span><span class="sxs-lookup"><span data-stu-id="d5731-108">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
 <span data-ttu-id="d5731-109">Pueden especificarse los siguientes cinco niveles de accesibilidad con los modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="d5731-109">The following five accessibility levels can be specified using the access modifiers:</span></span>  
  
 <span data-ttu-id="d5731-110">`public`: el acceso no está restringido.</span><span class="sxs-lookup"><span data-stu-id="d5731-110">`public`: Access is not restricted.</span></span>  
  
 <span data-ttu-id="d5731-111">`protected`: el acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="d5731-111">`protected`: Access is limited to the containing class or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="d5731-112">`Internal`: el acceso está limitado al ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="d5731-112">`Internal`: Access is limited to the current assembly.</span></span>  
  
 <span data-ttu-id="d5731-113">[protected internal](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md): el acceso está limitado al ensamblado actual o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="d5731-113">[protected internal](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="d5731-114">`private`: el acceso está limitado al tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="d5731-114">`private`: Access is limited to the containing type.</span></span>  
  
 <span data-ttu-id="d5731-115">En esta sección también se presenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d5731-115">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="d5731-116">[Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md): usar los cuatro modificadores de acceso para declarar cinco niveles de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="d5731-116">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare five levels of accessibility.</span></span>  
  
-   <span data-ttu-id="d5731-117">[Dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md): especifica en qué secciones del programa se puede hacer referencia a dicho miembro.</span><span class="sxs-lookup"><span data-stu-id="d5731-117">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="d5731-118">[Restricciones en el uso de niveles de accesibilidad](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): un resumen de las restricciones sobre usar niveles de accesibilidad declarados.</span><span class="sxs-lookup"><span data-stu-id="d5731-118">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5731-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5731-119">See Also</span></span>  
 <span data-ttu-id="d5731-120">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5731-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d5731-121">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5731-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d5731-122">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5731-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d5731-123">[Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="d5731-123">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="d5731-124">[Palabras clave de acceso](../../../csharp/language-reference/keywords/access-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="d5731-124">[Access Keywords](../../../csharp/language-reference/keywords/access-keywords.md) </span></span>  
 [<span data-ttu-id="d5731-125">Modificadores</span><span class="sxs-lookup"><span data-stu-id="d5731-125">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)


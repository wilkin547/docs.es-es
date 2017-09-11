---
title: Dominio de accesibilidad (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
caps.latest.revision: 17
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
ms.openlocfilehash: 90faf22d8a7d515ae8bd062f0b95f4be5e051f79
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="2b1ef-102">Dominio de accesibilidad (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="2b1ef-102">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="2b1ef-103">El dominio de accesibilidad de un miembro especifica en qué secciones del programa se puede hacer referencia a dicho miembro.</span><span class="sxs-lookup"><span data-stu-id="2b1ef-103">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="2b1ef-104">Si el miembro está anidado dentro de otro tipo, su dominio de accesibilidad viene determinado por el [nivel de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) del miembro y por el dominio de accesibilidad del tipo contenedor inmediato.</span><span class="sxs-lookup"><span data-stu-id="2b1ef-104">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](../../../csharp/language-reference/keywords/accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="2b1ef-105">El dominio de accesibilidad de un tipo de nivel superior es por lo menos el texto del programa del proyecto en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="2b1ef-105">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="2b1ef-106">Es decir, el dominio incluye todos los archivos de origen de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="2b1ef-106">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="2b1ef-107">El dominio de accesibilidad de un tipo anidado es, al menos, el texto del programa del tipo en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="2b1ef-107">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="2b1ef-108">Es decir, el dominio es el cuerpo del tipo, que incluye todos los tipos anidados.</span><span class="sxs-lookup"><span data-stu-id="2b1ef-108">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="2b1ef-109">El dominio de accesibilidad de un tipo anidado no puede superar nunca al del tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="2b1ef-109">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="2b1ef-110">Estos conceptos se muestran en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2b1ef-110">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b1ef-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b1ef-111">Example</span></span>  
 <span data-ttu-id="2b1ef-112">Este ejemplo contiene un tipo de nivel superior, `T1`, y dos clases anidadas, `M1` y `M2`.</span><span class="sxs-lookup"><span data-stu-id="2b1ef-112">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="2b1ef-113">Las clases contienen campos que tienen diferentes accesibilidades declaradas.</span><span class="sxs-lookup"><span data-stu-id="2b1ef-113">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="2b1ef-114">En el método `Main`, a cada instrucción le sigue un comentario que indica el dominio de accesibilidad de cada miembro.</span><span class="sxs-lookup"><span data-stu-id="2b1ef-114">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="2b1ef-115">Observe que las instrucciones que intentan hacer referencia a los miembros inaccesibles están marcadas con comentarios.</span><span class="sxs-lookup"><span data-stu-id="2b1ef-115">Notice that the statements that try to reference the inaccessible members are commented out.</span></span> <span data-ttu-id="2b1ef-116">Si quiere ver los errores generados por el compilador cuando se intenta hacer referencia a un miembro inaccesible, quite los comentarios de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="2b1ef-116">If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
 <span data-ttu-id="2b1ef-117">[!code-cs[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2b1ef-117">[!code-cs[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="2b1ef-118">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="2b1ef-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2b1ef-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b1ef-119">See Also</span></span>  
 <span data-ttu-id="2b1ef-120">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="2b1ef-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="2b1ef-121">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2b1ef-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2b1ef-122">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="2b1ef-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="2b1ef-123">[Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="2b1ef-123">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="2b1ef-124">[Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="2b1ef-124">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="2b1ef-125">[Restricciones en el uso de los niveles de accesibilidad](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="2b1ef-125">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span></span>  
 <span data-ttu-id="2b1ef-126">[Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="2b1ef-126">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="2b1ef-127">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="2b1ef-127">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="2b1ef-128">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="2b1ef-128">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="2b1ef-129">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="2b1ef-129">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 [<span data-ttu-id="2b1ef-130">internal</span><span class="sxs-lookup"><span data-stu-id="2b1ef-130">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)


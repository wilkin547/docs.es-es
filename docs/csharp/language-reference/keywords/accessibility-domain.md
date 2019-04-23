---
title: 'Dominio de accesibilidad: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 529d256a553c4000c77bcd5096db1a4d943874ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141757"
---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="f8f80-102">Dominio de accesibilidad (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f8f80-102">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="f8f80-103">El dominio de accesibilidad de un miembro especifica en qué secciones del programa se puede hacer referencia a dicho miembro.</span><span class="sxs-lookup"><span data-stu-id="f8f80-103">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="f8f80-104">Si el miembro está anidado dentro de otro tipo, su dominio de accesibilidad viene determinado por el [nivel de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) del miembro y por el dominio de accesibilidad del tipo contenedor inmediato.</span><span class="sxs-lookup"><span data-stu-id="f8f80-104">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](../../../csharp/language-reference/keywords/accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="f8f80-105">El dominio de accesibilidad de un tipo de nivel superior es por lo menos el texto del programa del proyecto en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="f8f80-105">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="f8f80-106">Es decir, el dominio incluye todos los archivos de origen de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="f8f80-106">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="f8f80-107">El dominio de accesibilidad de un tipo anidado es, al menos, el texto del programa del tipo en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="f8f80-107">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="f8f80-108">Es decir, el dominio es el cuerpo del tipo, que incluye todos los tipos anidados.</span><span class="sxs-lookup"><span data-stu-id="f8f80-108">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="f8f80-109">El dominio de accesibilidad de un tipo anidado no puede superar nunca al del tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="f8f80-109">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="f8f80-110">Estos conceptos se muestran en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f8f80-110">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8f80-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8f80-111">Example</span></span>  
 <span data-ttu-id="f8f80-112">Este ejemplo contiene un tipo de nivel superior, `T1`, y dos clases anidadas, `M1` y `M2`.</span><span class="sxs-lookup"><span data-stu-id="f8f80-112">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="f8f80-113">Las clases contienen campos que tienen diferentes accesibilidades declaradas.</span><span class="sxs-lookup"><span data-stu-id="f8f80-113">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="f8f80-114">En el método `Main`, a cada instrucción le sigue un comentario que indica el dominio de accesibilidad de cada miembro.</span><span class="sxs-lookup"><span data-stu-id="f8f80-114">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="f8f80-115">Observe que las instrucciones que intentan hacer referencia a los miembros inaccesibles están marcadas con comentarios. Si quiere ver los errores generados por el compilador cuando se intenta hacer referencia a un miembro inaccesible, quite los comentarios de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="f8f80-115">Notice that the statements that try to reference the inaccessible members are commented out. If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a><span data-ttu-id="f8f80-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f8f80-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f8f80-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8f80-117">See also</span></span>

- [<span data-ttu-id="f8f80-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f8f80-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="f8f80-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f8f80-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f8f80-120">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f8f80-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="f8f80-121">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="f8f80-121">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)
- [<span data-ttu-id="f8f80-122">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="f8f80-122">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)
- [<span data-ttu-id="f8f80-123">Restricciones en el uso de los niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="f8f80-123">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="f8f80-124">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="f8f80-124">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="f8f80-125">public</span><span class="sxs-lookup"><span data-stu-id="f8f80-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)
- [<span data-ttu-id="f8f80-126">private</span><span class="sxs-lookup"><span data-stu-id="f8f80-126">private</span></span>](../../../csharp/language-reference/keywords/private.md)
- [<span data-ttu-id="f8f80-127">protected</span><span class="sxs-lookup"><span data-stu-id="f8f80-127">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
- [<span data-ttu-id="f8f80-128">internal</span><span class="sxs-lookup"><span data-stu-id="f8f80-128">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

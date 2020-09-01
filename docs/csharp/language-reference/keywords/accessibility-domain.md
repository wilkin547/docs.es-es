---
description: 'Dominio de accesibilidad: Referencia de C#'
title: 'Dominio de accesibilidad: Referencia de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 2cfc4cc72a79b33276b7d822a2b31eb518dcf784
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89127066"
---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="7c2e5-103">Dominio de accesibilidad (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7c2e5-103">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="7c2e5-104">El dominio de accesibilidad de un miembro especifica en qué secciones del programa se puede hacer referencia a dicho miembro.</span><span class="sxs-lookup"><span data-stu-id="7c2e5-104">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="7c2e5-105">Si el miembro está anidado dentro de otro tipo, su dominio de accesibilidad viene determinado por el [nivel de accesibilidad](./accessibility-levels.md) del miembro y por el dominio de accesibilidad del tipo contenedor inmediato.</span><span class="sxs-lookup"><span data-stu-id="7c2e5-105">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](./accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="7c2e5-106">El dominio de accesibilidad de un tipo de nivel superior es por lo menos el texto del programa del proyecto en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="7c2e5-106">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="7c2e5-107">Es decir, el dominio incluye todos los archivos de origen de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7c2e5-107">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="7c2e5-108">El dominio de accesibilidad de un tipo anidado es, al menos, el texto del programa del tipo en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="7c2e5-108">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="7c2e5-109">Es decir, el dominio es el cuerpo del tipo, que incluye todos los tipos anidados.</span><span class="sxs-lookup"><span data-stu-id="7c2e5-109">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="7c2e5-110">El dominio de accesibilidad de un tipo anidado no puede superar nunca al del tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="7c2e5-110">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="7c2e5-111">Estos conceptos se muestran en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7c2e5-111">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c2e5-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c2e5-112">Example</span></span>  
 <span data-ttu-id="7c2e5-113">Este ejemplo contiene un tipo de nivel superior, `T1`, y dos clases anidadas, `M1` y `M2`.</span><span class="sxs-lookup"><span data-stu-id="7c2e5-113">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="7c2e5-114">Las clases contienen campos que tienen diferentes accesibilidades declaradas.</span><span class="sxs-lookup"><span data-stu-id="7c2e5-114">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="7c2e5-115">En el método `Main`, a cada instrucción le sigue un comentario que indica el dominio de accesibilidad de cada miembro.</span><span class="sxs-lookup"><span data-stu-id="7c2e5-115">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="7c2e5-116">Observe que las instrucciones que intentan hacer referencia a los miembros inaccesibles están marcadas con comentarios. Si quiere ver los errores generados por el compilador cuando se intenta hacer referencia a un miembro inaccesible, quite los comentarios de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="7c2e5-116">Notice that the statements that try to reference the inaccessible members are commented out. If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a><span data-ttu-id="7c2e5-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="7c2e5-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7c2e5-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c2e5-118">See also</span></span>

- [<span data-ttu-id="7c2e5-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="7c2e5-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7c2e5-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7c2e5-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7c2e5-121">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="7c2e5-121">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="7c2e5-122">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="7c2e5-122">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="7c2e5-123">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="7c2e5-123">Accessibility Levels</span></span>](./accessibility-levels.md)
- [<span data-ttu-id="7c2e5-124">Restricciones en el uso de los niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="7c2e5-124">Restrictions on Using Accessibility Levels</span></span>](./restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="7c2e5-125">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="7c2e5-125">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="7c2e5-126">public</span><span class="sxs-lookup"><span data-stu-id="7c2e5-126">public</span></span>](./public.md)
- [<span data-ttu-id="7c2e5-127">private</span><span class="sxs-lookup"><span data-stu-id="7c2e5-127">private</span></span>](./private.md)
- [<span data-ttu-id="7c2e5-128">protected</span><span class="sxs-lookup"><span data-stu-id="7c2e5-128">protected</span></span>](./protected.md)
- [<span data-ttu-id="7c2e5-129">internal</span><span class="sxs-lookup"><span data-stu-id="7c2e5-129">internal</span></span>](./internal.md)

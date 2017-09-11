---
title: "Cómo: Definir constantes en C#"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
caps.latest.revision: 7
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
ms.openlocfilehash: 6c5a6f63675893eb0700afab462bf237f5639d74
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-define-constants-in-c"></a><span data-ttu-id="9458b-102">Cómo: Definir constantes en C#</span><span class="sxs-lookup"><span data-stu-id="9458b-102">How to: Define Constants in C#</span></span>
<span data-ttu-id="9458b-103">Las constantes son campos cuyos valores se establecen en tiempo de compilación y nunca se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="9458b-103">Constants are fields whose values are set at compile time and can never be changed.</span></span> <span data-ttu-id="9458b-104">Use constantes para proporcionar nombres descriptivos en lugar de literales numéricos ("números mágicos") para valores especiales.</span><span class="sxs-lookup"><span data-stu-id="9458b-104">Use constants to provide meaningful names instead of numeric literals ("magic numbers") for special values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9458b-105">En C#, la directiva del preprocesador [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) no puede usarse para definir constantes en la manera que se usa normalmente en C y C++.</span><span class="sxs-lookup"><span data-stu-id="9458b-105">In C# the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive cannot be used to define constants in the way that is typically used in C and C++.</span></span>  
  
 <span data-ttu-id="9458b-106">Para definir valores constantes de tipos enteros (`int`, `byte` y así sucesivamente) use un tipo enumerado.</span><span class="sxs-lookup"><span data-stu-id="9458b-106">To define constant values of integral types (`int`, `byte`, and so on) use an enumerated type.</span></span> <span data-ttu-id="9458b-107">Para más información, vea [enum](../../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="9458b-107">For more information, see [enum](../../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="9458b-108">Para definir constantes no enteras, un enfoque es agruparlas en una única clase estática denominada `Constants`.</span><span class="sxs-lookup"><span data-stu-id="9458b-108">To define non-integral constants, one approach is to group them in a single static class named `Constants`.</span></span> <span data-ttu-id="9458b-109">Esto necesitará que todas las referencias a las constantes vayan precedidas por el nombre de clase, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9458b-109">This will require that all references to the constants be prefaced with the class name, as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9458b-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9458b-110">Example</span></span>  
 <span data-ttu-id="9458b-111">[!code-cs[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9458b-111">[!code-cs[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]</span></span>  
  
 <span data-ttu-id="9458b-112">El uso del calificador de nombre de clase ayuda a garantizar que usted y otros usuarios que usan la constante comprenden que es una constante y que no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="9458b-112">The use of the class name qualifier helps ensure that you and others who use the constant understand that it is constant and cannot be modified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9458b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9458b-113">See Also</span></span>  
 [<span data-ttu-id="9458b-114">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="9458b-114">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)


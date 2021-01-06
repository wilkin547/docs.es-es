---
title: Definición de constantes en C#
description: Aprenda a definir constantes de C#, que son campos cuyos valores se establecen en tiempo de compilación. Use constantes para proporcionar nombres descriptivos a los valores especiales.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: 972deaa4616c15c00e83e26891c4473eae7bfcf8
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513060"
---
# <a name="how-to-define-constants-in-c"></a><span data-ttu-id="13932-104">Definición de constantes en C\#</span><span class="sxs-lookup"><span data-stu-id="13932-104">How to define constants in C\#</span></span>

<span data-ttu-id="13932-105">Las constantes son campos cuyos valores se establecen en tiempo de compilación y nunca se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="13932-105">Constants are fields whose values are set at compile time and can never be changed.</span></span> <span data-ttu-id="13932-106">Use constantes para proporcionar nombres descriptivos en lugar de literales numéricos ("números mágicos") para valores especiales.</span><span class="sxs-lookup"><span data-stu-id="13932-106">Use constants to provide meaningful names instead of numeric literals ("magic numbers") for special values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13932-107">En C#, la directiva del preprocesador [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) no puede usarse para definir constantes en la manera que se usa normalmente en C y C++.</span><span class="sxs-lookup"><span data-stu-id="13932-107">In C# the [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive cannot be used to define constants in the way that is typically used in C and C++.</span></span>  
  
 <span data-ttu-id="13932-108">Para definir valores constantes de tipos enteros (`int`, `byte` y así sucesivamente) use un tipo enumerado.</span><span class="sxs-lookup"><span data-stu-id="13932-108">To define constant values of integral types (`int`, `byte`, and so on) use an enumerated type.</span></span> <span data-ttu-id="13932-109">Para más información, vea [enum](../../language-reference/builtin-types/enum.md).</span><span class="sxs-lookup"><span data-stu-id="13932-109">For more information, see [enum](../../language-reference/builtin-types/enum.md).</span></span>  
  
 <span data-ttu-id="13932-110">Para definir constantes no enteras, un enfoque es agruparlas en una única clase estática denominada `Constants`.</span><span class="sxs-lookup"><span data-stu-id="13932-110">To define non-integral constants, one approach is to group them in a single static class named `Constants`.</span></span> <span data-ttu-id="13932-111">Esto necesitará que todas las referencias a las constantes vayan precedidas por el nombre de clase, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="13932-111">This will require that all references to the constants be prefaced with the class name, as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13932-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="13932-112">Example</span></span>  

 [!code-csharp[csProgGuideObjects#89](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#89)]  
  
 <span data-ttu-id="13932-113">El uso del calificador de nombre de clase ayuda a garantizar que usted y otros usuarios que usan la constante comprenden que es una constante y que no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="13932-113">The use of the class name qualifier helps ensure that you and others who use the constant understand that it is constant and cannot be modified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13932-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13932-114">See also</span></span>

- [<span data-ttu-id="13932-115">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="13932-115">Classes and Structs</span></span>](./index.md)

---
title: 'Pasar parámetros: Guía de programación de C#'
description: En C#, puede pasar un argumento a un parámetro por valor o referencia. Los cambios en un argumento pasado por referencia se conservan. Use ref o out para pasar por referencia.
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: 875a42aacf3d7aa4124684aefafdcb07ff4c87d6
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864740"
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="9ad0b-105">Pasar parámetros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9ad0b-105">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="9ad0b-106">En C#, los argumentos se pueden pasar a parámetros por valor o por referencia.</span><span class="sxs-lookup"><span data-stu-id="9ad0b-106">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="9ad0b-107">El paso de parámetros por referencia permite a los miembros de funciones, métodos, propiedades, indexadores, operadores y constructores cambiar el valor de los parámetros y hacer que ese cambio persista en el entorno de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9ad0b-107">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="9ad0b-108">Para pasar un parámetro por referencia con la intención de cambiar el valor, use la palabra clave `ref` o `out`.</span><span class="sxs-lookup"><span data-stu-id="9ad0b-108">To pass a parameter by reference with the intent of changing the value, use the `ref`, or `out` keyword.</span></span> <span data-ttu-id="9ad0b-109">Para pasar un parámetro por referencia con la intención de evitar la copia pero no modificar el valor, use el modificador `in`.</span><span class="sxs-lookup"><span data-stu-id="9ad0b-109">To pass by reference with the intent of avoiding copying but not changing the value, use the `in` modifier.</span></span> <span data-ttu-id="9ad0b-110">En los ejemplos de este tema, para simplificar, solo se usa la palabra clave `ref`.</span><span class="sxs-lookup"><span data-stu-id="9ad0b-110">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="9ad0b-111">Para obtener más información sobre la diferencia entre `in`, `ref` y `out`, vea [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md) y [out](../../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="9ad0b-111">For more information about the difference between `in`, `ref`, and `out`, see [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), and [out](../../language-reference/keywords/out-parameter-modifier.md).</span></span>  
  
 <span data-ttu-id="9ad0b-112">En el ejemplo siguiente se muestra la diferencia entre los parámetros de valor y de referencia.</span><span class="sxs-lookup"><span data-stu-id="9ad0b-112">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#10)]  
  
 <span data-ttu-id="9ad0b-113">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9ad0b-113">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="9ad0b-114">Pasar parámetros de tipo de valor</span><span class="sxs-lookup"><span data-stu-id="9ad0b-114">Passing Value-Type Parameters</span></span>](./passing-value-type-parameters.md)  
  
- [<span data-ttu-id="9ad0b-115">Pasar parámetros Reference-Type</span><span class="sxs-lookup"><span data-stu-id="9ad0b-115">Passing Reference-Type Parameters</span></span>](./passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="9ad0b-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="9ad0b-116">C# Language Specification</span></span>  

<span data-ttu-id="9ad0b-117">Para obtener más información, vea la sección [Listas de argumentos](~/_csharplang/spec/expressions.md#argument-lists) de [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="9ad0b-117">For more information, see [Argument lists](~/_csharplang/spec/expressions.md#argument-lists) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="9ad0b-118">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="9ad0b-118">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9ad0b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ad0b-119">See also</span></span>

- [<span data-ttu-id="9ad0b-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9ad0b-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9ad0b-121">Métodos</span><span class="sxs-lookup"><span data-stu-id="9ad0b-121">Methods</span></span>](./methods.md)

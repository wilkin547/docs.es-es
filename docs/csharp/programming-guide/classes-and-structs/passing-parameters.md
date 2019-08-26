---
title: 'Pasar parámetros: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: 1c42ce7b258ca35d4e91e1ef28c71b60fe1f01de
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69596252"
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="99148-102">Pasar parámetros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="99148-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="99148-103">En C#, los argumentos se pueden pasar a parámetros por valor o por referencia.</span><span class="sxs-lookup"><span data-stu-id="99148-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="99148-104">El paso de parámetros por referencia permite a los miembros de funciones, métodos, propiedades, indexadores, operadores y constructores cambiar el valor de los parámetros y hacer que ese cambio persista en el entorno de la llamada.</span><span class="sxs-lookup"><span data-stu-id="99148-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="99148-105">Para pasar un parámetro por referencia con la intención de cambiar el valor, use la palabra clave `ref` o `out`.</span><span class="sxs-lookup"><span data-stu-id="99148-105">To pass a parameter by reference with the intent of changing the value, use the `ref`, or `out` keyword.</span></span> <span data-ttu-id="99148-106">Para pasar un parámetro por referencia con la intención de evitar la copia pero no modificar el valor, use el modificador `in`.</span><span class="sxs-lookup"><span data-stu-id="99148-106">To pass by reference with the intent of avoiding copying but not changing the value, use the `in` modifier.</span></span> <span data-ttu-id="99148-107">En los ejemplos de este tema, para simplificar, solo se usa la palabra clave `ref`.</span><span class="sxs-lookup"><span data-stu-id="99148-107">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="99148-108">Para obtener más información sobre la diferencia entre `in`, `ref` y `out`, vea [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md) y [out](../../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="99148-108">For more information about the difference between `in`, `ref`, and `out`, see [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), and [out](../../language-reference/keywords/out-parameter-modifier.md).</span></span>  
  
 <span data-ttu-id="99148-109">En el ejemplo siguiente se muestra la diferencia entre los parámetros de valor y de referencia.</span><span class="sxs-lookup"><span data-stu-id="99148-109">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#10)]  
  
 <span data-ttu-id="99148-110">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="99148-110">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="99148-111">Pasar parámetros de tipo de valor</span><span class="sxs-lookup"><span data-stu-id="99148-111">Passing Value-Type Parameters</span></span>](./passing-value-type-parameters.md)  
  
- [<span data-ttu-id="99148-112">Pasar parámetros Reference-Type</span><span class="sxs-lookup"><span data-stu-id="99148-112">Passing Reference-Type Parameters</span></span>](./passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="99148-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="99148-113">C# Language Specification</span></span>  

<span data-ttu-id="99148-114">Para obtener más información, vea la sección [Listas de argumentos](~/_csharplang/spec/expressions.md#argument-lists) de [Especificación del lenguaje C#](../../language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="99148-114">For more information, see [Argument lists](~/_csharplang/spec/expressions.md#argument-lists) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="99148-115">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="99148-115">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="99148-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="99148-116">See also</span></span>

- [<span data-ttu-id="99148-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="99148-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="99148-118">Métodos</span><span class="sxs-lookup"><span data-stu-id="99148-118">Methods</span></span>](./methods.md)

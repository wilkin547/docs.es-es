---
title: 'Método partial: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 742d6ca744ac723179718f1400e600411712dd40
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238291"
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="63f14-102">partial (Método) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="63f14-102">partial method (C# Reference)</span></span>

<span data-ttu-id="63f14-103">Un método parcial tiene su signatura definida en una parte de un tipo parcial y su implementación definida en otra parte del tipo.</span><span class="sxs-lookup"><span data-stu-id="63f14-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="63f14-104">Los métodos parciales permiten a los diseñadores de clases proporcionar enlaces de método, similares a los controladores de eventos, que los desarrolladores pueden decidir implementar o no.</span><span class="sxs-lookup"><span data-stu-id="63f14-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="63f14-105">Si el desarrollador no proporciona una implementación, el compilador quita la signatura en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="63f14-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="63f14-106">Se aplican las siguientes condiciones a los métodos parciales:</span><span class="sxs-lookup"><span data-stu-id="63f14-106">The following conditions apply to partial methods:</span></span>

- <span data-ttu-id="63f14-107">Las signaturas de ambas partes del tipo parcial deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="63f14-107">Signatures in both parts of the partial type must match.</span></span>

- <span data-ttu-id="63f14-108">El método debe devolver el valor void.</span><span class="sxs-lookup"><span data-stu-id="63f14-108">The method must return void.</span></span>

- <span data-ttu-id="63f14-109">No se permiten modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="63f14-109">No access modifiers are allowed.</span></span> <span data-ttu-id="63f14-110">Los métodos parciales son privados implícitamente.</span><span class="sxs-lookup"><span data-stu-id="63f14-110">Partial methods are implicitly private.</span></span>

<span data-ttu-id="63f14-111">En el ejemplo siguiente se muestra un método parcial definido en dos partes de una clase parcial:</span><span class="sxs-lookup"><span data-stu-id="63f14-111">The following example shows a partial method defined in two parts of a partial class:</span></span>

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

<span data-ttu-id="63f14-112">Para más información, vea [Clases y métodos parciales](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="63f14-112">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="63f14-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="63f14-113">See also</span></span>

- [<span data-ttu-id="63f14-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="63f14-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="63f14-115">partial (tipo)</span><span class="sxs-lookup"><span data-stu-id="63f14-115">partial type</span></span>](partial-type.md)
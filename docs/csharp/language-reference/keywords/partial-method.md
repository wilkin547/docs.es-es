---
title: 'Método partial: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 62efd8b47fb565316b417a65e1b0fe37e40786c8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713227"
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="7f9c1-102">partial (Método) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7f9c1-102">partial method (C# Reference)</span></span>

<span data-ttu-id="7f9c1-103">Un método parcial tiene su signatura definida en una parte de un tipo parcial y su implementación definida en otra parte del tipo.</span><span class="sxs-lookup"><span data-stu-id="7f9c1-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="7f9c1-104">Los métodos parciales permiten a los diseñadores de clases proporcionar enlaces de método, similares a los controladores de eventos, que los desarrolladores pueden decidir implementar o no.</span><span class="sxs-lookup"><span data-stu-id="7f9c1-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="7f9c1-105">Si el desarrollador no proporciona una implementación, el compilador quita la signatura en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="7f9c1-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="7f9c1-106">Se aplican las siguientes condiciones a los métodos parciales:</span><span class="sxs-lookup"><span data-stu-id="7f9c1-106">The following conditions apply to partial methods:</span></span>

- <span data-ttu-id="7f9c1-107">Las signaturas de ambas partes del tipo parcial deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="7f9c1-107">Signatures in both parts of the partial type must match.</span></span>

- <span data-ttu-id="7f9c1-108">El método debe devolver el valor void.</span><span class="sxs-lookup"><span data-stu-id="7f9c1-108">The method must return void.</span></span>

- <span data-ttu-id="7f9c1-109">No se permiten modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="7f9c1-109">No access modifiers are allowed.</span></span> <span data-ttu-id="7f9c1-110">Los métodos parciales son privados implícitamente.</span><span class="sxs-lookup"><span data-stu-id="7f9c1-110">Partial methods are implicitly private.</span></span>

<span data-ttu-id="7f9c1-111">En el ejemplo siguiente se muestra un método parcial definido en dos partes de una clase parcial:</span><span class="sxs-lookup"><span data-stu-id="7f9c1-111">The following example shows a partial method defined in two parts of a partial class:</span></span>

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

<span data-ttu-id="7f9c1-112">Para obtener más información, consulte [Clases y métodos parciales](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="7f9c1-112">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7f9c1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f9c1-113">See also</span></span>

- [<span data-ttu-id="7f9c1-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="7f9c1-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7f9c1-115">partial (tipo)</span><span class="sxs-lookup"><span data-stu-id="7f9c1-115">partial type</span></span>](partial-type.md)

---
title: Instrucción return (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 0d20da39d3f56220c4499f699e542bd24ded93ca
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43480534"
---
# <a name="return-c-reference"></a><span data-ttu-id="a51e1-102">return (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a51e1-102">return (C# Reference)</span></span>

<span data-ttu-id="a51e1-103">La instrucción `return` termina la ejecución del método en el que aparece y devuelve el control al método de llamada.</span><span class="sxs-lookup"><span data-stu-id="a51e1-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="a51e1-104">También puede devolver un valor opcional.</span><span class="sxs-lookup"><span data-stu-id="a51e1-104">It can also return an optional value.</span></span> <span data-ttu-id="a51e1-105">Si el método es del tipo `void`, la instrucción `return` se puede omitir.</span><span class="sxs-lookup"><span data-stu-id="a51e1-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>

 <span data-ttu-id="a51e1-106">Si la instrucción return está incluida en un bloque `try`, el bloque `finally`, si existe, se ejecutará antes de que el control se devuelva al método de llamada.</span><span class="sxs-lookup"><span data-stu-id="a51e1-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>

## <a name="example"></a><span data-ttu-id="a51e1-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a51e1-107">Example</span></span>

 <span data-ttu-id="a51e1-108">En el siguiente ejemplo, el método `CalculateArea()` devuelve la variable local `area` como un valor de tipo [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="a51e1-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a [double](double.md) value.</span></span>

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="a51e1-109">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a51e1-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a51e1-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a51e1-110">See also</span></span>

- [<span data-ttu-id="a51e1-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a51e1-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a51e1-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a51e1-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a51e1-113">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="a51e1-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a51e1-114">return (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a51e1-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)
- [<span data-ttu-id="a51e1-115">Instrucciones de salto</span><span class="sxs-lookup"><span data-stu-id="a51e1-115">Jump Statements</span></span>](jump-statements.md)

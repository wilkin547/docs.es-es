---
title: 'La declaración del operador debe ser uno de los siguientes: +,-, *,-,-, ^, &amp; , like, mod, and, or, XOR, not,  <<,  >>, =,  <>, <, <=, >, >=, ctype, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: a94e62e33427987a302a6244b2b8ce8d295e4f11
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159903"
---
# <a name="bc33000-operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="60e91-102">BC33000: la declaración del operador debe ser uno de los siguientes: +,-, \*, \, /, ^, &amp; , like, mod, and, or, XOR, not, \<\<, >>...</span><span class="sxs-lookup"><span data-stu-id="60e91-102">BC33000: Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>

<span data-ttu-id="60e91-103">Solo puede declarar un operador que sea válido para la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="60e91-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="60e91-104">En la tabla siguiente se enumeran los operadores que se pueden declarar.</span><span class="sxs-lookup"><span data-stu-id="60e91-104">The following table lists the operators you can declare.</span></span>

|<span data-ttu-id="60e91-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="60e91-105">Type</span></span>|<span data-ttu-id="60e91-106">Operadores</span><span class="sxs-lookup"><span data-stu-id="60e91-106">Operators</span></span>|
|----------|---------------|
|<span data-ttu-id="60e91-107">Unario</span><span class="sxs-lookup"><span data-stu-id="60e91-107">Unary</span></span>|<span data-ttu-id="60e91-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="60e91-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|
|<span data-ttu-id="60e91-109">Binary</span><span class="sxs-lookup"><span data-stu-id="60e91-109">Binary</span></span>|<span data-ttu-id="60e91-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="60e91-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|
|<span data-ttu-id="60e91-111">Conversión (unaria)</span><span class="sxs-lookup"><span data-stu-id="60e91-111">Conversion (unary)</span></span>|`CType`|

 <span data-ttu-id="60e91-112">Tenga en cuenta que el `=` operador de la lista binaria es el operador de comparación, no el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="60e91-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>

 <span data-ttu-id="60e91-113">**Identificador de error:** BC33000</span><span class="sxs-lookup"><span data-stu-id="60e91-113">**Error ID:** BC33000</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="60e91-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="60e91-114">To correct this error</span></span>

- <span data-ttu-id="60e91-115">Seleccione un operador del conjunto de operadores sobrecargables.</span><span class="sxs-lookup"><span data-stu-id="60e91-115">Select an operator from the set of overloadable operators.</span></span>

- <span data-ttu-id="60e91-116">Si necesita la función de sobrecarga de un operador que no se puede sobrecargar directamente, cree un procedimiento `Function` que tome los parámetros adecuados y devuelva el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="60e91-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>

## <a name="see-also"></a><span data-ttu-id="60e91-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="60e91-117">See also</span></span>

- [<span data-ttu-id="60e91-118">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="60e91-118">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="60e91-119">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="60e91-119">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="60e91-120">Procedimiento para definir un operador</span><span class="sxs-lookup"><span data-stu-id="60e91-120">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="60e91-121">Procedimiento para definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="60e91-121">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="60e91-122">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="60e91-122">Function Statement</span></span>](../statements/function-statement.md)

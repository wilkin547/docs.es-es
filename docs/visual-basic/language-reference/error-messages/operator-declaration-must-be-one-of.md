---
description: 'Obtenga más información sobre: BC33000: la declaración del operador debe ser uno de los siguientes: +,-, *,,/, ^, &amp; , like, mod, and, or, XOR, not,  <<  >>...'
title: 'La declaración del operador debe ser uno de los siguientes: +,-, *,-,-, ^, &amp; , like, mod, and, or, XOR, not,  <<,  >>, =,  <>, <, <=, >, >=, ctype, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 0ad82a6414387278622a10624952ebc35e7e9b83
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795565"
---
# <a name="bc33000-operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="6be6e-103">BC33000: la declaración del operador debe ser uno de los siguientes: +,-, \*, \, /, ^, &amp; , like, mod, and, or, XOR, not, \<\<, >>...</span><span class="sxs-lookup"><span data-stu-id="6be6e-103">BC33000: Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>

<span data-ttu-id="6be6e-104">Solo puede declarar un operador que sea válido para la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="6be6e-104">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="6be6e-105">En la tabla siguiente se enumeran los operadores que se pueden declarar.</span><span class="sxs-lookup"><span data-stu-id="6be6e-105">The following table lists the operators you can declare.</span></span>

|<span data-ttu-id="6be6e-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="6be6e-106">Type</span></span>|<span data-ttu-id="6be6e-107">Operadores</span><span class="sxs-lookup"><span data-stu-id="6be6e-107">Operators</span></span>|
|----------|---------------|
|<span data-ttu-id="6be6e-108">Unario</span><span class="sxs-lookup"><span data-stu-id="6be6e-108">Unary</span></span>|<span data-ttu-id="6be6e-109">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="6be6e-109">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|
|<span data-ttu-id="6be6e-110">Binary</span><span class="sxs-lookup"><span data-stu-id="6be6e-110">Binary</span></span>|<span data-ttu-id="6be6e-111">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="6be6e-111">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|
|<span data-ttu-id="6be6e-112">Conversión (unaria)</span><span class="sxs-lookup"><span data-stu-id="6be6e-112">Conversion (unary)</span></span>|`CType`|

 <span data-ttu-id="6be6e-113">Tenga en cuenta que el `=` operador de la lista binaria es el operador de comparación, no el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="6be6e-113">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>

 <span data-ttu-id="6be6e-114">**Identificador de error:** BC33000</span><span class="sxs-lookup"><span data-stu-id="6be6e-114">**Error ID:** BC33000</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6be6e-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6be6e-115">To correct this error</span></span>

- <span data-ttu-id="6be6e-116">Seleccione un operador del conjunto de operadores sobrecargables.</span><span class="sxs-lookup"><span data-stu-id="6be6e-116">Select an operator from the set of overloadable operators.</span></span>

- <span data-ttu-id="6be6e-117">Si necesita la función de sobrecarga de un operador que no se puede sobrecargar directamente, cree un procedimiento `Function` que tome los parámetros adecuados y devuelva el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="6be6e-117">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>

## <a name="see-also"></a><span data-ttu-id="6be6e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6be6e-118">See also</span></span>

- [<span data-ttu-id="6be6e-119">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="6be6e-119">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="6be6e-120">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="6be6e-120">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="6be6e-121">Procedimiento para definir un operador</span><span class="sxs-lookup"><span data-stu-id="6be6e-121">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="6be6e-122">Procedimiento para definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="6be6e-122">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="6be6e-123">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="6be6e-123">Function Statement</span></span>](../statements/function-statement.md)

---
title: Se esperaba una declaración
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 2755f5afcb96ca7a6c4d140908649390dd66d571
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162705"
---
# <a name="bc30188-declaration-expected"></a><span data-ttu-id="c0da5-102">BC30188: se esperaba una declaración</span><span class="sxs-lookup"><span data-stu-id="c0da5-102">BC30188: Declaration expected</span></span>

<span data-ttu-id="c0da5-103">Una instrucción no declarativa, como una instrucción de asignación o bucle, se produce fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c0da5-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="c0da5-104">Solo se permiten declaraciones fuera de los procedimientos.</span><span class="sxs-lookup"><span data-stu-id="c0da5-104">Only declarations are allowed outside procedures.</span></span>

 <span data-ttu-id="c0da5-105">Como alternativa, un elemento de programación se declara sin una palabra clave de declaración, como `Dim` o `Const` .</span><span class="sxs-lookup"><span data-stu-id="c0da5-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>

 <span data-ttu-id="c0da5-106">**Identificador de error:** BC30188</span><span class="sxs-lookup"><span data-stu-id="c0da5-106">**Error ID:** BC30188</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c0da5-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c0da5-107">To correct this error</span></span>

- <span data-ttu-id="c0da5-108">Mueva la instrucción no declarativa al cuerpo de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c0da5-108">Move the nondeclarative statement to the body of a procedure.</span></span>

- <span data-ttu-id="c0da5-109">Comience la declaración con una palabra clave de declaración adecuada.</span><span class="sxs-lookup"><span data-stu-id="c0da5-109">Begin the declaration with an appropriate declaration keyword.</span></span>

- <span data-ttu-id="c0da5-110">Asegúrese de que una palabra clave de declaración no esté mal escrita.</span><span class="sxs-lookup"><span data-stu-id="c0da5-110">Ensure that a declaration keyword is not misspelled.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0da5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0da5-111">See also</span></span>

- [<span data-ttu-id="c0da5-112">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="c0da5-112">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="c0da5-113">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="c0da5-113">Dim Statement</span></span>](../statements/dim-statement.md)

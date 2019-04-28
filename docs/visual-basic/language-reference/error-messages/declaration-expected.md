---
title: Se esperaba una declaración
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 64ee75c93615f57b15fea29f06fff500a395ba0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803836"
---
# <a name="declaration-expected"></a><span data-ttu-id="f0217-102">Se esperaba una declaración</span><span class="sxs-lookup"><span data-stu-id="f0217-102">Declaration expected</span></span>
<span data-ttu-id="f0217-103">Una instrucción no declarativa, como una asignación o una instrucción del bucle, se produce fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f0217-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="f0217-104">Sólo se permiten declaraciones procedimientos externos.</span><span class="sxs-lookup"><span data-stu-id="f0217-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="f0217-105">Como alternativa, se declara un elemento de programación sin una palabra clave como `Dim` o `Const`.</span><span class="sxs-lookup"><span data-stu-id="f0217-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="f0217-106">**Identificador de error:** BC30188</span><span class="sxs-lookup"><span data-stu-id="f0217-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f0217-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f0217-107">To correct this error</span></span>  
  
- <span data-ttu-id="f0217-108">Mueva la instrucción no declarativa en el cuerpo de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f0217-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
- <span data-ttu-id="f0217-109">Comience la declaración con una palabra clave de declaración adecuada.</span><span class="sxs-lookup"><span data-stu-id="f0217-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
- <span data-ttu-id="f0217-110">Asegúrese de que una palabra clave no está mal escrita.</span><span class="sxs-lookup"><span data-stu-id="f0217-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0217-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0217-111">See also</span></span>

- [<span data-ttu-id="f0217-112">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="f0217-112">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="f0217-113">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f0217-113">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

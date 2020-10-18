---
title: "'<keyword>' sólo es válida en un método de instancia"
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: ad39ade294b362b20f2dfb93455445bf41d056cd
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163329"
---
# <a name="bc30043-keyword-is-valid-only-within-an-instance-method"></a><span data-ttu-id="9bd21-102">BC30043: ' \<keyword> ' solo es válido en un método de instancia</span><span class="sxs-lookup"><span data-stu-id="9bd21-102">BC30043: '\<keyword>' is valid only within an instance method</span></span>

<span data-ttu-id="9bd21-103">Las `Me` `MyClass` `MyBase` palabras clave, y hacen referencia a instancias de clase específicas.</span><span class="sxs-lookup"><span data-stu-id="9bd21-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="9bd21-104">No se pueden usar dentro de un `Function` procedimiento compartido o `Sub` .</span><span class="sxs-lookup"><span data-stu-id="9bd21-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>

<span data-ttu-id="9bd21-105">*Identificador de error:*\* BC30043</span><span class="sxs-lookup"><span data-stu-id="9bd21-105">*Error ID:*\* BC30043</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="9bd21-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="9bd21-106">To correct this error</span></span>

- <span data-ttu-id="9bd21-107">Quite la palabra clave del procedimiento o quite la `Shared` palabra clave de la declaración de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9bd21-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bd21-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bd21-108">See also</span></span>

- [<span data-ttu-id="9bd21-109">Asignación de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="9bd21-109">Object Variable Assignment</span></span>](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="9bd21-110">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="9bd21-110">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="9bd21-111">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="9bd21-111">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)

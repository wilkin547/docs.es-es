---
description: "Más información sobre: BC30043: ' <keyword> ' solo es válido dentro de un método de instancia"
title: "'<keyword>' sólo es válida en un método de instancia"
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 0bca2df44e096da016c9cb0c2031a8ef6faeb2b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795981"
---
# <a name="bc30043-keyword-is-valid-only-within-an-instance-method"></a><span data-ttu-id="d7eca-103">BC30043: ' \<keyword> ' solo es válido en un método de instancia</span><span class="sxs-lookup"><span data-stu-id="d7eca-103">BC30043: '\<keyword>' is valid only within an instance method</span></span>

<span data-ttu-id="d7eca-104">Las `Me` `MyClass` `MyBase` palabras clave, y hacen referencia a instancias de clase específicas.</span><span class="sxs-lookup"><span data-stu-id="d7eca-104">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="d7eca-105">No se pueden usar dentro de un `Function` procedimiento compartido o `Sub` .</span><span class="sxs-lookup"><span data-stu-id="d7eca-105">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>

<span data-ttu-id="d7eca-106">*Identificador de error:*\* BC30043</span><span class="sxs-lookup"><span data-stu-id="d7eca-106">*Error ID:*\* BC30043</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d7eca-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d7eca-107">To correct this error</span></span>

- <span data-ttu-id="d7eca-108">Quite la palabra clave del procedimiento o quite la `Shared` palabra clave de la declaración de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d7eca-108">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7eca-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7eca-109">See also</span></span>

- [<span data-ttu-id="d7eca-110">Asignación de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="d7eca-110">Object Variable Assignment</span></span>](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="d7eca-111">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="d7eca-111">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="d7eca-112">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="d7eca-112">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)

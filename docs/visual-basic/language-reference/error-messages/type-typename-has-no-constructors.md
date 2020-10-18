---
title: El tipo '<typename>' no tiene ningún constructor
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: 249bcb7020f26c7c43d560e91ef7a34e4dc64470
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161184"
---
# <a name="bc30251-type-typename-has-no-constructors"></a><span data-ttu-id="4e7ec-102">BC30251: el tipo ' \<typename> ' no tiene constructores</span><span class="sxs-lookup"><span data-stu-id="4e7ec-102">BC30251: Type '\<typename>' has no constructors</span></span>

<span data-ttu-id="4e7ec-103">Un tipo no admite una llamada a `Sub New()`.</span><span class="sxs-lookup"><span data-stu-id="4e7ec-103">A type does not support a call to `Sub New()`.</span></span> <span data-ttu-id="4e7ec-104">Una causa probable puede ser un archivo binario o un compilador dañado.</span><span class="sxs-lookup"><span data-stu-id="4e7ec-104">One possible cause is a corrupted compiler or binary file.</span></span>

 <span data-ttu-id="4e7ec-105">**Identificador de error:** BC30251</span><span class="sxs-lookup"><span data-stu-id="4e7ec-105">**Error ID:** BC30251</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="4e7ec-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4e7ec-106">To correct this error</span></span>

1. <span data-ttu-id="4e7ec-107">Si el tipo está en proyecto distinto o en un archivo al que se hace referencia, reinstale el proyecto o archivo en cuestión.</span><span class="sxs-lookup"><span data-stu-id="4e7ec-107">If the type is in a different project or in a referenced file, reinstall the project or file.</span></span>

2. <span data-ttu-id="4e7ec-108">Si el tipo se encuentra en el mismo proyecto, vuelva a compilar el ensamblado que contiene dicho tipo.</span><span class="sxs-lookup"><span data-stu-id="4e7ec-108">If the type is in the same project, recompile the assembly containing the type.</span></span>

3. <span data-ttu-id="4e7ec-109">Si el error se repite, vuelva a instalar el compilador de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4e7ec-109">If the error recurs, reinstall the Visual Basic compiler.</span></span>

4. <span data-ttu-id="4e7ec-110">Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4e7ec-110">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e7ec-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e7ec-111">See also</span></span>

- [<span data-ttu-id="4e7ec-112">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="4e7ec-112">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="4e7ec-113">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="4e7ec-113">Talk to Us</span></span>](/visualstudio/ide/feedback-options)

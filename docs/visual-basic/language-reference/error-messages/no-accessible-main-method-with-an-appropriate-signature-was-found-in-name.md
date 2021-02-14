---
description: "Más información acerca de: BC30737: no se encontró ningún método ' Main ' accesible con una signatura adecuada en ' <name> '"
title: No se encontró ningún método 'Main' accesible con una firma apropiada en '<name>'
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 5ff79c1b7589f6b67492ad640179f7a852a2f381
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483526"
---
# <a name="bc30737-no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="51bd6-103">BC30737: no se encontró ningún método ' Main ' accesible con una signatura adecuada en ' \<name> '</span><span class="sxs-lookup"><span data-stu-id="51bd6-103">BC30737: No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>

<span data-ttu-id="51bd6-104">Las aplicaciones de línea de comandos deben tener un `Sub Main` definido.</span><span class="sxs-lookup"><span data-stu-id="51bd6-104">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="51bd6-105">`Main` se debe declarar como `Public Shared` si se hubiera definido en una clase o como si se hubiera `Public` definido en un módulo.</span><span class="sxs-lookup"><span data-stu-id="51bd6-105">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>

 <span data-ttu-id="51bd6-106">**Identificador de error:** BC30737</span><span class="sxs-lookup"><span data-stu-id="51bd6-106">**Error ID:** BC30737</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="51bd6-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="51bd6-107">To correct this error</span></span>

- <span data-ttu-id="51bd6-108">Defina un `Public Sub Main` procedimiento para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="51bd6-108">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="51bd6-109">Declárela como `Shared` si y solo si lo define dentro de una clase.</span><span class="sxs-lookup"><span data-stu-id="51bd6-109">Declare it as `Shared` if and only if you define it inside a class.</span></span>

## <a name="see-also"></a><span data-ttu-id="51bd6-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="51bd6-110">See also</span></span>

- [<span data-ttu-id="51bd6-111">Estructura de un programa de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="51bd6-111">Structure of a Visual Basic Program</span></span>](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="51bd6-112">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="51bd6-112">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)

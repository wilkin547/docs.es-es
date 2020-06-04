---
title: No se encontró ningún método 'Main' accesible con una firma apropiada en '<name>'
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6760b931ceb2ad5c2c04169d664da8629badc487
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409418"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="59161-102">No se encontró ningún método 'Main' accesible con una firma apropiada en '\<name>'</span><span class="sxs-lookup"><span data-stu-id="59161-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>
<span data-ttu-id="59161-103">Las aplicaciones de línea de comandos deben tener un `Sub Main` definido.</span><span class="sxs-lookup"><span data-stu-id="59161-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="59161-104">`Main`se debe declarar como `Public Shared` si se hubiera definido en una clase o como si se hubiera `Public` definido en un módulo.</span><span class="sxs-lookup"><span data-stu-id="59161-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="59161-105">**Identificador de error:** BC30737</span><span class="sxs-lookup"><span data-stu-id="59161-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="59161-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="59161-106">To correct this error</span></span>  
  
- <span data-ttu-id="59161-107">Defina un `Public Sub Main` procedimiento para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="59161-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="59161-108">Declárela como `Shared` si y solo si lo define dentro de una clase.</span><span class="sxs-lookup"><span data-stu-id="59161-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59161-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59161-109">See also</span></span>

- [<span data-ttu-id="59161-110">Estructura de un programa de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="59161-110">Structure of a Visual Basic Program</span></span>](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="59161-111">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="59161-111">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)

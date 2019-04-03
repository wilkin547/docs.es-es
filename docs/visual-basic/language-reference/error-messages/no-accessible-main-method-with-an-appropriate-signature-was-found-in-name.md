---
title: No se encontró ningún método 'Main' accesible con una firma apropiada en '<name>'
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: f5053bddf4b9ba791ad6d0733e1dd89c4ded91bd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818363"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="7e3e0-102">No se encontró ningún método 'Main' accesible con una firma apropiada en '\<nombre >'</span><span class="sxs-lookup"><span data-stu-id="7e3e0-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>
<span data-ttu-id="7e3e0-103">Las aplicaciones de línea de comandos deben tener un `Sub Main` definido.</span><span class="sxs-lookup"><span data-stu-id="7e3e0-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="7e3e0-104">`Main` debe declararse como `Public Shared` si está definido en una clase o como `Public` si está definido en un módulo.</span><span class="sxs-lookup"><span data-stu-id="7e3e0-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="7e3e0-105">**Identificador de error:** BC30737</span><span class="sxs-lookup"><span data-stu-id="7e3e0-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7e3e0-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7e3e0-106">To correct this error</span></span>  
  
-   <span data-ttu-id="7e3e0-107">Definir un `Public Sub Main` procedimiento para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7e3e0-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="7e3e0-108">Declara como `Shared` si y solo si se define dentro de una clase.</span><span class="sxs-lookup"><span data-stu-id="7e3e0-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e3e0-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e3e0-109">See also</span></span>

- [<span data-ttu-id="7e3e0-110">Estructura de un programa de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7e3e0-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="7e3e0-111">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7e3e0-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)

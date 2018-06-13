---
title: No accesible &#39;Main&#39; se encontró el método con una firma apropiada en &#39; &lt;nombre&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6a60e26a2bd0e31c0f92dbbfb2518c75f304d9f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593225"
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a><span data-ttu-id="16398-102">No accesible &#39;Main&#39; se encontró el método con una firma apropiada en &#39; &lt;nombre&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="16398-102">No accessible &#39;Main&#39; method with an appropriate signature was found in &#39;&lt;name&gt;&#39;</span></span>
<span data-ttu-id="16398-103">Las aplicaciones de línea de comandos deben tener un `Sub Main` definido.</span><span class="sxs-lookup"><span data-stu-id="16398-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="16398-104">`Main` debe declararse como `Public Shared` si se ha definido en una clase o como `Public` si está definido en un módulo.</span><span class="sxs-lookup"><span data-stu-id="16398-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="16398-105">**Id. de error:** BC30737</span><span class="sxs-lookup"><span data-stu-id="16398-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="16398-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="16398-106">To correct this error</span></span>  
  
-   <span data-ttu-id="16398-107">Definir una `Public Sub Main` procedimiento para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="16398-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="16398-108">Declara como `Shared` si y solo si se define dentro de una clase.</span><span class="sxs-lookup"><span data-stu-id="16398-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16398-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="16398-109">See Also</span></span>  
 [<span data-ttu-id="16398-110">Estructura de un programa de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16398-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [<span data-ttu-id="16398-111">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="16398-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)

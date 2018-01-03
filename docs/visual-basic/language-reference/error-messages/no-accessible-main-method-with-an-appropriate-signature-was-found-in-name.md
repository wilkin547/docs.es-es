---
title: "No accesible &#39; Main &#39; se encontró el método con una firma apropiada en &#39; &lt;nombre&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords: BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6a2d66c860b72bd3ef59c02f548ac563fab6b8c
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a><span data-ttu-id="44643-102">No accesible &#39; Main &#39; se encontró el método con una firma apropiada en &#39; &lt;nombre&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="44643-102">No accessible &#39;Main&#39; method with an appropriate signature was found in &#39;&lt;name&gt;&#39;</span></span>
<span data-ttu-id="44643-103">Las aplicaciones de línea de comandos deben tener un `Sub Main` definido.</span><span class="sxs-lookup"><span data-stu-id="44643-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="44643-104">`Main`debe declararse como `Public Shared` si se ha definido en una clase o como `Public` si está definido en un módulo.</span><span class="sxs-lookup"><span data-stu-id="44643-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="44643-105">**Id. de error:** BC30737</span><span class="sxs-lookup"><span data-stu-id="44643-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="44643-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="44643-106">To correct this error</span></span>  
  
-   <span data-ttu-id="44643-107">Definir una `Public Sub Main` procedimiento para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="44643-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="44643-108">Declara como `Shared` si y solo si se define dentro de una clase.</span><span class="sxs-lookup"><span data-stu-id="44643-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44643-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="44643-109">See Also</span></span>  
 [<span data-ttu-id="44643-110">Estructura de un programa de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="44643-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [<span data-ttu-id="44643-111">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="44643-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)

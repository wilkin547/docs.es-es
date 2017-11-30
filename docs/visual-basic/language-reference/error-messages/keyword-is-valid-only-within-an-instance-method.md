---
title: "&#39; &lt;palabra clave&gt;&#39; es válida sólo dentro de un método de instancia"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords: BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a61314c036cec0fd1412a9c844a610fbd1401add
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="39ltkeywordgt39-is-valid-only-within-an-instance-method"></a><span data-ttu-id="01d22-102">&#39; &lt;palabra clave&gt;&#39; es válida sólo dentro de un método de instancia</span><span class="sxs-lookup"><span data-stu-id="01d22-102">&#39;&lt;keyword&gt;&#39; is valid only within an instance method</span></span>
<span data-ttu-id="01d22-103">El `Me`, `MyClass`, y `MyBase` palabras clave hacen referencia a instancias de clase específica.</span><span class="sxs-lookup"><span data-stu-id="01d22-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="01d22-104">No se pueden usar dentro de un compartido `Function` o `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="01d22-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="01d22-105">**Id. de error:** BC30043</span><span class="sxs-lookup"><span data-stu-id="01d22-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="01d22-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="01d22-106">To correct this error</span></span>  
  
-   <span data-ttu-id="01d22-107">Quite la palabra clave del procedimiento o quite la `Shared` palabra clave de la declaración de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="01d22-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01d22-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="01d22-108">See Also</span></span>  
 [<span data-ttu-id="01d22-109">Asignación de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="01d22-109">Object Variable Assignment</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="01d22-110">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="01d22-110">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="01d22-111">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="01d22-111">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)

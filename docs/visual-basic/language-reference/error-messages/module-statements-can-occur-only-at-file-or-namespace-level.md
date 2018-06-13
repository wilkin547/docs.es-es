---
title: '&#39;Módulo&#39; instrucciones pueden ocurrir solo en el nivel de archivo o espacio de nombres'
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 53199c2d7081445dc5490d5c54c98f93ee7522eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593170"
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="6f09b-102">&#39;Módulo&#39; instrucciones pueden ocurrir solo en el nivel de archivo o espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6f09b-102">&#39;Module&#39; statements can occur only at file or namespace level</span></span>
<span data-ttu-id="6f09b-103">`Module` las instrucciones deben aparecer en la parte superior del archivo de origen inmediatamente después de `Option` y `Imports` instrucciones, los atributos globales y declaraciones de espacios de nombres, pero antes de todas las demás declaraciones.</span><span class="sxs-lookup"><span data-stu-id="6f09b-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="6f09b-104">**Id. de error:** BC30617</span><span class="sxs-lookup"><span data-stu-id="6f09b-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6f09b-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6f09b-105">To correct this error</span></span>  
  
-   <span data-ttu-id="6f09b-106">Mover el `Module` instrucción al principio de su archivo de origen o de declaración de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f09b-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f09b-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f09b-107">See Also</span></span>  
 [<span data-ttu-id="6f09b-108">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6f09b-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)

---
title: Las instrucciones 'Module' sólo pueden ocurrir en el nivel de archivo o de espacio de nombres
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 0820763cce9cc27f9a379ed5e766e0691a75f36b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271270"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="5e6cf-102">Las instrucciones 'Module' sólo pueden ocurrir en el nivel de archivo o de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="5e6cf-102">'Module' statements can occur only at file or namespace level</span></span>
<span data-ttu-id="5e6cf-103">`Module` las instrucciones deben aparecer en la parte superior del archivo de origen inmediatamente después de `Option` y `Imports` instrucciones, los atributos globales y las declaraciones de espacio de nombres, pero antes de todas las demás declaraciones.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="5e6cf-104">**Identificador de error:** BC30617</span><span class="sxs-lookup"><span data-stu-id="5e6cf-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5e6cf-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5e6cf-105">To correct this error</span></span>  
  
-   <span data-ttu-id="5e6cf-106">Mueva la instrucción `Module` a la parte superior de la declaración del espacio de nombres o el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e6cf-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e6cf-107">See also</span></span>
- [<span data-ttu-id="5e6cf-108">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5e6cf-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)

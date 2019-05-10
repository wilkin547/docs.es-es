---
title: Las instrucciones 'Module' sólo pueden ocurrir en el nivel de archivo o de espacio de nombres
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: fc3c102dbfe7c55e66093421bc11379d48ba000d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592096"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="a8934-102">Las instrucciones 'Module' sólo pueden ocurrir en el nivel de archivo o de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="a8934-102">'Module' statements can occur only at file or namespace level</span></span>
<span data-ttu-id="a8934-103">`Module` las instrucciones deben aparecer en la parte superior del archivo de origen inmediatamente después de `Option` y `Imports` instrucciones, los atributos globales y las declaraciones de espacio de nombres, pero antes de todas las demás declaraciones.</span><span class="sxs-lookup"><span data-stu-id="a8934-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="a8934-104">**Identificador de error:** BC30617</span><span class="sxs-lookup"><span data-stu-id="a8934-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a8934-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a8934-105">To correct this error</span></span>  
  
- <span data-ttu-id="a8934-106">Mueva la instrucción `Module` a la parte superior de la declaración del espacio de nombres o el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="a8934-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8934-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8934-107">See also</span></span>

- [<span data-ttu-id="a8934-108">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a8934-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)

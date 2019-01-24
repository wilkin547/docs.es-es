---
title: '&#39;Módulo&#39; instrucciones sólo pueden ocurrir en el nivel de archivo o espacio de nombres'
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: bdbf8df5942e9df4b9696aeea4e3492121efe21a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746317"
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="5f10f-102">&#39;Módulo&#39; instrucciones sólo pueden ocurrir en el nivel de archivo o espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="5f10f-102">&#39;Module&#39; statements can occur only at file or namespace level</span></span>
<span data-ttu-id="5f10f-103">`Module` las instrucciones deben aparecer en la parte superior del archivo de origen inmediatamente después de `Option` y `Imports` instrucciones, los atributos globales y las declaraciones de espacio de nombres, pero antes de todas las demás declaraciones.</span><span class="sxs-lookup"><span data-stu-id="5f10f-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="5f10f-104">**Identificador de error:** BC30617</span><span class="sxs-lookup"><span data-stu-id="5f10f-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5f10f-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5f10f-105">To correct this error</span></span>  
  
-   <span data-ttu-id="5f10f-106">Mueva la instrucción `Module` a la parte superior de la declaración del espacio de nombres o el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="5f10f-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f10f-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f10f-107">See also</span></span>
- [<span data-ttu-id="5f10f-108">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5f10f-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)

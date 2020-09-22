---
title: Las instrucciones 'Module' sólo pueden ocurrir en el nivel de archivo o de espacio de nombres
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 91e6c81bb64c259411cbef8a36629b8b320ea584
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873759"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="9ccb9-102">Las instrucciones 'Module' sólo pueden ocurrir en el nivel de archivo o de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="9ccb9-102">'Module' statements can occur only at file or namespace level</span></span>

<span data-ttu-id="9ccb9-103">`Module` las instrucciones deben aparecer en la parte superior del archivo de código fuente inmediatamente después de las `Option` `Imports` instrucciones y, los atributos globales y las declaraciones de espacio de nombres, pero antes de todas las demás declaraciones.</span><span class="sxs-lookup"><span data-stu-id="9ccb9-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="9ccb9-104">**Identificador de error:** BC30617</span><span class="sxs-lookup"><span data-stu-id="9ccb9-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9ccb9-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="9ccb9-105">To correct this error</span></span>  
  
- <span data-ttu-id="9ccb9-106">Mueva la instrucción `Module` a la parte superior de la declaración del espacio de nombres o el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="9ccb9-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ccb9-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ccb9-107">See also</span></span>

- [<span data-ttu-id="9ccb9-108">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="9ccb9-108">Module Statement</span></span>](../statements/module-statement.md)

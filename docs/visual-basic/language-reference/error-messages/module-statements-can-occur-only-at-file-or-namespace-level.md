---
title: Las instrucciones 'Module' sólo pueden ocurrir en el nivel de archivo o de espacio de nombres
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: b946a527d3de3a030ac03691c77afcf440f518ee
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160319"
---
# <a name="bc30617-module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="61e97-102">BC30617: las instrucciones ' module ' solo pueden aparecer en el nivel de archivo o de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="61e97-102">BC30617: 'Module' statements can occur only at file or namespace level</span></span>

<span data-ttu-id="61e97-103">`Module` las instrucciones deben aparecer en la parte superior del archivo de código fuente inmediatamente después de las `Option` `Imports` instrucciones y, los atributos globales y las declaraciones de espacio de nombres, pero antes de todas las demás declaraciones.</span><span class="sxs-lookup"><span data-stu-id="61e97-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>

 <span data-ttu-id="61e97-104">**Identificador de error:** BC30617</span><span class="sxs-lookup"><span data-stu-id="61e97-104">**Error ID:** BC30617</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="61e97-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="61e97-105">To correct this error</span></span>

- <span data-ttu-id="61e97-106">Mueva la instrucción `Module` a la parte superior de la declaración del espacio de nombres o el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="61e97-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>

## <a name="see-also"></a><span data-ttu-id="61e97-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="61e97-107">See also</span></span>

- [<span data-ttu-id="61e97-108">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="61e97-108">Module Statement</span></span>](../statements/module-statement.md)

---
title: Archivo ya abierto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: ce8f8bf96d7355e45b2df82e8a131472c2ed2367
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162757"
---
# <a name="file-already-open"></a><span data-ttu-id="efa7f-102">Archivo ya abierto</span><span class="sxs-lookup"><span data-stu-id="efa7f-102">File already open</span></span>

<span data-ttu-id="efa7f-103">A veces, un archivo debe cerrarse antes de que `FileOpen` se produzca otra operación.</span><span class="sxs-lookup"><span data-stu-id="efa7f-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="efa7f-104">Entre las causas posibles de este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="efa7f-104">Among the possible causes of this error are:</span></span>

- <span data-ttu-id="efa7f-105">`FileOpen`Se ejecutó una operación de modo de salida secuencial para un archivo que ya está abierto</span><span class="sxs-lookup"><span data-stu-id="efa7f-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>

- <span data-ttu-id="efa7f-106">Una instrucción hace referencia a un archivo abierto.</span><span class="sxs-lookup"><span data-stu-id="efa7f-106">A statement refers to an open file.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="efa7f-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="efa7f-107">To correct this error</span></span>

- <span data-ttu-id="efa7f-108">Cierre el archivo antes de ejecutar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="efa7f-108">Close the file before executing the statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="efa7f-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="efa7f-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>

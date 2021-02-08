---
description: 'Más información acerca de: el archivo ya está abierto'
title: Archivo ya abierto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 2f3345c15f4a3095a8e733c2c8424edb25b4dee6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796306"
---
# <a name="file-already-open"></a><span data-ttu-id="ecf8f-103">Archivo ya abierto</span><span class="sxs-lookup"><span data-stu-id="ecf8f-103">File already open</span></span>

<span data-ttu-id="ecf8f-104">A veces, un archivo debe cerrarse antes de que `FileOpen` se produzca otra operación.</span><span class="sxs-lookup"><span data-stu-id="ecf8f-104">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="ecf8f-105">Entre las causas posibles de este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="ecf8f-105">Among the possible causes of this error are:</span></span>

- <span data-ttu-id="ecf8f-106">`FileOpen`Se ejecutó una operación de modo de salida secuencial para un archivo que ya está abierto</span><span class="sxs-lookup"><span data-stu-id="ecf8f-106">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>

- <span data-ttu-id="ecf8f-107">Una instrucción hace referencia a un archivo abierto.</span><span class="sxs-lookup"><span data-stu-id="ecf8f-107">A statement refers to an open file.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="ecf8f-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ecf8f-108">To correct this error</span></span>

- <span data-ttu-id="ecf8f-109">Cierre el archivo antes de ejecutar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="ecf8f-109">Close the file before executing the statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="ecf8f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecf8f-110">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>

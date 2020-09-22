---
title: Archivo ya abierto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 97f9e13e6802e793f7c7baf1f03ec51205eb6d42
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874182"
---
# <a name="file-already-open"></a><span data-ttu-id="3841a-102">Archivo ya abierto</span><span class="sxs-lookup"><span data-stu-id="3841a-102">File already open</span></span>

<span data-ttu-id="3841a-103">A veces, un archivo debe cerrarse antes de que `FileOpen` se produzca otra operación.</span><span class="sxs-lookup"><span data-stu-id="3841a-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="3841a-104">Entre las causas posibles de este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="3841a-104">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="3841a-105">`FileOpen`Se ejecutó una operación de modo de salida secuencial para un archivo que ya está abierto</span><span class="sxs-lookup"><span data-stu-id="3841a-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
- <span data-ttu-id="3841a-106">Una instrucción hace referencia a un archivo abierto.</span><span class="sxs-lookup"><span data-stu-id="3841a-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3841a-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="3841a-107">To correct this error</span></span>  
  
1. <span data-ttu-id="3841a-108">Cierre el archivo antes de ejecutar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="3841a-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3841a-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3841a-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>

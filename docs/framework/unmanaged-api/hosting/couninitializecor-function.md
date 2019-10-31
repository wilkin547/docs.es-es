---
title: CoUninitializeCor (Función)
ms.date: 03/30/2017
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeCor
helpviewer_keywords:
- CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type:
- apiref
ms.openlocfilehash: eddc2f29da0efd9e56df710203b1d7621ffc27a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136864"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="14822-102">CoUninitializeCor (Función)</span><span class="sxs-lookup"><span data-stu-id="14822-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="14822-103">`CoUninitializeCor` está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="14822-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14822-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14822-104">Syntax</span></span>  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="14822-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14822-105">Remarks</span></span>  
 <span data-ttu-id="14822-106">No se puede descargar el Common Language Runtime de un proceso.</span><span class="sxs-lookup"><span data-stu-id="14822-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="14822-107">Para quitar completamente el Runtime de un proceso en ejecución, debe cerrar ese proceso.</span><span class="sxs-lookup"><span data-stu-id="14822-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14822-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="14822-108">See also</span></span>

- [<span data-ttu-id="14822-109">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="14822-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)

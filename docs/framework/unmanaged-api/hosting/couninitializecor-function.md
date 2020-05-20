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
ms.openlocfilehash: 8a8c2764398d737192190f91646d45f4edf3a0e4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616483"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="72c0d-102">CoUninitializeCor (Función)</span><span class="sxs-lookup"><span data-stu-id="72c0d-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="72c0d-103">`CoUninitializeCor` está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="72c0d-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72c0d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72c0d-104">Syntax</span></span>  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="72c0d-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="72c0d-105">Remarks</span></span>  
 <span data-ttu-id="72c0d-106">No se puede descargar el Common Language Runtime de un proceso.</span><span class="sxs-lookup"><span data-stu-id="72c0d-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="72c0d-107">Para quitar completamente el Runtime de un proceso en ejecución, debe cerrar ese proceso.</span><span class="sxs-lookup"><span data-stu-id="72c0d-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72c0d-108">Consulta también</span><span class="sxs-lookup"><span data-stu-id="72c0d-108">See also</span></span>

- [<span data-ttu-id="72c0d-109">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="72c0d-109">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)

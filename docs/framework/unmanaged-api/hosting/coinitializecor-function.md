---
title: CoInitializeCor (Función)
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
ms.openlocfilehash: 188f98504fa73c4a85615a4e688bae02d966b9b6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616754"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="6c3e8-102">CoInitializeCor (Función)</span><span class="sxs-lookup"><span data-stu-id="6c3e8-102">CoInitializeCor Function</span></span>
<span data-ttu-id="6c3e8-103">`CoInitializeCor` está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="6c3e8-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c3e8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c3e8-104">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="6c3e8-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6c3e8-105">Remarks</span></span>  
 <span data-ttu-id="6c3e8-106">Para inicializar el Common Language Runtime, use [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime (](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="6c3e8-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c3e8-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c3e8-107">Requirements</span></span>  
 <span data-ttu-id="6c3e8-108">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6c3e8-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c3e8-109">Consulta también</span><span class="sxs-lookup"><span data-stu-id="6c3e8-109">See also</span></span>

- [<span data-ttu-id="6c3e8-110">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="6c3e8-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)

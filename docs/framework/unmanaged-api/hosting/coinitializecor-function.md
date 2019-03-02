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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 556d26ac7e4fb8847f132d19bd2e749aff345abf
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57211850"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="aabce-102">CoInitializeCor (Función)</span><span class="sxs-lookup"><span data-stu-id="aabce-102">CoInitializeCor Function</span></span>
<span data-ttu-id="aabce-103">`CoInitializeCor` está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="aabce-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aabce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aabce-104">Syntax</span></span>  
  
```  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="aabce-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aabce-105">Remarks</span></span>  
 <span data-ttu-id="aabce-106">Para inicializar common language runtime, utilice [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="aabce-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aabce-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aabce-107">Requirements</span></span>  
 <span data-ttu-id="aabce-108">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="aabce-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aabce-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="aabce-109">See also</span></span>
- [<span data-ttu-id="aabce-110">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="aabce-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)

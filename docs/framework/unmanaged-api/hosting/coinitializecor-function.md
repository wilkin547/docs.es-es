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
ms.openlocfilehash: 8642c165c29f9ca63535a0efbb9dbb58d4660a49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160399"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="66ea0-102">CoInitializeCor (Función)</span><span class="sxs-lookup"><span data-stu-id="66ea0-102">CoInitializeCor Function</span></span>
`CoInitializeCor` <span data-ttu-id="66ea0-103">está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="66ea0-103">is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66ea0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66ea0-104">Syntax</span></span>  
  
```  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="66ea0-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="66ea0-105">Remarks</span></span>  
 <span data-ttu-id="66ea0-106">Para inicializar common language runtime, utilice [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="66ea0-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66ea0-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66ea0-107">Requirements</span></span>  
 <span data-ttu-id="66ea0-108">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="66ea0-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66ea0-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="66ea0-109">See also</span></span>

- [<span data-ttu-id="66ea0-110">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="66ea0-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)

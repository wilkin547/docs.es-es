---
title: ICLRDebugManager::SetSymbolReadingPolicy (Método)
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetSymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetSymbolReadingPolicy
helpviewer_keywords:
- ICLRDebugManager, SetSymbolREadingPolicy method
- SetSymbolReadingPolicy method [.NET Framework hosting]
- ICLRDebugManager::SetSymbolReadingPolicy method [.NET Framework hosting]
ms.assetid: bd921fa2-d377-4d79-acfc-64c38d4dcae9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2dc3d350f5c97736b3b65c814a668195aceef2b0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132826"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="ef29f-102">ICLRDebugManager::SetSymbolReadingPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="ef29f-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="ef29f-103">Establece la directiva para leer los archivos de programa (PDB) de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ef29f-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="ef29f-104">La directiva determina si se incluye información sobre archivos y números de línea en las pilas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ef29f-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef29f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef29f-105">Syntax</span></span>  
  
```  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef29f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef29f-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="ef29f-107">[in] Un miembro de la [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="ef29f-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef29f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ef29f-108">Return Value</span></span>  
  
|<span data-ttu-id="ef29f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ef29f-109">HRESULT</span></span>|<span data-ttu-id="ef29f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef29f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ef29f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef29f-111">S_OK</span></span>|<span data-ttu-id="ef29f-112">`SetSymbolReadingPolicy` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ef29f-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="ef29f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ef29f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ef29f-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ef29f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ef29f-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ef29f-115">E_FAIL</span></span>|<span data-ttu-id="ef29f-116">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="ef29f-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ef29f-117">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="ef29f-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ef29f-118">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ef29f-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ef29f-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef29f-119">Requirements</span></span>  
 <span data-ttu-id="ef29f-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef29f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef29f-121">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ef29f-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef29f-122">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef29f-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef29f-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef29f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef29f-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef29f-124">See also</span></span>

- [<span data-ttu-id="ef29f-125">ICLRDebugManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef29f-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)

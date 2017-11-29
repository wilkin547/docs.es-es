---
title: "ICLRDebugManager::SetSymbolReadingPolicy (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.SetSymbolReadingPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::SetSymbolReadingPolicy
helpviewer_keywords:
- ICLRDebugManager, SetSymbolREadingPolicy method
- SetSymbolReadingPolicy method [.NET Framework hosting]
- ICLRDebugManager::SetSymbolReadingPolicy method [.NET Framework hosting]
ms.assetid: bd921fa2-d377-4d79-acfc-64c38d4dcae9
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d116883c39b4400451ede07df83ac77893ce285c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="aa624-102">ICLRDebugManager::SetSymbolReadingPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="aa624-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="aa624-103">Establece la directiva para leer los archivos de programa (PDB) de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aa624-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="aa624-104">La directiva determina si se incluye información sobre los números de línea y los archivos en las pilas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="aa624-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa624-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa624-105">Syntax</span></span>  
  
```  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa624-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa624-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="aa624-107">[in] Un miembro de la [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="aa624-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa624-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aa624-108">Return Value</span></span>  
  
|<span data-ttu-id="aa624-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aa624-109">HRESULT</span></span>|<span data-ttu-id="aa624-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa624-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa624-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa624-111">S_OK</span></span>|<span data-ttu-id="aa624-112">`SetSymbolReadingPolicy`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="aa624-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="aa624-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aa624-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aa624-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="aa624-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aa624-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aa624-115">E_FAIL</span></span>|<span data-ttu-id="aa624-116">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="aa624-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aa624-117">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="aa624-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aa624-118">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="aa624-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa624-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa624-119">Requirements</span></span>  
 <span data-ttu-id="aa624-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa624-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa624-121">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aa624-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa624-122">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aa624-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa624-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa624-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa624-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa624-124">See Also</span></span>  
 [<span data-ttu-id="aa624-125">ICLRDebugManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa624-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)

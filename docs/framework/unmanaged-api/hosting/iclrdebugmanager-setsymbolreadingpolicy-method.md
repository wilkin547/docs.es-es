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
ms.openlocfilehash: 2921484cb2baa92593ddb0335cf7b20c5c0f33eb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773010"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="7e835-102">ICLRDebugManager::SetSymbolReadingPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="7e835-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="7e835-103">Establece la directiva para leer los archivos de programa (PDB) de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7e835-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="7e835-104">La directiva determina si se incluye información sobre archivos y números de línea en las pilas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7e835-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e835-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e835-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e835-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e835-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="7e835-107">[in] Un miembro de la [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="7e835-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e835-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7e835-108">Return Value</span></span>  
  
|<span data-ttu-id="7e835-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e835-109">HRESULT</span></span>|<span data-ttu-id="7e835-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7e835-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e835-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e835-111">S_OK</span></span>|<span data-ttu-id="7e835-112">`SetSymbolReadingPolicy` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7e835-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="7e835-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7e835-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7e835-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7e835-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7e835-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7e835-115">E_FAIL</span></span>|<span data-ttu-id="7e835-116">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="7e835-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7e835-117">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="7e835-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7e835-118">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7e835-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7e835-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e835-119">Requirements</span></span>  
 <span data-ttu-id="7e835-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e835-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e835-121">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7e835-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e835-122">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e835-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e835-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e835-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e835-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e835-124">See also</span></span>

- [<span data-ttu-id="7e835-125">ICLRDebugManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e835-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)

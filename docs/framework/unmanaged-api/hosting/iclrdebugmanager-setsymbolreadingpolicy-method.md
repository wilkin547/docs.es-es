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
ms.openlocfilehash: 6737b953f39c1087d01f3fb864d84340a6968aba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129355"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="1d20a-102">ICLRDebugManager::SetSymbolReadingPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="1d20a-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="1d20a-103">Establece la Directiva para leer archivos de base de datos de programa (PDB).</span><span class="sxs-lookup"><span data-stu-id="1d20a-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="1d20a-104">La Directiva determina si la información sobre los números de línea y los archivos se incluye en las pilas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1d20a-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d20a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d20a-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d20a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1d20a-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="1d20a-107">de Miembro de la enumeración [ESymbolReadingPolicy (](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="1d20a-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d20a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1d20a-108">Return Value</span></span>  
  
|<span data-ttu-id="1d20a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d20a-109">HRESULT</span></span>|<span data-ttu-id="1d20a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d20a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d20a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d20a-111">S_OK</span></span>|<span data-ttu-id="1d20a-112">`SetSymbolReadingPolicy` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1d20a-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="1d20a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d20a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d20a-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1d20a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1d20a-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d20a-115">E_FAIL</span></span>|<span data-ttu-id="1d20a-116">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="1d20a-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1d20a-117">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="1d20a-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1d20a-118">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1d20a-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d20a-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d20a-119">Requirements</span></span>  
 <span data-ttu-id="1d20a-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d20a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d20a-121">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1d20a-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d20a-122">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1d20a-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d20a-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d20a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d20a-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d20a-124">See also</span></span>

- [<span data-ttu-id="1d20a-125">ICLRDebugManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d20a-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)

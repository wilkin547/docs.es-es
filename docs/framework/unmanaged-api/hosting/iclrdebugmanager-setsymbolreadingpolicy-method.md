---
description: 'Más información sobre: ICLRDebugManager:: SetSymbolReadingPolicy ((método)'
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
ms.openlocfilehash: 2c0862f3c572808ffbf418b275e1ad1c62c2ac89
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781953"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="c3d4a-103">ICLRDebugManager::SetSymbolReadingPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="c3d4a-103">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>

<span data-ttu-id="c3d4a-104">Establece la Directiva para leer archivos de base de datos de programa (PDB).</span><span class="sxs-lookup"><span data-stu-id="c3d4a-104">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="c3d4a-105">La Directiva determina si la información sobre los números de línea y los archivos se incluye en las pilas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c3d4a-105">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3d4a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3d4a-106">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3d4a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3d4a-107">Parameters</span></span>  

 `policy`  
 <span data-ttu-id="c3d4a-108">de Miembro de la enumeración [ESymbolReadingPolicy (](esymbolreadingpolicy-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="c3d4a-108">[in] A member of the [ESymbolReadingPolicy](esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3d4a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c3d4a-109">Return Value</span></span>  
  
|<span data-ttu-id="c3d4a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c3d4a-110">HRESULT</span></span>|<span data-ttu-id="c3d4a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3d4a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c3d4a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3d4a-112">S_OK</span></span>|<span data-ttu-id="c3d4a-113">`SetSymbolReadingPolicy` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c3d4a-113">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="c3d4a-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c3d4a-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c3d4a-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c3d4a-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c3d4a-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c3d4a-116">E_FAIL</span></span>|<span data-ttu-id="c3d4a-117">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c3d4a-117">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c3d4a-118">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c3d4a-118">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c3d4a-119">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c3d4a-119">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3d4a-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3d4a-120">Requirements</span></span>  

 <span data-ttu-id="c3d4a-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3d4a-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3d4a-122">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c3d4a-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3d4a-123">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c3d4a-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3d4a-124">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3d4a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3d4a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3d4a-125">See also</span></span>

- [<span data-ttu-id="c3d4a-126">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c3d4a-126">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)

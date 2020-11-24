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
ms.openlocfilehash: a311166e79f930e763b0338451f6356c8c93f929
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670150"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="f666c-102">ICLRDebugManager::SetSymbolReadingPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="f666c-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>

<span data-ttu-id="f666c-103">Establece la Directiva para leer archivos de base de datos de programa (PDB).</span><span class="sxs-lookup"><span data-stu-id="f666c-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="f666c-104">La Directiva determina si la información sobre los números de línea y los archivos se incluye en las pilas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f666c-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f666c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f666c-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f666c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f666c-106">Parameters</span></span>  

 `policy`  
 <span data-ttu-id="f666c-107">de Miembro de la enumeración [ESymbolReadingPolicy (](esymbolreadingpolicy-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="f666c-107">[in] A member of the [ESymbolReadingPolicy](esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f666c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f666c-108">Return Value</span></span>  
  
|<span data-ttu-id="f666c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f666c-109">HRESULT</span></span>|<span data-ttu-id="f666c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="f666c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f666c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f666c-111">S_OK</span></span>|<span data-ttu-id="f666c-112">`SetSymbolReadingPolicy` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f666c-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="f666c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f666c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f666c-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f666c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f666c-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f666c-115">E_FAIL</span></span>|<span data-ttu-id="f666c-116">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="f666c-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f666c-117">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f666c-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f666c-118">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f666c-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f666c-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f666c-119">Requirements</span></span>  

 <span data-ttu-id="f666c-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f666c-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f666c-121">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f666c-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f666c-122">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f666c-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f666c-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f666c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f666c-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f666c-124">See also</span></span>

- [<span data-ttu-id="f666c-125">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f666c-125">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)

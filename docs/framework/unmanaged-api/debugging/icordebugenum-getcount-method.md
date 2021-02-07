---
description: 'Más información acerca de: ICorDebugEnum:: GetCount (método)'
title: ICorDebugEnum::GetCount (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::GetCount
helpviewer_keywords:
- ICorDebugEnum::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: d8a74304-1cb2-4977-a21d-e1af48c563ff
topic_type:
- apiref
ms.openlocfilehash: 38fa85958ea0c6945a5575d12700701ed355891d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694565"
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="2ff97-103">ICorDebugEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="2ff97-103">ICorDebugEnum::GetCount Method</span></span>

<span data-ttu-id="2ff97-104">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="2ff97-104">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ff97-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ff97-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ff97-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2ff97-106">Parameters</span></span>  

 `pcelt`  
 <span data-ttu-id="2ff97-107">enuncia Puntero al número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="2ff97-107">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ff97-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ff97-108">Requirements</span></span>  

 <span data-ttu-id="2ff97-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ff97-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ff97-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ff97-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ff97-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ff97-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ff97-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ff97-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

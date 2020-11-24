---
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
ms.openlocfilehash: 7293528bb119c23f6ef39405a82180252b336735
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687247"
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="47e01-102">ICorDebugEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="47e01-102">ICorDebugEnum::GetCount Method</span></span>

<span data-ttu-id="47e01-103">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="47e01-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47e01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47e01-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47e01-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47e01-105">Parameters</span></span>  

 `pcelt`  
 <span data-ttu-id="47e01-106">enuncia Puntero al número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="47e01-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47e01-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47e01-107">Requirements</span></span>  

 <span data-ttu-id="47e01-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47e01-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47e01-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47e01-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47e01-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47e01-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47e01-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47e01-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

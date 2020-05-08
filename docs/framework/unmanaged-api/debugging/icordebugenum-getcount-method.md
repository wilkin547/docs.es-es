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
ms.openlocfilehash: 90ba690897abced2d4f6282eedef91712d8ceeca
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976348"
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="48296-102">ICorDebugEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="48296-102">ICorDebugEnum::GetCount Method</span></span>
<span data-ttu-id="48296-103">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="48296-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48296-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48296-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48296-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48296-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="48296-106">enuncia Puntero al número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="48296-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48296-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48296-107">Requirements</span></span>  
 <span data-ttu-id="48296-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48296-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48296-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48296-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48296-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48296-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48296-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48296-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

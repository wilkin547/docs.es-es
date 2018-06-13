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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5eddad89c60f25c957a06822d54cc73501b974ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415634"
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="d6949-102">ICorDebugEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="d6949-102">ICorDebugEnum::GetCount Method</span></span>
<span data-ttu-id="d6949-103">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="d6949-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6949-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6949-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6949-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6949-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="d6949-106">[out] Un puntero al número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="d6949-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6949-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6949-107">Requirements</span></span>  
 <span data-ttu-id="d6949-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6949-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6949-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6949-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6949-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6949-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6949-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6949-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

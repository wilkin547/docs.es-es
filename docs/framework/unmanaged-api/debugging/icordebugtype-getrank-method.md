---
title: ICorDebugType::GetRank (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetRank
helpviewer_keywords:
- GetRank method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetRank method [.NET Framework debugging]
ms.assetid: 72d3d927-f590-4f2d-8f60-448f3dfb96af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 134fe55de71e3d6a9a68249febc4c70f11d4f36f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993868"
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="e4ffb-102">ICorDebugType::GetRank (Método)</span><span class="sxs-lookup"><span data-stu-id="e4ffb-102">ICorDebugType::GetRank Method</span></span>
<span data-ttu-id="e4ffb-103">Obtiene el número de dimensiones en un tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-103">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4ffb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4ffb-104">Syntax</span></span>  
  
```  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4ffb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e4ffb-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="e4ffb-106">[out] Un puntero al número de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-106">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4ffb-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4ffb-107">Requirements</span></span>  
 <span data-ttu-id="e4ffb-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4ffb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4ffb-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4ffb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4ffb-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4ffb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4ffb-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4ffb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

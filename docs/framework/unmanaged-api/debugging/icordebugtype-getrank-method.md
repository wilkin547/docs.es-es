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
ms.openlocfilehash: 9f112e0d064041a877963939b78029da08bbbed1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417659"
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="8c270-102">ICorDebugType::GetRank (Método)</span><span class="sxs-lookup"><span data-stu-id="8c270-102">ICorDebugType::GetRank Method</span></span>
<span data-ttu-id="8c270-103">Obtiene el número de dimensiones de un tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="8c270-103">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c270-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c270-104">Syntax</span></span>  
  
```  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c270-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8c270-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="8c270-106">[out] Un puntero al número de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="8c270-106">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c270-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c270-107">Requirements</span></span>  
 <span data-ttu-id="8c270-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c270-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c270-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c270-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c270-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c270-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c270-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c270-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

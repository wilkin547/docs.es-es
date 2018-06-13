---
title: ICorDebugFunction::GetCurrentVersionNumber (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61b2de0595ac9330d9bb4e8e2dcbe4591928eb91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413891"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="557d9-102">ICorDebugFunction::GetCurrentVersionNumber (Método)</span><span class="sxs-lookup"><span data-stu-id="557d9-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="557d9-103">Obtiene el número de versión de la edición más reciente realizada en la función representada por este objeto ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="557d9-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="557d9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="557d9-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="557d9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="557d9-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="557d9-106">[out] Un puntero a un valor entero que es el número de versión de la edición más reciente realizada en esta función.</span><span class="sxs-lookup"><span data-stu-id="557d9-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="557d9-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="557d9-107">Remarks</span></span>  
 <span data-ttu-id="557d9-108">El número de versión de la edición más reciente realizada en esta función puede ser mayor que el número de versión de la propia función.</span><span class="sxs-lookup"><span data-stu-id="557d9-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="557d9-109">Utilice la [ICorDebugFunction2:: GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) método o la [ICorDebugCode:: GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) método para recuperar el número de versión de la función.</span><span class="sxs-lookup"><span data-stu-id="557d9-109">Use either the [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="557d9-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="557d9-110">Requirements</span></span>  
 <span data-ttu-id="557d9-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="557d9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="557d9-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="557d9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="557d9-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="557d9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="557d9-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="557d9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

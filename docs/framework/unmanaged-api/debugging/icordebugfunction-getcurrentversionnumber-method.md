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
ms.openlocfilehash: 0530ba742a739003bfa33079ad75cb1e6f5f5e59
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124018"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="2ca19-102">ICorDebugFunction::GetCurrentVersionNumber (Método)</span><span class="sxs-lookup"><span data-stu-id="2ca19-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="2ca19-103">Obtiene el número de versión de la edición más reciente realizada en la función representada por este objeto ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="2ca19-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ca19-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ca19-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ca19-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2ca19-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="2ca19-106">enuncia Un puntero a un valor entero que es el número de versión de la edición más reciente realizada a esta función.</span><span class="sxs-lookup"><span data-stu-id="2ca19-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ca19-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2ca19-107">Remarks</span></span>  
 <span data-ttu-id="2ca19-108">El número de versión de la última edición realizada a esta función puede ser mayor que el número de versión de la propia función.</span><span class="sxs-lookup"><span data-stu-id="2ca19-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="2ca19-109">Use el método [ICorDebugFunction2:: GetVersionNumber (](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) o el método [ICorDebugCode:: GetVersionNumber (](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) para recuperar el número de versión de la función.</span><span class="sxs-lookup"><span data-stu-id="2ca19-109">Use either the [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ca19-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ca19-110">Requirements</span></span>  
 <span data-ttu-id="2ca19-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ca19-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ca19-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ca19-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ca19-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ca19-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ca19-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ca19-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

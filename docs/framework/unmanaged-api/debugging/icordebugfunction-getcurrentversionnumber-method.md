---
description: 'Más información acerca de: ICorDebugFunction:: GetCurrentVersionNumber ((método)'
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
ms.openlocfilehash: ccc96755ac74624a00b806e3f569f39f2d6059f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692542"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="19f4a-103">ICorDebugFunction::GetCurrentVersionNumber (Método)</span><span class="sxs-lookup"><span data-stu-id="19f4a-103">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>

<span data-ttu-id="19f4a-104">Obtiene el número de versión de la edición más reciente realizada en la función representada por este objeto ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="19f4a-104">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19f4a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19f4a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19f4a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19f4a-106">Parameters</span></span>  

 `pnCurrentVersion`  
 <span data-ttu-id="19f4a-107">enuncia Un puntero a un valor entero que es el número de versión de la edición más reciente realizada a esta función.</span><span class="sxs-lookup"><span data-stu-id="19f4a-107">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19f4a-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="19f4a-108">Remarks</span></span>  

 <span data-ttu-id="19f4a-109">El número de versión de la última edición realizada a esta función puede ser mayor que el número de versión de la propia función.</span><span class="sxs-lookup"><span data-stu-id="19f4a-109">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="19f4a-110">Use el método [ICorDebugFunction2:: GetVersionNumber (](icordebugfunction2-getversionnumber-method.md) o el método [ICorDebugCode:: GetVersionNumber (](icordebugcode-getversionnumber-method.md) para recuperar el número de versión de la función.</span><span class="sxs-lookup"><span data-stu-id="19f4a-110">Use either the [ICorDebugFunction2::GetVersionNumber](icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19f4a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19f4a-111">Requirements</span></span>  

 <span data-ttu-id="19f4a-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19f4a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19f4a-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19f4a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19f4a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19f4a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19f4a-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19f4a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

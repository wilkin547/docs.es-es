---
title: ICorDebugValue::GetAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b88c49ba93ff3c4cc3f5c7a656dfa5da6e82109e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559849"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="8860e-102">ICorDebugValue::GetAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="8860e-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="8860e-103">Obtiene la dirección de este objeto de "ICorDebugValue", que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="8860e-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8860e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8860e-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8860e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8860e-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="8860e-106">[out] Puntero a un `CORDB_ADDRESS` objeto que especifica la dirección de este objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="8860e-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8860e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8860e-107">Remarks</span></span>  
 <span data-ttu-id="8860e-108">Si el valor no está disponible, se devuelve 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="8860e-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="8860e-109">Esto podría suceder si el valor es al menos en parte en los registros o almacenado en un identificador de recolector de elementos no utilizados (`GCHandle`).</span><span class="sxs-lookup"><span data-stu-id="8860e-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8860e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8860e-110">Requirements</span></span>  
 <span data-ttu-id="8860e-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8860e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8860e-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8860e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8860e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8860e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8860e-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8860e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8860e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8860e-115">See also</span></span>


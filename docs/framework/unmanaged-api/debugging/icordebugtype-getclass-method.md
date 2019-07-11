---
title: ICorDebugType::GetClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd68df77adafb8b21e7684b28fe978722ca37e16
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736797"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="8bc27-102">ICorDebugType::GetClass (Método)</span><span class="sxs-lookup"><span data-stu-id="8bc27-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="8bc27-103">Obtiene un puntero de interfaz a ICorDebugClass que representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="8bc27-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bc27-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8bc27-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bc27-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8bc27-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="8bc27-106">[out] Un puntero a la dirección de un `ICorDebugClass` interfaz que representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="8bc27-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bc27-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8bc27-107">Remarks</span></span>  
 <span data-ttu-id="8bc27-108">`GetClass` se puede llamar sólo bajo ciertas condiciones.</span><span class="sxs-lookup"><span data-stu-id="8bc27-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="8bc27-109">Llame a [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) antes de llamar a `GetClass`.</span><span class="sxs-lookup"><span data-stu-id="8bc27-109">Call [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="8bc27-110">Si `ICorDebugType::GetType` devuelve un valor CorElementType ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, `GetClass` se puede llamar para obtener el tipo sin instancias de un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="8bc27-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bc27-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8bc27-111">Requirements</span></span>  
 <span data-ttu-id="8bc27-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bc27-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bc27-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bc27-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bc27-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bc27-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bc27-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bc27-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

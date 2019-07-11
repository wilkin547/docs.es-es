---
title: ICorDebugProcess5::GetObject (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetObject method [.NET Framework debugging]
ms.assetid: c8111502-5a20-447f-9dc2-76e8acd7ed5a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ec3dc37984228565b4a3fcc560d3857a1c1e46d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767330"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="2acda-102">ICorDebugProcess5::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="2acda-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="2acda-103">Convierte una dirección de objeto a un objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="2acda-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2acda-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2acda-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,   
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2acda-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2acda-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="2acda-106">[in] La dirección del objeto.</span><span class="sxs-lookup"><span data-stu-id="2acda-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="2acda-107">[out] Un puntero a la dirección de un objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="2acda-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2acda-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2acda-108">Remarks</span></span>  
 <span data-ttu-id="2acda-109">Si `addr` no apunta a un objeto administrado válido, el `GetObject` devuelve del método `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="2acda-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2acda-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2acda-110">Requirements</span></span>  
 <span data-ttu-id="2acda-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2acda-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2acda-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2acda-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2acda-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2acda-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2acda-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2acda-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2acda-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2acda-115">See also</span></span>

- [<span data-ttu-id="2acda-116">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2acda-116">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="2acda-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2acda-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

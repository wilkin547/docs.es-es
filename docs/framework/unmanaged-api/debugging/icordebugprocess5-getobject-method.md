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
ms.openlocfilehash: 4b48132ee60bcaebb218d8f583de6558372f5055
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178603"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="d05c5-102">ICorDebugProcess5::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="d05c5-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="d05c5-103">Convierte una dirección de objeto en un objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="d05c5-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d05c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d05c5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d05c5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d05c5-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="d05c5-106">[en] La dirección del objeto.</span><span class="sxs-lookup"><span data-stu-id="d05c5-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="d05c5-107">[fuera] Puntero a la dirección de un objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="d05c5-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d05c5-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d05c5-108">Remarks</span></span>  
 <span data-ttu-id="d05c5-109">Si `addr` no apunta a un objeto `GetObject` administrado `E_FAIL`válido, el método devuelve .</span><span class="sxs-lookup"><span data-stu-id="d05c5-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d05c5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d05c5-110">Requirements</span></span>  
 <span data-ttu-id="d05c5-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d05c5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d05c5-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d05c5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d05c5-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d05c5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d05c5-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d05c5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d05c5-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d05c5-115">See also</span></span>

- [<span data-ttu-id="d05c5-116">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d05c5-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="d05c5-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d05c5-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

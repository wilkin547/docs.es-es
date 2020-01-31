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
ms.openlocfilehash: 540ca78c5548d4fbdd3338671ea02314736f15cd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792362"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="92a4f-102">ICorDebugProcess5::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="92a4f-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="92a4f-103">Convierte una dirección de objeto en un objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="92a4f-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92a4f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92a4f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,   
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92a4f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="92a4f-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="92a4f-106">de Dirección del objeto.</span><span class="sxs-lookup"><span data-stu-id="92a4f-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="92a4f-107">enuncia Puntero a la dirección de un objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="92a4f-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92a4f-108">Notas</span><span class="sxs-lookup"><span data-stu-id="92a4f-108">Remarks</span></span>  
 <span data-ttu-id="92a4f-109">Si `addr` no apunta a un objeto administrado válido, el método `GetObject` devuelve `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="92a4f-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92a4f-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="92a4f-110">Requirements</span></span>  
 <span data-ttu-id="92a4f-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92a4f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92a4f-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92a4f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92a4f-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92a4f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92a4f-114">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92a4f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92a4f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="92a4f-115">See also</span></span>

- [<span data-ttu-id="92a4f-116">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="92a4f-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="92a4f-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="92a4f-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

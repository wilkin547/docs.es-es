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
ms.openlocfilehash: de570507c4312f09def0908b9d56e5371c63527e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207292"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="1f94b-102">ICorDebugProcess5::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="1f94b-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="1f94b-103">Convierte una dirección de objeto en un objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="1f94b-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f94b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f94b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f94b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1f94b-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="1f94b-106">de Dirección del objeto.</span><span class="sxs-lookup"><span data-stu-id="1f94b-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="1f94b-107">enuncia Puntero a la dirección de un objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="1f94b-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f94b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1f94b-108">Remarks</span></span>  
 <span data-ttu-id="1f94b-109">Si no `addr` señala a un objeto administrado válido, el `GetObject` método devuelve `E_FAIL` .</span><span class="sxs-lookup"><span data-stu-id="1f94b-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f94b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f94b-110">Requirements</span></span>  
 <span data-ttu-id="1f94b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f94b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f94b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f94b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f94b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f94b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f94b-114">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f94b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f94b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f94b-115">See also</span></span>

- [<span data-ttu-id="1f94b-116">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f94b-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="1f94b-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="1f94b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

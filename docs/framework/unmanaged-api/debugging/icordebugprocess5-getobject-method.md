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
ms.openlocfilehash: ff2913399e1dbeb33bbfb697058db3caf2a8d1fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713111"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="d4adc-102">ICorDebugProcess5::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="d4adc-102">ICorDebugProcess5::GetObject Method</span></span>

<span data-ttu-id="d4adc-103">Convierte una dirección de objeto en un objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="d4adc-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4adc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4adc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4adc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4adc-105">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="d4adc-106">de Dirección del objeto.</span><span class="sxs-lookup"><span data-stu-id="d4adc-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="d4adc-107">enuncia Puntero a la dirección de un objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="d4adc-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4adc-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d4adc-108">Remarks</span></span>  

 <span data-ttu-id="d4adc-109">Si no `addr` señala a un objeto administrado válido, el `GetObject` método devuelve `E_FAIL` .</span><span class="sxs-lookup"><span data-stu-id="d4adc-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4adc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4adc-110">Requirements</span></span>  

 <span data-ttu-id="d4adc-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4adc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4adc-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4adc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4adc-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4adc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4adc-114">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4adc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4adc-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d4adc-115">See also</span></span>

- [<span data-ttu-id="d4adc-116">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4adc-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="d4adc-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d4adc-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

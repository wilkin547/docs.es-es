---
title: Método de ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: f3e64def16fb2817244ef7669ff4bb7fef0bd07c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684453"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="8dbc6-102">Método de ICorDebugAppDomain4::GetObjectForCCW</span><span class="sxs-lookup"><span data-stu-id="8dbc6-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>

<span data-ttu-id="8dbc6-103">Obtiene un objeto administrado de un puntero de contenedor CCW (COM callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="8dbc6-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dbc6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8dbc6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dbc6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8dbc6-105">Parameters</span></span>  

 `ccwPointer`  
 <span data-ttu-id="8dbc6-106">[in] Puntero de contenedor CCW (COM callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="8dbc6-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="8dbc6-107">enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el objeto administrado que corresponde al puntero CCW especificado.</span><span class="sxs-lookup"><span data-stu-id="8dbc6-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dbc6-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8dbc6-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dbc6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8dbc6-109">Requirements</span></span>  

 <span data-ttu-id="8dbc6-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8dbc6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dbc6-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8dbc6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8dbc6-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8dbc6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8dbc6-113">**.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dbc6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dbc6-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8dbc6-114">See also</span></span>

- [<span data-ttu-id="8dbc6-115">Interfaz de ICorDebugAppDomain4</span><span class="sxs-lookup"><span data-stu-id="8dbc6-115">ICorDebugAppDomain4 Interface</span></span>](icordebugappdomain4-interface.md)
- [<span data-ttu-id="8dbc6-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="8dbc6-116">Debugging Interfaces</span></span>](debugging-interfaces.md)

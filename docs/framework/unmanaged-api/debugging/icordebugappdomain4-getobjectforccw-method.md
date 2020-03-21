---
title: Método de ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 10d32314e46aba4f030b294cadc3cbb36e8742f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179048"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="3f438-102">Método de ICorDebugAppDomain4::GetObjectForCCW</span><span class="sxs-lookup"><span data-stu-id="3f438-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="3f438-103">Obtiene un objeto administrado de un puntero de contenedor CCW (COM callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="3f438-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f438-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f438-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f438-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f438-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="3f438-106">[in] Puntero de contenedor CCW (COM callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="3f438-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="3f438-107">[fuera] Puntero a la dirección de un objeto "ICorDebugValue" que representa el objeto administrado que corresponde al puntero CCW especificado.</span><span class="sxs-lookup"><span data-stu-id="3f438-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f438-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3f438-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f438-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f438-109">Requirements</span></span>  
 <span data-ttu-id="3f438-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f438-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f438-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f438-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f438-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f438-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f438-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f438-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f438-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f438-114">See also</span></span>

- [<span data-ttu-id="3f438-115">Interfaz de ICorDebugAppDomain4</span><span class="sxs-lookup"><span data-stu-id="3f438-115">ICorDebugAppDomain4 Interface</span></span>](icordebugappdomain4-interface.md)
- [<span data-ttu-id="3f438-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3f438-116">Debugging Interfaces</span></span>](debugging-interfaces.md)

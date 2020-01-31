---
title: Método de ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 50f46394c809321f0bd256e4c8d75b76fc7c2c70
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784859"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="bb160-102">Método de ICorDebugAppDomain4::GetObjectForCCW</span><span class="sxs-lookup"><span data-stu-id="bb160-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="bb160-103">Obtiene un objeto administrado de un puntero de contenedor CCW (COM callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="bb160-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb160-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb160-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb160-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="bb160-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="bb160-106">[in] Puntero de contenedor CCW (COM callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="bb160-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="bb160-107">enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el objeto administrado que corresponde al puntero CCW especificado.</span><span class="sxs-lookup"><span data-stu-id="bb160-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb160-108">Notas</span><span class="sxs-lookup"><span data-stu-id="bb160-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb160-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="bb160-109">Requirements</span></span>  
 <span data-ttu-id="bb160-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb160-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb160-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb160-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb160-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb160-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb160-113">**.NET Framework versiones:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb160-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb160-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb160-114">See also</span></span>

- [<span data-ttu-id="bb160-115">ICorDebugAppDomain4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb160-115">ICorDebugAppDomain4 Interface</span></span>](icordebugappdomain4-interface.md)
- [<span data-ttu-id="bb160-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="bb160-116">Debugging Interfaces</span></span>](debugging-interfaces.md)

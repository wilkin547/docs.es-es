---
title: Método de ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 8b046eb5926bb9aa4738e8fff8e61b0b7c23a3aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088826"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="3a856-102">Método de ICorDebugAppDomain4::GetObjectForCCW</span><span class="sxs-lookup"><span data-stu-id="3a856-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="3a856-103">Obtiene un objeto administrado de un puntero de contenedor CCW (COM callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="3a856-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a856-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a856-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a856-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a856-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="3a856-106">[in] Puntero de contenedor CCW (COM callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="3a856-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="3a856-107">enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el objeto administrado que corresponde al puntero CCW especificado.</span><span class="sxs-lookup"><span data-stu-id="3a856-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a856-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a856-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a856-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a856-109">Requirements</span></span>  
 <span data-ttu-id="3a856-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a856-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a856-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a856-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a856-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a856-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a856-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a856-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a856-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a856-114">See also</span></span>

- [<span data-ttu-id="3a856-115">ICorDebugAppDomain4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a856-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)
- [<span data-ttu-id="3a856-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3a856-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

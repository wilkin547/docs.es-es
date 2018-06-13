---
title: Método de ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1089668aa19747f5f694360ebb87098e2df9ad4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405556"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="661b7-102">Método de ICorDebugAppDomain4::GetObjectForCCW</span><span class="sxs-lookup"><span data-stu-id="661b7-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="661b7-103">Obtiene un objeto administrado de un puntero de contenedor CCW (COM callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="661b7-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="661b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="661b7-104">Syntax</span></span>  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="661b7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="661b7-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="661b7-106">[in] Puntero de contenedor CCW (COM callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="661b7-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="661b7-107">[out] Un puntero a la dirección de un objeto de "ICorDebugValue" que representa el objeto administrado que corresponde al puntero CCW especificado.</span><span class="sxs-lookup"><span data-stu-id="661b7-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="661b7-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="661b7-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="661b7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="661b7-109">Requirements</span></span>  
 <span data-ttu-id="661b7-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="661b7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="661b7-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="661b7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="661b7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="661b7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="661b7-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="661b7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="661b7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="661b7-114">See Also</span></span>  
 [<span data-ttu-id="661b7-115">ICorDebugAppDomain4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="661b7-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 [<span data-ttu-id="661b7-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="661b7-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

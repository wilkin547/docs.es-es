---
description: 'Más información sobre: ICorDebugAppDomain4:: GetObjectForCCW (método)'
title: Método de ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 5ba4923c933d02f5d6ad5c1fd8c4d0e2ddb410d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754139"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="4cc7d-103">Método de ICorDebugAppDomain4::GetObjectForCCW</span><span class="sxs-lookup"><span data-stu-id="4cc7d-103">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>

<span data-ttu-id="4cc7d-104">Obtiene un objeto administrado de un puntero de contenedor CCW (COM callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="4cc7d-104">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cc7d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4cc7d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cc7d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4cc7d-106">Parameters</span></span>  

 `ccwPointer`  
 <span data-ttu-id="4cc7d-107">[in] Puntero de contenedor CCW (COM callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="4cc7d-107">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="4cc7d-108">enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el objeto administrado que corresponde al puntero CCW especificado.</span><span class="sxs-lookup"><span data-stu-id="4cc7d-108">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cc7d-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4cc7d-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cc7d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4cc7d-110">Requirements</span></span>  

 <span data-ttu-id="4cc7d-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cc7d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cc7d-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4cc7d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cc7d-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cc7d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cc7d-114">**.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cc7d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc7d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cc7d-115">See also</span></span>

- [<span data-ttu-id="4cc7d-116">Interfaz de ICorDebugAppDomain4</span><span class="sxs-lookup"><span data-stu-id="4cc7d-116">ICorDebugAppDomain4 Interface</span></span>](icordebugappdomain4-interface.md)
- [<span data-ttu-id="4cc7d-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="4cc7d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

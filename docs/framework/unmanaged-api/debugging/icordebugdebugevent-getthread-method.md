---
title: Método ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5b4a15f637526cd2faadd2d9d3da143c40140f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414910"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="6498f-102">Método ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="6498f-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="6498f-103">Obtiene el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="6498f-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6498f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6498f-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6498f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6498f-105">Parameters</span></span>  
 <span data-ttu-id="6498f-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="6498f-106">ppThread</span></span>  
 <span data-ttu-id="6498f-107">[out] Un puntero a la dirección de un objeto ICorDebugThread que representa el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="6498f-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6498f-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6498f-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6498f-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6498f-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6498f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6498f-110">Requirements</span></span>  
 <span data-ttu-id="6498f-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6498f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6498f-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6498f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6498f-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6498f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6498f-114">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6498f-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6498f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6498f-115">See Also</span></span>  
 [<span data-ttu-id="6498f-116">ICorDebugDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6498f-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [<span data-ttu-id="6498f-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6498f-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

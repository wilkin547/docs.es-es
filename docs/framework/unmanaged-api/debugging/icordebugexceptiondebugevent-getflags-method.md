---
description: 'Más información acerca de: ICorDebugExceptionDebugEvent:: GetFlags (método)'
title: ICorDebugExceptionDebugEvent::GetFlags (método)
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 54a6c9b0dff2346ca130f80e72fe06dbb3017f10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693478"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="a3c63-103">ICorDebugExceptionDebugEvent::GetFlags (método)</span><span class="sxs-lookup"><span data-stu-id="a3c63-103">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>

<span data-ttu-id="a3c63-104">Obtiene una marca que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="a3c63-104">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3c63-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3c63-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3c63-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3c63-106">Parameters</span></span>  

 `pdwFlags`  
 <span data-ttu-id="a3c63-107">enuncia Un puntero a un valor de [cordebugexceptionflags (](cordebugexceptionflags-enumeration.md) que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="a3c63-107">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3c63-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a3c63-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3c63-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a3c63-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3c63-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3c63-110">Requirements</span></span>  

 <span data-ttu-id="a3c63-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3c63-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3c63-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3c63-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3c63-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3c63-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3c63-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3c63-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c63-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3c63-115">See also</span></span>

- [<span data-ttu-id="a3c63-116">Interfaz ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="a3c63-116">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="a3c63-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a3c63-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

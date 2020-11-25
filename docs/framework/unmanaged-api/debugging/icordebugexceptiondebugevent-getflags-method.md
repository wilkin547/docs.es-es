---
title: ICorDebugExceptionDebugEvent::GetFlags (método)
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 02a20b54b7fecc711bda010c6916fe036cf20dd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729608"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="d7d7b-102">ICorDebugExceptionDebugEvent::GetFlags (método)</span><span class="sxs-lookup"><span data-stu-id="d7d7b-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>

<span data-ttu-id="d7d7b-103">Obtiene una marca que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="d7d7b-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7d7b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7d7b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7d7b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d7d7b-105">Parameters</span></span>  

 `pdwFlags`  
 <span data-ttu-id="d7d7b-106">enuncia Un puntero a un valor de [cordebugexceptionflags (](cordebugexceptionflags-enumeration.md) que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="d7d7b-106">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7d7b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d7d7b-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7d7b-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d7d7b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7d7b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7d7b-109">Requirements</span></span>  

 <span data-ttu-id="d7d7b-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7d7b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7d7b-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7d7b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7d7b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7d7b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7d7b-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7d7b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d7b-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7d7b-114">See also</span></span>

- [<span data-ttu-id="d7d7b-115">Interfaz ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="d7d7b-115">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="d7d7b-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d7d7b-116">Debugging Interfaces</span></span>](debugging-interfaces.md)

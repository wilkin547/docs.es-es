---
title: Método ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 453f691f414050905f5d73e201ebeed79e2aaf50
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910204"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="2598d-102">Método ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="2598d-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="2598d-103">Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="2598d-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2598d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2598d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2598d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2598d-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="2598d-106">Puntero al número de bytes que este campo de instancia compensa en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="2598d-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2598d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2598d-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2598d-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2598d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2598d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2598d-109">Requirements</span></span>  
 <span data-ttu-id="2598d-110">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2598d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2598d-111">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="2598d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2598d-112">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2598d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2598d-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2598d-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2598d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2598d-114">See also</span></span>

- [<span data-ttu-id="2598d-115">ICorDebugInstanceFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2598d-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="2598d-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2598d-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

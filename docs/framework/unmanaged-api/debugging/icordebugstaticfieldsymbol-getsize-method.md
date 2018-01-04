---
title: "ICorDebugStaticFieldSymbol::GetSize (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b67cbe6858e91e089c36047d6ed83743e45e1d1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="edf8f-102">ICorDebugStaticFieldSymbol::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="edf8f-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="edf8f-103">Obtiene el tamaño del campo estático, en bytes.</span><span class="sxs-lookup"><span data-stu-id="edf8f-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edf8f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="edf8f-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="edf8f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="edf8f-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="edf8f-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="edf8f-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edf8f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="edf8f-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="edf8f-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="edf8f-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edf8f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="edf8f-109">Requirements</span></span>  
 <span data-ttu-id="edf8f-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edf8f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edf8f-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="edf8f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="edf8f-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edf8f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edf8f-113">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edf8f-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edf8f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="edf8f-114">See Also</span></span>  
 [<span data-ttu-id="edf8f-115">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="edf8f-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="edf8f-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="edf8f-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

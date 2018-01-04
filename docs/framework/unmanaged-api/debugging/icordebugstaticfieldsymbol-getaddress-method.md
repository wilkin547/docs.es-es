---
title: "ICorDebugStaticFieldSymbol::GetAddress (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5382a0b04a8a4d5adf9745d21b5bbcf629da1df3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="04d7e-102">ICorDebugStaticFieldSymbol::GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="04d7e-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="04d7e-103">Obtiene la dirección de un campo estático.</span><span class="sxs-lookup"><span data-stu-id="04d7e-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04d7e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04d7e-104">Syntax</span></span>  
  
```  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04d7e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04d7e-105">Parameters</span></span>  
 <span data-ttu-id="04d7e-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="04d7e-106">pRVA</span></span>  
 <span data-ttu-id="04d7e-107">[out] Puntero a la dirección virtual relativa (RVA) del campo estático.</span><span class="sxs-lookup"><span data-stu-id="04d7e-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04d7e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04d7e-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04d7e-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="04d7e-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04d7e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04d7e-110">Requirements</span></span>  
 <span data-ttu-id="04d7e-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04d7e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04d7e-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04d7e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04d7e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04d7e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04d7e-114">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04d7e-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04d7e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="04d7e-115">See Also</span></span>  
 [<span data-ttu-id="04d7e-116">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="04d7e-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="04d7e-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="04d7e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

---
title: "Método ICorDebugInstanceFieldSymbol::GetSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad13dbe8148d4d9507c6a450d2833da049e0e13a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="2c5df-102">Método ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="2c5df-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="2c5df-103">Obtiene el tamaño, en bytes, del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="2c5df-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c5df-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c5df-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c5df-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2c5df-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="2c5df-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="2c5df-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c5df-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2c5df-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c5df-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2c5df-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c5df-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c5df-109">Requirements</span></span>  
 <span data-ttu-id="2c5df-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c5df-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c5df-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c5df-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c5df-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c5df-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c5df-113">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c5df-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c5df-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c5df-114">See Also</span></span>  
 [<span data-ttu-id="2c5df-115">ICorDebugInstanceFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c5df-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="2c5df-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2c5df-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

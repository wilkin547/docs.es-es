---
title: "ICorDebugVariableSymbol::GetSize (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 99cba63edd56e0d27d5f558a77ee54ebf2629446
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="c5862-102">ICorDebugVariableSymbol::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="c5862-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="c5862-103">Obtiene el tamaño de una variable en bytes.</span><span class="sxs-lookup"><span data-stu-id="c5862-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5862-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5862-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5862-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c5862-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="c5862-106">Puntero a un entero de 32 bits sin signo que contiene el tamaño de la variable.</span><span class="sxs-lookup"><span data-stu-id="c5862-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5862-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c5862-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5862-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c5862-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5862-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5862-109">Requirements</span></span>  
 <span data-ttu-id="c5862-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5862-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5862-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5862-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5862-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5862-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5862-113">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5862-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5862-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5862-114">See Also</span></span>  
 [<span data-ttu-id="c5862-115">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c5862-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="c5862-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c5862-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

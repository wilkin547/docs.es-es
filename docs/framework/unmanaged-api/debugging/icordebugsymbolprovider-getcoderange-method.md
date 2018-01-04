---
title: "ICorDebugSymbolProvider::GetCodeRange (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0bb2729ee5bc77842f658e38a2afbbb2b24da55
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="01ac7-102">ICorDebugSymbolProvider::GetCodeRange (método)</span><span class="sxs-lookup"><span data-stu-id="01ac7-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>
<span data-ttu-id="01ac7-103">Obtiene el tamaño y la dirección de inicio del método a partir de una dirección virtual relativa (RVA) en un método.</span><span class="sxs-lookup"><span data-stu-id="01ac7-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01ac7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01ac7-104">Syntax</span></span>  
  
```  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01ac7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="01ac7-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="01ac7-106">[in] Dirección virtual relativa (RVA) en un método.</span><span class="sxs-lookup"><span data-stu-id="01ac7-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="01ac7-107">[out] Puntero a la dirección de inicio del método.</span><span class="sxs-lookup"><span data-stu-id="01ac7-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="01ac7-108">Puntero al tamaño del código del método (número de bytes del código del método).</span><span class="sxs-lookup"><span data-stu-id="01ac7-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01ac7-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="01ac7-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01ac7-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="01ac7-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01ac7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01ac7-111">Requirements</span></span>  
 <span data-ttu-id="01ac7-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01ac7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01ac7-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01ac7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01ac7-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01ac7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01ac7-115">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01ac7-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01ac7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="01ac7-116">See Also</span></span>  
 [<span data-ttu-id="01ac7-117">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="01ac7-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="01ac7-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="01ac7-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

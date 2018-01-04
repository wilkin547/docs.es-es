---
title: "ICorDebugSymbolProvider2::GetFrameProps (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f74ed8cdd7448d7ebeaa98108e84b42e86f428b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="93b3e-102">ICorDebugSymbolProvider2::GetFrameProps (método)</span><span class="sxs-lookup"><span data-stu-id="93b3e-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="93b3e-103">Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="93b3e-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93b3e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93b3e-104">Syntax</span></span>  
  
```  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93b3e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="93b3e-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="93b3e-106">[in] Dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="93b3e-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="93b3e-107">[out] Puntero a la dirección virtual relativa de inicio del método.</span><span class="sxs-lookup"><span data-stu-id="93b3e-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="93b3e-108">[out] Puntero a la dirección virtual relativa de inicio del marco.</span><span class="sxs-lookup"><span data-stu-id="93b3e-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93b3e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93b3e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93b3e-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="93b3e-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93b3e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93b3e-111">Requirements</span></span>  
 <span data-ttu-id="93b3e-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93b3e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93b3e-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93b3e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93b3e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93b3e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93b3e-115">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93b3e-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93b3e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="93b3e-116">See Also</span></span>  
 [<span data-ttu-id="93b3e-117">ICorDebugSymbolProvider2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="93b3e-117">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 [<span data-ttu-id="93b3e-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="93b3e-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

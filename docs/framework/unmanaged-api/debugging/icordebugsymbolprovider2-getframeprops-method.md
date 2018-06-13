---
title: ICorDebugSymbolProvider2::GetFrameProps (método)
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 419e7bae5998679fafac48ebfd5b0673e0e4bac5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419086"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="631fe-102">ICorDebugSymbolProvider2::GetFrameProps (método)</span><span class="sxs-lookup"><span data-stu-id="631fe-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="631fe-103">Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="631fe-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="631fe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="631fe-104">Syntax</span></span>  
  
```  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="631fe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="631fe-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="631fe-106">[in] Dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="631fe-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="631fe-107">[out] Puntero a la dirección virtual relativa de inicio del método.</span><span class="sxs-lookup"><span data-stu-id="631fe-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="631fe-108">[out] Puntero a la dirección virtual relativa de inicio del marco.</span><span class="sxs-lookup"><span data-stu-id="631fe-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="631fe-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="631fe-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="631fe-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="631fe-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="631fe-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="631fe-111">Requirements</span></span>  
 <span data-ttu-id="631fe-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="631fe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="631fe-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="631fe-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="631fe-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="631fe-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="631fe-115">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="631fe-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="631fe-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="631fe-116">See Also</span></span>  
 [<span data-ttu-id="631fe-117">ICorDebugSymbolProvider2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="631fe-117">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 [<span data-ttu-id="631fe-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="631fe-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

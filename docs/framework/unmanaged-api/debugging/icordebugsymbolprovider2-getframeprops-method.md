---
title: ICorDebugSymbolProvider2::GetFrameProps (método)
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b20d78abbfa1db43047872a596289028833de37d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098993"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="3c036-102">ICorDebugSymbolProvider2::GetFrameProps (método)</span><span class="sxs-lookup"><span data-stu-id="3c036-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="3c036-103">Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="3c036-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c036-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c036-104">Syntax</span></span>  
  
```  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c036-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c036-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="3c036-106">[in] Dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="3c036-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="3c036-107">[out] Puntero a la dirección virtual relativa de inicio del método.</span><span class="sxs-lookup"><span data-stu-id="3c036-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="3c036-108">[out] Puntero a la dirección virtual relativa de inicio del marco.</span><span class="sxs-lookup"><span data-stu-id="3c036-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c036-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c036-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c036-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3c036-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c036-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c036-111">Requirements</span></span>  
 <span data-ttu-id="3c036-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c036-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c036-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c036-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c036-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c036-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3c036-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3c036-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3c036-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c036-116">See also</span></span>

- [<span data-ttu-id="3c036-117">Interfaz ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="3c036-117">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="3c036-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="3c036-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

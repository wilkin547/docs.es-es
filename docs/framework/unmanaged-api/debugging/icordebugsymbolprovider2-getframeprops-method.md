---
title: ICorDebugSymbolProvider2::GetFrameProps (método)
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c02a2b31ecc588879b43668d56cd9978b62e49a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482488"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="6044c-102">ICorDebugSymbolProvider2::GetFrameProps (método)</span><span class="sxs-lookup"><span data-stu-id="6044c-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="6044c-103">Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="6044c-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6044c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6044c-104">Syntax</span></span>  
  
```  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6044c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6044c-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="6044c-106">[in] Dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="6044c-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="6044c-107">[out] Puntero a la dirección virtual relativa de inicio del método.</span><span class="sxs-lookup"><span data-stu-id="6044c-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="6044c-108">[out] Puntero a la dirección virtual relativa de inicio del marco.</span><span class="sxs-lookup"><span data-stu-id="6044c-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6044c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6044c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6044c-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6044c-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6044c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6044c-111">Requirements</span></span>  
 <span data-ttu-id="6044c-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6044c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6044c-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6044c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6044c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6044c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6044c-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6044c-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6044c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6044c-116">See also</span></span>
- [<span data-ttu-id="6044c-117">ICorDebugSymbolProvider2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6044c-117">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="6044c-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6044c-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

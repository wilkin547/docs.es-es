---
title: ICorDebugSymbolProvider2::GetFrameProps (método)
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 274da030bbbb7c614709b5150f08f37ddf5aaf5a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771165"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="ba39b-102">ICorDebugSymbolProvider2::GetFrameProps (método)</span><span class="sxs-lookup"><span data-stu-id="ba39b-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="ba39b-103">Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="ba39b-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba39b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba39b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba39b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ba39b-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="ba39b-106">[in] Dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="ba39b-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="ba39b-107">[out] Puntero a la dirección virtual relativa de inicio del método.</span><span class="sxs-lookup"><span data-stu-id="ba39b-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="ba39b-108">[out] Puntero a la dirección virtual relativa de inicio del marco.</span><span class="sxs-lookup"><span data-stu-id="ba39b-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba39b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba39b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba39b-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ba39b-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba39b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba39b-111">Requirements</span></span>  
 <span data-ttu-id="ba39b-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba39b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba39b-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba39b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba39b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba39b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba39b-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba39b-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba39b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba39b-116">See also</span></span>

- [<span data-ttu-id="ba39b-117">ICorDebugSymbolProvider2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba39b-117">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="ba39b-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ba39b-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

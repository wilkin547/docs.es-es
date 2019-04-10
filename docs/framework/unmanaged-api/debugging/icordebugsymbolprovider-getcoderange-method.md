---
title: ICorDebugSymbolProvider::GetCodeRange (método)
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 52fd0e9dac1d255197909d153099d9c6f2bd8ff7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212939"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="33b6f-102">ICorDebugSymbolProvider::GetCodeRange (método)</span><span class="sxs-lookup"><span data-stu-id="33b6f-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>
<span data-ttu-id="33b6f-103">Obtiene el tamaño y la dirección de inicio del método a partir de una dirección virtual relativa (RVA) en un método.</span><span class="sxs-lookup"><span data-stu-id="33b6f-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33b6f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33b6f-104">Syntax</span></span>  
  
```  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33b6f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33b6f-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="33b6f-106">[in] Dirección virtual relativa (RVA) en un método.</span><span class="sxs-lookup"><span data-stu-id="33b6f-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="33b6f-107">[out] Puntero a la dirección de inicio del método.</span><span class="sxs-lookup"><span data-stu-id="33b6f-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="33b6f-108">Puntero al tamaño del código del método (número de bytes del código del método).</span><span class="sxs-lookup"><span data-stu-id="33b6f-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33b6f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33b6f-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33b6f-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="33b6f-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33b6f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33b6f-111">Requirements</span></span>  
 <span data-ttu-id="33b6f-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33b6f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33b6f-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33b6f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33b6f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33b6f-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="33b6f-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="33b6f-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="33b6f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="33b6f-116">See also</span></span>

- [<span data-ttu-id="33b6f-117">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="33b6f-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="33b6f-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="33b6f-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

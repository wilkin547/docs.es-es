---
title: ICorDebugSymbolProvider::GetCodeRange (método)
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6d1f2bd903124773eaa20581f013bb41cf9cf99
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771490"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="51ebc-102">ICorDebugSymbolProvider::GetCodeRange (método)</span><span class="sxs-lookup"><span data-stu-id="51ebc-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>
<span data-ttu-id="51ebc-103">Obtiene el tamaño y la dirección de inicio del método a partir de una dirección virtual relativa (RVA) en un método.</span><span class="sxs-lookup"><span data-stu-id="51ebc-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51ebc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51ebc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51ebc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="51ebc-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="51ebc-106">[in] Dirección virtual relativa (RVA) en un método.</span><span class="sxs-lookup"><span data-stu-id="51ebc-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="51ebc-107">[out] Puntero a la dirección de inicio del método.</span><span class="sxs-lookup"><span data-stu-id="51ebc-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="51ebc-108">Puntero al tamaño del código del método (número de bytes del código del método).</span><span class="sxs-lookup"><span data-stu-id="51ebc-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51ebc-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="51ebc-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51ebc-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="51ebc-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51ebc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51ebc-111">Requirements</span></span>  
 <span data-ttu-id="51ebc-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51ebc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51ebc-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51ebc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51ebc-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51ebc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51ebc-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51ebc-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51ebc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="51ebc-116">See also</span></span>

- [<span data-ttu-id="51ebc-117">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="51ebc-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="51ebc-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="51ebc-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

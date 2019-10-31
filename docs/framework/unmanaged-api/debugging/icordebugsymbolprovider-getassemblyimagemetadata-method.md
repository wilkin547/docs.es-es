---
title: 'ICorDebugSymbolProvider:: Getassemblyimagemetadata ((método)'
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: fb08df3b594e0c34dfe4ca791983b0c111239b23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138913"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="391ce-102">ICorDebugSymbolProvider:: Getassemblyimagemetadata ((método)</span><span class="sxs-lookup"><span data-stu-id="391ce-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="391ce-103">Devuelve los metadatos desde un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="391ce-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="391ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="391ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="391ce-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="391ce-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="391ce-106">enuncia Puntero a la dirección de un objeto [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) que contiene información sobre el tamaño y la dirección de los metadatos del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="391ce-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="391ce-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="391ce-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="391ce-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="391ce-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="391ce-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="391ce-109">Requirements</span></span>  
 <span data-ttu-id="391ce-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="391ce-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="391ce-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="391ce-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="391ce-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="391ce-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="391ce-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="391ce-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="391ce-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="391ce-114">See also</span></span>

- [<span data-ttu-id="391ce-115">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="391ce-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="391ce-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="391ce-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

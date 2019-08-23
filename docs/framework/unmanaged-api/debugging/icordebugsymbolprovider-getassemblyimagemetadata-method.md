---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata (método)
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad86c42d0f23de25fe0e5b9123a0dba3695d8d64
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964658"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="7ec68-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata (método)</span><span class="sxs-lookup"><span data-stu-id="7ec68-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="7ec68-103">Devuelve los metadatos desde un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="7ec68-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ec68-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ec68-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ec68-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ec68-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="7ec68-106">enuncia Puntero a la dirección de un objeto [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) que contiene información sobre el tamaño y la dirección de los metadatos del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="7ec68-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ec68-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ec68-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ec68-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7ec68-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ec68-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ec68-109">Requirements</span></span>  
 <span data-ttu-id="7ec68-110">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ec68-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ec68-111">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="7ec68-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ec68-112">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ec68-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ec68-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ec68-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec68-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ec68-114">See also</span></span>

- [<span data-ttu-id="7ec68-115">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ec68-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="7ec68-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7ec68-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

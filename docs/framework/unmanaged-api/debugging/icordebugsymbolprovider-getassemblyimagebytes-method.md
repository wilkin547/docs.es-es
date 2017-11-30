---
title: "ICorDebugSymbolProvider::GetAssemblyImageBytes (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 127ebe82c32e9bf3d06c171d6cbf426d508eacaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="6db46-102">ICorDebugSymbolProvider::GetAssemblyImageBytes (método)</span><span class="sxs-lookup"><span data-stu-id="6db46-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="6db46-103">Lee datos de un ensamblado combinado a partir de una dirección virtual relativa (RVA) en el ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="6db46-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6db46-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6db46-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6db46-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6db46-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="6db46-106">[in] Dirección virtual relativa (RVA) en un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="6db46-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="6db46-107">Número de bytes para leer desde el ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="6db46-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="6db46-108">Un puntero a la dirección de un [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) objeto que contiene información sobre el búfer de memoria con los metadatos del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="6db46-108">A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6db46-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6db46-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6db46-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6db46-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6db46-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6db46-111">Requirements</span></span>  
 <span data-ttu-id="6db46-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6db46-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6db46-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6db46-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6db46-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6db46-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6db46-115">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6db46-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6db46-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6db46-116">See Also</span></span>  
 [<span data-ttu-id="6db46-117">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="6db46-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="6db46-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6db46-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

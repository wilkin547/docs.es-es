---
title: "ICorDebugSymbolProvider::GetAssemblyImageMetadata (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 48e5e9daf191cb2f4112dd2a957f29c0a7521398
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="0f8cd-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata (método)</span><span class="sxs-lookup"><span data-stu-id="0f8cd-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="0f8cd-103">Devuelve los metadatos desde un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f8cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f8cd-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f8cd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f8cd-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="0f8cd-106">[out] Un puntero a la dirección de un [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) objeto que contiene información sobre el tamaño y la dirección de metadatos del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f8cd-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0f8cd-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f8cd-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f8cd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f8cd-109">Requirements</span></span>  
 <span data-ttu-id="0f8cd-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f8cd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f8cd-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f8cd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f8cd-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f8cd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f8cd-113">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f8cd-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f8cd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f8cd-114">See Also</span></span>  
 [<span data-ttu-id="0f8cd-115">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="0f8cd-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="0f8cd-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0f8cd-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

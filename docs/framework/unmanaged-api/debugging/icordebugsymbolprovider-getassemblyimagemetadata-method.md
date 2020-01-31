---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata (método)
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: 3ee80c18d3091406bf0bbd5b22c5f6021888906d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791658"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="4d6ad-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata (método)</span><span class="sxs-lookup"><span data-stu-id="4d6ad-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="4d6ad-103">Devuelve los metadatos desde un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="4d6ad-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d6ad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d6ad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d6ad-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4d6ad-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="4d6ad-106">enuncia Puntero a la dirección de un objeto [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) que contiene información sobre el tamaño y la dirección de los metadatos del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="4d6ad-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d6ad-107">Notas</span><span class="sxs-lookup"><span data-stu-id="4d6ad-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4d6ad-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4d6ad-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d6ad-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4d6ad-109">Requirements</span></span>  
 <span data-ttu-id="4d6ad-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d6ad-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d6ad-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d6ad-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d6ad-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d6ad-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d6ad-113">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d6ad-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d6ad-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d6ad-114">See also</span></span>

- [<span data-ttu-id="4d6ad-115">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d6ad-115">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="4d6ad-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4d6ad-116">Debugging Interfaces</span></span>](debugging-interfaces.md)

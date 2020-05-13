---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata (método)
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: d118f0c984663e0844783ff52859698dd5335058
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83376148"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="5f2e3-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata (método)</span><span class="sxs-lookup"><span data-stu-id="5f2e3-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="5f2e3-103">Devuelve los metadatos desde un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="5f2e3-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f2e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f2e3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f2e3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f2e3-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="5f2e3-106">enuncia Puntero a la dirección de un objeto [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) que contiene información sobre el tamaño y la dirección de los metadatos del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="5f2e3-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f2e3-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5f2e3-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f2e3-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5f2e3-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f2e3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f2e3-109">Requirements</span></span>  
 <span data-ttu-id="5f2e3-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f2e3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f2e3-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f2e3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f2e3-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f2e3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f2e3-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f2e3-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f2e3-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f2e3-114">See also</span></span>

- [<span data-ttu-id="5f2e3-115">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="5f2e3-115">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="5f2e3-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5f2e3-116">Debugging Interfaces</span></span>](debugging-interfaces.md)

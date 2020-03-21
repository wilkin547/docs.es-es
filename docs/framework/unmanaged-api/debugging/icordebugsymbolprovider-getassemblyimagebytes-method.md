---
title: ICorDebugSymbolProvider::GetAssemblyImageBytes (método)
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: 6361b12802876ef480acbe1cc13f32b77ba0be49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178489"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="8f28d-102">ICorDebugSymbolProvider::GetAssemblyImageBytes (método)</span><span class="sxs-lookup"><span data-stu-id="8f28d-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="8f28d-103">Lee datos de un ensamblado combinado a partir de una dirección virtual relativa (RVA) del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="8f28d-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f28d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f28d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,
   [in] ULONG32 length,
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f28d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f28d-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="8f28d-106">[in] Dirección virtual relativa (RVA) en un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="8f28d-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="8f28d-107">Número de bytes para leer desde el ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="8f28d-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="8f28d-108">Puntero a la dirección de un [Objeto ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) que contiene información sobre el búfer de memoria con metadatos de ensamblado combinados.</span><span class="sxs-lookup"><span data-stu-id="8f28d-108">A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f28d-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8f28d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f28d-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8f28d-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f28d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f28d-111">Requirements</span></span>  
 <span data-ttu-id="8f28d-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f28d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f28d-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f28d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f28d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f28d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f28d-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f28d-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f28d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8f28d-116">See also</span></span>

- [<span data-ttu-id="8f28d-117">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="8f28d-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="8f28d-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8f28d-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

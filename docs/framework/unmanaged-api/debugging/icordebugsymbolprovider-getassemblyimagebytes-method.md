---
title: ICorDebugSymbolProvider::GetAssemblyImageBytes (método)
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: b52614065d599edf8e556524c33e8bc50b4924ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709185"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="dec51-102">ICorDebugSymbolProvider::GetAssemblyImageBytes (método)</span><span class="sxs-lookup"><span data-stu-id="dec51-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>

<span data-ttu-id="dec51-103">Lee datos de un ensamblado combinado a partir de una dirección virtual relativa (RVA) del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="dec51-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dec51-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dec51-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,
   [in] ULONG32 length,
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dec51-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dec51-105">Parameters</span></span>  

 `rva`  
 <span data-ttu-id="dec51-106">[in] Dirección virtual relativa (RVA) en un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="dec51-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="dec51-107">Número de bytes para leer desde el ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="dec51-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="dec51-108">Puntero a la dirección de un objeto [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) que contiene información sobre el búfer de memoria con metadatos de ensamblado combinados.</span><span class="sxs-lookup"><span data-stu-id="dec51-108">A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dec51-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dec51-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dec51-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="dec51-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dec51-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dec51-111">Requirements</span></span>  

 <span data-ttu-id="dec51-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dec51-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dec51-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dec51-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dec51-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dec51-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dec51-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dec51-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dec51-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dec51-116">See also</span></span>

- [<span data-ttu-id="dec51-117">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="dec51-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="dec51-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="dec51-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

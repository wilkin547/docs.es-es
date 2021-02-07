---
description: 'Más información sobre: ICorDebugSymbolProvider:: Getassemblyimagebytes ((método)'
title: ICorDebugSymbolProvider::GetAssemblyImageBytes (método)
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: 2e08b23e35913e8767135d75d28ff66efc890565
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717282"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="86abe-103">ICorDebugSymbolProvider::GetAssemblyImageBytes (método)</span><span class="sxs-lookup"><span data-stu-id="86abe-103">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>

<span data-ttu-id="86abe-104">Lee datos de un ensamblado combinado a partir de una dirección virtual relativa (RVA) del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="86abe-104">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86abe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86abe-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,
   [in] ULONG32 length,
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86abe-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86abe-106">Parameters</span></span>  

 `rva`  
 <span data-ttu-id="86abe-107">[in] Dirección virtual relativa (RVA) en un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="86abe-107">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="86abe-108">Número de bytes para leer desde el ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="86abe-108">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="86abe-109">Puntero a la dirección de un objeto [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) que contiene información sobre el búfer de memoria con metadatos de ensamblado combinados.</span><span class="sxs-lookup"><span data-stu-id="86abe-109">A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86abe-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="86abe-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86abe-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="86abe-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86abe-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86abe-112">Requirements</span></span>  

 <span data-ttu-id="86abe-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86abe-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86abe-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86abe-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86abe-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86abe-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86abe-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86abe-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86abe-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="86abe-117">See also</span></span>

- [<span data-ttu-id="86abe-118">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="86abe-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="86abe-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="86abe-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

---
title: ICorDebugSymbolProvider::GetAssemblyImageBytes (método)
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 103e724c37ae356729dd5bba3ff66c0f443f6eaa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61953535"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="6ff1d-102">ICorDebugSymbolProvider::GetAssemblyImageBytes (método)</span><span class="sxs-lookup"><span data-stu-id="6ff1d-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="6ff1d-103">Lee datos de un ensamblado combinado a partir de una dirección virtual relativa (RVA) del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="6ff1d-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ff1d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ff1d-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ff1d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6ff1d-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="6ff1d-106">[in] Dirección virtual relativa (RVA) en un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="6ff1d-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="6ff1d-107">Número de bytes para leer desde el ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="6ff1d-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="6ff1d-108">Un puntero a la dirección de un [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) objeto que contiene información sobre el búfer de memoria con los metadatos del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="6ff1d-108">A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ff1d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6ff1d-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ff1d-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6ff1d-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ff1d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ff1d-111">Requirements</span></span>  
 <span data-ttu-id="6ff1d-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ff1d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ff1d-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ff1d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ff1d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ff1d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ff1d-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ff1d-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ff1d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ff1d-116">See also</span></span>

- [<span data-ttu-id="6ff1d-117">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ff1d-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="6ff1d-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6ff1d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

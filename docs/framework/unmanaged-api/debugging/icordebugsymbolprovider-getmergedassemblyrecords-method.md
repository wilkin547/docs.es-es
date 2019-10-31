---
title: 'ICorDebugSymbolProvider:: Getmergedassemblyrecords ((método)'
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: 6faf8960c06488c8fff5a076aae375529e1d0260
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138876"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="4190e-102">ICorDebugSymbolProvider:: Getmergedassemblyrecords ((método)</span><span class="sxs-lookup"><span data-stu-id="4190e-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="4190e-103">Obtiene los registros de símbolos para todos los ensamblados combinados.</span><span class="sxs-lookup"><span data-stu-id="4190e-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4190e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4190e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4190e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4190e-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="4190e-106">[in] Número de registros de símbolos solicitado.</span><span class="sxs-lookup"><span data-stu-id="4190e-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="4190e-107">[out] Puntero al número de registros de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="4190e-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="4190e-108">Puntero a una matriz de objetos [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4190e-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4190e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4190e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4190e-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4190e-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4190e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4190e-111">Requirements</span></span>  
 <span data-ttu-id="4190e-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4190e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4190e-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4190e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4190e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4190e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4190e-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4190e-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4190e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4190e-116">See also</span></span>

- [<span data-ttu-id="4190e-117">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4190e-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="4190e-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4190e-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

---
title: ICorDebugSymbolProvider::GetMergedAssemblyRecords (método)
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: 10bbcf2e6a536eeb4ab8141c10c177a53faa1c95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730882"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="a0075-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords (método)</span><span class="sxs-lookup"><span data-stu-id="a0075-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>

<span data-ttu-id="a0075-103">Obtiene los registros de símbolos para todos los ensamblados combinados.</span><span class="sxs-lookup"><span data-stu-id="a0075-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0075-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0075-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0075-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a0075-105">Parameters</span></span>  

 `cRequestedRecords`  
 <span data-ttu-id="a0075-106">[in] Número de registros de símbolos solicitado.</span><span class="sxs-lookup"><span data-stu-id="a0075-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="a0075-107">[out] Puntero al número de registros de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="a0075-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="a0075-108">Puntero a una matriz de objetos [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a0075-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0075-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0075-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0075-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a0075-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0075-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0075-111">Requirements</span></span>  

 <span data-ttu-id="a0075-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0075-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0075-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0075-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0075-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0075-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0075-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0075-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0075-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0075-116">See also</span></span>

- [<span data-ttu-id="a0075-117">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="a0075-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="a0075-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a0075-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

---
title: ICorDebugSymbolProvider::GetMergedAssemblyRecords (método)
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: b7d26fa80a7a8ebe7b4606b914c8cd09c52df1e4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379619"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="d7d04-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords (método)</span><span class="sxs-lookup"><span data-stu-id="d7d04-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="d7d04-103">Obtiene los registros de símbolos para todos los ensamblados combinados.</span><span class="sxs-lookup"><span data-stu-id="d7d04-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7d04-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7d04-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7d04-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d7d04-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="d7d04-106">[in] Número de registros de símbolos solicitado.</span><span class="sxs-lookup"><span data-stu-id="d7d04-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="d7d04-107">[out] Puntero al número de registros de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="d7d04-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="d7d04-108">Puntero a una matriz de objetos [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d7d04-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7d04-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d7d04-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7d04-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d7d04-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7d04-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7d04-111">Requirements</span></span>  
 <span data-ttu-id="d7d04-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7d04-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7d04-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7d04-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7d04-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7d04-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7d04-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7d04-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d04-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7d04-116">See also</span></span>

- [<span data-ttu-id="d7d04-117">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="d7d04-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="d7d04-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d7d04-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

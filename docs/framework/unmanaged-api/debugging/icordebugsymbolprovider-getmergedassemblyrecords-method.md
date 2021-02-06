---
description: 'Más información sobre: ICorDebugSymbolProvider:: Getmergedassemblyrecords ((método)'
title: ICorDebugSymbolProvider::GetMergedAssemblyRecords (método)
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: f12bb3a49d7b49f9f8916c9d04417340502d44ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659886"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="5414d-103">ICorDebugSymbolProvider::GetMergedAssemblyRecords (método)</span><span class="sxs-lookup"><span data-stu-id="5414d-103">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>

<span data-ttu-id="5414d-104">Obtiene los registros de símbolos para todos los ensamblados combinados.</span><span class="sxs-lookup"><span data-stu-id="5414d-104">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5414d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5414d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5414d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5414d-106">Parameters</span></span>  

 `cRequestedRecords`  
 <span data-ttu-id="5414d-107">[in] Número de registros de símbolos solicitado.</span><span class="sxs-lookup"><span data-stu-id="5414d-107">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="5414d-108">[out] Puntero al número de registros de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="5414d-108">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="5414d-109">Puntero a una matriz de objetos [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5414d-109">A pointer to an array of [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5414d-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5414d-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5414d-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5414d-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5414d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5414d-112">Requirements</span></span>  

 <span data-ttu-id="5414d-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5414d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5414d-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5414d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5414d-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5414d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5414d-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5414d-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5414d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5414d-117">See also</span></span>

- [<span data-ttu-id="5414d-118">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="5414d-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="5414d-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5414d-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

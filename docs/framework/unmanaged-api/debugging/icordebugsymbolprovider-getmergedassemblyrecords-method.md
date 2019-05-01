---
title: ICorDebugSymbolProvider::GetMergedAssemblyRecords (método)
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9003482860e554049c39ea9ffed4c52345bfeff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61953314"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="6a91d-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords (método)</span><span class="sxs-lookup"><span data-stu-id="6a91d-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="6a91d-103">Obtiene los registros de símbolos para todos los ensamblados combinados.</span><span class="sxs-lookup"><span data-stu-id="6a91d-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a91d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a91d-104">Syntax</span></span>  
  
```  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a91d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6a91d-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="6a91d-106">[in] Número de registros de símbolos solicitado.</span><span class="sxs-lookup"><span data-stu-id="6a91d-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="6a91d-107">[out] Puntero al número de registros de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="6a91d-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="6a91d-108">Un puntero a una matriz de [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) objetos.</span><span class="sxs-lookup"><span data-stu-id="6a91d-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a91d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6a91d-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a91d-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6a91d-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a91d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a91d-111">Requirements</span></span>  
 <span data-ttu-id="6a91d-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a91d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a91d-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a91d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a91d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a91d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a91d-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a91d-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a91d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a91d-116">See also</span></span>

- [<span data-ttu-id="6a91d-117">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a91d-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="6a91d-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6a91d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

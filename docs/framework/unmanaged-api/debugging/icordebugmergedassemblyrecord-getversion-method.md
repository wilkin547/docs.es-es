---
title: ICorDebugMergedAssemblyRecord::GetVersion (método)
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36cf8647b3caafeaae2db3c2fd53471496e922fa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109544"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="c4324-102">ICorDebugMergedAssemblyRecord::GetVersion (método)</span><span class="sxs-lookup"><span data-stu-id="c4324-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="c4324-103">Obtiene información de la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c4324-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4324-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4324-104">Syntax</span></span>  
  
```  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4324-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c4324-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="c4324-106">[out] Puntero al número de revisión principal.</span><span class="sxs-lookup"><span data-stu-id="c4324-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="c4324-107">[out] Puntero al número de revisión secundaria.</span><span class="sxs-lookup"><span data-stu-id="c4324-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="c4324-108">[out] Puntero al número de revisión de compilación.</span><span class="sxs-lookup"><span data-stu-id="c4324-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="c4324-109">[out] Puntero al número de revisión.</span><span class="sxs-lookup"><span data-stu-id="c4324-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4324-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c4324-110">Remarks</span></span>  
 <span data-ttu-id="c4324-111">Para obtener información sobre los números de versión del ensamblado, consulte el tema de la clase <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="c4324-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4324-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c4324-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4324-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4324-113">Requirements</span></span>  
 <span data-ttu-id="c4324-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4324-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4324-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4324-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4324-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4324-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4324-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4324-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4324-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4324-118">See also</span></span>

- [<span data-ttu-id="c4324-119">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4324-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="c4324-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c4324-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

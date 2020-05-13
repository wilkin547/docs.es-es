---
title: ICorDebugMergedAssemblyRecord::GetVersion (método)
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: cad71080c86e92beb318722db86011b09ce02e91
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207623"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="2a032-102">ICorDebugMergedAssemblyRecord::GetVersion (método)</span><span class="sxs-lookup"><span data-stu-id="2a032-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="2a032-103">Obtiene información de la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2a032-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a032-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a032-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,
   [out] USHORT *pMinor,
   [out] USHORT *pBuild,
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a032-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a032-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="2a032-106">[out] Puntero al número de revisión principal.</span><span class="sxs-lookup"><span data-stu-id="2a032-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="2a032-107">[out] Puntero al número de revisión secundaria.</span><span class="sxs-lookup"><span data-stu-id="2a032-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="2a032-108">[out] Puntero al número de revisión de compilación.</span><span class="sxs-lookup"><span data-stu-id="2a032-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="2a032-109">[out] Puntero al número de revisión.</span><span class="sxs-lookup"><span data-stu-id="2a032-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a032-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2a032-110">Remarks</span></span>  
 <span data-ttu-id="2a032-111">Para obtener información sobre los números de versión del ensamblado, consulte el tema de la clase <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="2a032-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a032-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2a032-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a032-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a032-113">Requirements</span></span>  
 <span data-ttu-id="2a032-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a032-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a032-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a032-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a032-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a032-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a032-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a032-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a032-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2a032-118">See also</span></span>

- [<span data-ttu-id="2a032-119">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="2a032-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="2a032-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2a032-120">Debugging Interfaces</span></span>](debugging-interfaces.md)

---
title: ICorDebugMergedAssemblyRecord::GetVersion (método)
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: 8b5995183be7f1c992cf3230e16456cb248eff0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793079"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="b4543-102">ICorDebugMergedAssemblyRecord::GetVersion (método)</span><span class="sxs-lookup"><span data-stu-id="b4543-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="b4543-103">Obtiene información de la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b4543-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4543-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4543-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4543-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b4543-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="b4543-106">[out] Puntero al número de revisión principal.</span><span class="sxs-lookup"><span data-stu-id="b4543-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="b4543-107">[out] Puntero al número de revisión secundaria.</span><span class="sxs-lookup"><span data-stu-id="b4543-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="b4543-108">[out] Puntero al número de revisión de compilación.</span><span class="sxs-lookup"><span data-stu-id="b4543-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="b4543-109">[out] Puntero al número de revisión.</span><span class="sxs-lookup"><span data-stu-id="b4543-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4543-110">Notas</span><span class="sxs-lookup"><span data-stu-id="b4543-110">Remarks</span></span>  
 <span data-ttu-id="b4543-111">Para obtener información sobre los números de versión del ensamblado, consulte el tema de la clase <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="b4543-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b4543-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b4543-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4543-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="b4543-113">Requirements</span></span>  
 <span data-ttu-id="b4543-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4543-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4543-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4543-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4543-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4543-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4543-117">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4543-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4543-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4543-118">See also</span></span>

- [<span data-ttu-id="b4543-119">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4543-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="b4543-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b4543-120">Debugging Interfaces</span></span>](debugging-interfaces.md)

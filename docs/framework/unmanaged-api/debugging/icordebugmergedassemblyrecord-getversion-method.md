---
title: 'ICorDebugMergedAssemblyRecord:: GetVersion (método)'
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: 0c89d0749281da412bbf71400d51bee1ed651fbe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129770"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="aee72-102">ICorDebugMergedAssemblyRecord:: GetVersion (método)</span><span class="sxs-lookup"><span data-stu-id="aee72-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="aee72-103">Obtiene información de la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="aee72-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aee72-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aee72-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aee72-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aee72-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="aee72-106">[out] Puntero al número de revisión principal.</span><span class="sxs-lookup"><span data-stu-id="aee72-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="aee72-107">[out] Puntero al número de revisión secundaria.</span><span class="sxs-lookup"><span data-stu-id="aee72-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="aee72-108">[out] Puntero al número de revisión de compilación.</span><span class="sxs-lookup"><span data-stu-id="aee72-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="aee72-109">[out] Puntero al número de revisión.</span><span class="sxs-lookup"><span data-stu-id="aee72-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aee72-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aee72-110">Remarks</span></span>  
 <span data-ttu-id="aee72-111">Para obtener información sobre los números de versión del ensamblado, consulte el tema de la clase <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="aee72-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aee72-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="aee72-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aee72-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aee72-113">Requirements</span></span>  
 <span data-ttu-id="aee72-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aee72-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aee72-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aee72-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aee72-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aee72-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aee72-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aee72-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aee72-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="aee72-118">See also</span></span>

- [<span data-ttu-id="aee72-119">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aee72-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="aee72-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="aee72-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

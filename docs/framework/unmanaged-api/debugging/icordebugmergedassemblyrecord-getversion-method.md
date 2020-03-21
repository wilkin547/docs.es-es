---
title: ICorDebugMergedAssemblyRecord::GetVersion (método)
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: 5dc9995e88086da854d2e9382cef81b229ff9dc9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178684"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="bc496-102">ICorDebugMergedAssemblyRecord::GetVersion (método)</span><span class="sxs-lookup"><span data-stu-id="bc496-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="bc496-103">Obtiene información de la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bc496-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc496-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc496-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,
   [out] USHORT *pMinor,
   [out] USHORT *pBuild,
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc496-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc496-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="bc496-106">[out] Puntero al número de revisión principal.</span><span class="sxs-lookup"><span data-stu-id="bc496-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="bc496-107">[out] Puntero al número de revisión secundaria.</span><span class="sxs-lookup"><span data-stu-id="bc496-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="bc496-108">[out] Puntero al número de revisión de compilación.</span><span class="sxs-lookup"><span data-stu-id="bc496-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="bc496-109">[out] Puntero al número de revisión.</span><span class="sxs-lookup"><span data-stu-id="bc496-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc496-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bc496-110">Remarks</span></span>  
 <span data-ttu-id="bc496-111">Para obtener información sobre los números de versión del ensamblado, consulte el tema de la clase <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="bc496-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bc496-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bc496-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc496-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc496-113">Requirements</span></span>  
 <span data-ttu-id="bc496-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc496-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc496-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc496-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc496-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc496-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc496-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc496-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc496-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc496-118">See also</span></span>

- [<span data-ttu-id="bc496-119">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="bc496-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="bc496-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="bc496-120">Debugging Interfaces</span></span>](debugging-interfaces.md)

---
description: 'Más información sobre: ICorDebugMergedAssemblyRecord:: GetVersion (método)'
title: ICorDebugMergedAssemblyRecord::GetVersion (método)
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: 0e87e2bbb1207ebd1eb5775b7f52d5689b4e8727
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650344"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="9d61d-103">ICorDebugMergedAssemblyRecord::GetVersion (método)</span><span class="sxs-lookup"><span data-stu-id="9d61d-103">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>

<span data-ttu-id="9d61d-104">Obtiene información de la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9d61d-104">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d61d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d61d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,
   [out] USHORT *pMinor,
   [out] USHORT *pBuild,
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d61d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9d61d-106">Parameters</span></span>  

 `pMajor`  
 <span data-ttu-id="9d61d-107">[out] Puntero al número de revisión principal.</span><span class="sxs-lookup"><span data-stu-id="9d61d-107">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="9d61d-108">[out] Puntero al número de revisión secundaria.</span><span class="sxs-lookup"><span data-stu-id="9d61d-108">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="9d61d-109">[out] Puntero al número de revisión de compilación.</span><span class="sxs-lookup"><span data-stu-id="9d61d-109">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="9d61d-110">[out] Puntero al número de revisión.</span><span class="sxs-lookup"><span data-stu-id="9d61d-110">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d61d-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9d61d-111">Remarks</span></span>  

 <span data-ttu-id="9d61d-112">Para obtener información sobre los números de versión del ensamblado, consulte el tema de la clase <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="9d61d-112">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d61d-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9d61d-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d61d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d61d-114">Requirements</span></span>  

 <span data-ttu-id="9d61d-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d61d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d61d-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d61d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d61d-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d61d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d61d-118">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d61d-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d61d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d61d-119">See also</span></span>

- [<span data-ttu-id="9d61d-120">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="9d61d-120">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="9d61d-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="9d61d-121">Debugging Interfaces</span></span>](debugging-interfaces.md)

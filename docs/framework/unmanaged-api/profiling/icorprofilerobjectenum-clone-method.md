---
title: ICorProfilerObjectEnum::Clone (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 14e8086532eff5dba6883575cc2daf447a32343a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182369"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="091a7-102">ICorProfilerObjectEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="091a7-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="091a7-103">Obtiene un puntero de interfaz a una copia de este [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="091a7-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="091a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="091a7-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="091a7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="091a7-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="091a7-106">[out] Un puntero al puntero de interfaz que a su vez señala a la copia de este `ICorProfilerObjectEnum` interfaz.</span><span class="sxs-lookup"><span data-stu-id="091a7-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="091a7-107">La copia mantiene su propio estado de enumeración por separado de ésta.</span><span class="sxs-lookup"><span data-stu-id="091a7-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="091a7-108">Sin embargo, posición inicial del cursor de la copia será igual que la posición del cursor actual de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="091a7-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="091a7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="091a7-109">Requirements</span></span>  
 <span data-ttu-id="091a7-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="091a7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="091a7-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="091a7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="091a7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="091a7-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="091a7-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="091a7-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="091a7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="091a7-114">See also</span></span>

- [<span data-ttu-id="091a7-115">ICorProfilerObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="091a7-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)

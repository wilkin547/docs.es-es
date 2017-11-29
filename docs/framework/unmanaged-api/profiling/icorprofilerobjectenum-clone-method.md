---
title: "ICorProfilerObjectEnum::Clone (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum.Clone
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e077115863ab3371570463d0bfd9244b69888f9e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="39a16-102">ICorProfilerObjectEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="39a16-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="39a16-103">Obtiene un puntero de interfaz a una copia de este [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="39a16-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39a16-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39a16-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39a16-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39a16-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="39a16-106">[out] Un puntero al puntero de interfaz que a su vez señala a la copia de este `ICorProfilerObjectEnum` interfaz.</span><span class="sxs-lookup"><span data-stu-id="39a16-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="39a16-107">La copia mantiene su propio estado de enumeración independientemente de éste.</span><span class="sxs-lookup"><span data-stu-id="39a16-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="39a16-108">Sin embargo, posición inicial del cursor de la copia será igual que la posición del cursor actual de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="39a16-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39a16-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39a16-109">Requirements</span></span>  
 <span data-ttu-id="39a16-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39a16-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39a16-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="39a16-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="39a16-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39a16-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39a16-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39a16-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a16-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="39a16-114">See Also</span></span>  
 [<span data-ttu-id="39a16-115">ICorProfilerObjectEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="39a16-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)

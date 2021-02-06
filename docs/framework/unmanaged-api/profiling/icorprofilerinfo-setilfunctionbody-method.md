---
description: 'Más información acerca de: ICorProfilerInfo:: SetILFunctionBody ((método)'
title: ICorProfilerInfo::SetILFunctionBody (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
ms.openlocfilehash: 38e7907080065dc96d72a3d38a67227414637a70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647172"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="169eb-103">ICorProfilerInfo::SetILFunctionBody (Método)</span><span class="sxs-lookup"><span data-stu-id="169eb-103">ICorProfilerInfo::SetILFunctionBody Method</span></span>

<span data-ttu-id="169eb-104">Reemplaza el cuerpo de la función especificada en el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="169eb-104">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="169eb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="169eb-105">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="169eb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="169eb-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="169eb-107">de IDENTIFICADOR del módulo en el que reside la función.</span><span class="sxs-lookup"><span data-stu-id="169eb-107">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="169eb-108">de Token de la función para la que se va a reemplazar el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="169eb-108">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="169eb-109">de Nuevo encabezado de la función.</span><span class="sxs-lookup"><span data-stu-id="169eb-109">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="169eb-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="169eb-110">Remarks</span></span>  

 <span data-ttu-id="169eb-111">El `SetILFunctionBody` método reemplaza la dirección virtual relativa de la función en los metadatos para que apunte al nuevo cuerpo de la función y ajusta las estructuras de datos internas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="169eb-111">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="169eb-112">`SetILFunctionBody`Solo se puede llamar al método en aquellas funciones que nunca ha compilado un compilador Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="169eb-112">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="169eb-113">Use el método [ICorProfilerInfo:: getilfunctionbodyallocator (](icorprofilerinfo-getilfunctionbodyallocator-method.md) para asignar espacio para el nuevo método con el fin de asegurarse de que el búfer sea compatible.</span><span class="sxs-lookup"><span data-stu-id="169eb-113">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="169eb-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="169eb-114">Requirements</span></span>  

 <span data-ttu-id="169eb-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="169eb-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="169eb-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="169eb-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="169eb-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="169eb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="169eb-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="169eb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="169eb-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="169eb-119">See also</span></span>

- [<span data-ttu-id="169eb-120">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="169eb-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

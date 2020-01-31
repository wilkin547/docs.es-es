---
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
ms.openlocfilehash: 296c3973403a5b09332efa24961d7a474d814aab
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863353"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="bdf05-102">ICorProfilerInfo::SetILFunctionBody (Método)</span><span class="sxs-lookup"><span data-stu-id="bdf05-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="bdf05-103">Reemplaza el cuerpo de la función especificada en el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="bdf05-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdf05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bdf05-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdf05-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="bdf05-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="bdf05-106">de IDENTIFICADOR del módulo en el que reside la función.</span><span class="sxs-lookup"><span data-stu-id="bdf05-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="bdf05-107">de Token de la función para la que se va a reemplazar el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="bdf05-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="bdf05-108">de Nuevo encabezado de la función.</span><span class="sxs-lookup"><span data-stu-id="bdf05-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdf05-109">Notas</span><span class="sxs-lookup"><span data-stu-id="bdf05-109">Remarks</span></span>  
 <span data-ttu-id="bdf05-110">El método `SetILFunctionBody` reemplaza la dirección virtual relativa de la función en los metadatos para que apunte al nuevo cuerpo de la función y ajusta las estructuras de datos internas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="bdf05-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="bdf05-111">Solo se puede llamar al método `SetILFunctionBody` en aquellas funciones que nunca ha compilado un compilador Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="bdf05-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="bdf05-112">Use el método [ICorProfilerInfo:: getilfunctionbodyallocator (](icorprofilerinfo-getilfunctionbodyallocator-method.md) para asignar espacio para el nuevo método con el fin de asegurarse de que el búfer sea compatible.</span><span class="sxs-lookup"><span data-stu-id="bdf05-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdf05-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="bdf05-113">Requirements</span></span>  
 <span data-ttu-id="bdf05-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdf05-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdf05-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bdf05-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bdf05-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdf05-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdf05-117">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdf05-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf05-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdf05-118">See also</span></span>

- [<span data-ttu-id="bdf05-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bdf05-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

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
ms.openlocfilehash: da81bd3e255898543c94d4ac64c6afbf39b6bdba
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449876"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="19528-102">ICorProfilerInfo::SetILFunctionBody (Método)</span><span class="sxs-lookup"><span data-stu-id="19528-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="19528-103">Reemplaza el cuerpo de la función especificada en el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="19528-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19528-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19528-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19528-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19528-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="19528-106">de IDENTIFICADOR del módulo en el que reside la función.</span><span class="sxs-lookup"><span data-stu-id="19528-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="19528-107">de Token de la función para la que se va a reemplazar el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="19528-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="19528-108">de Nuevo encabezado de la función.</span><span class="sxs-lookup"><span data-stu-id="19528-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19528-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="19528-109">Remarks</span></span>  
 <span data-ttu-id="19528-110">El método `SetILFunctionBody` reemplaza la dirección virtual relativa de la función en los metadatos para que apunte al nuevo cuerpo de la función y ajusta las estructuras de datos internas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="19528-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="19528-111">Solo se puede llamar al método `SetILFunctionBody` en aquellas funciones que nunca ha compilado un compilador Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="19528-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="19528-112">Use el método [ICorProfilerInfo:: getilfunctionbodyallocator (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) para asignar espacio para el nuevo método con el fin de asegurarse de que el búfer sea compatible.</span><span class="sxs-lookup"><span data-stu-id="19528-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19528-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19528-113">Requirements</span></span>  
 <span data-ttu-id="19528-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19528-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19528-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="19528-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="19528-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19528-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19528-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19528-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19528-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="19528-118">See also</span></span>

- [<span data-ttu-id="19528-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="19528-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

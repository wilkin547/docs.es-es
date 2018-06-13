---
title: ICorProfilerInfo::GetILFunctionBodyAllocator (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 00a3afab4d5f6151bcd0efd2b658d4cd7fa8f1e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462207"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="ea3b6-102">ICorProfilerInfo::GetILFunctionBodyAllocator (Método)</span><span class="sxs-lookup"><span data-stu-id="ea3b6-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>
<span data-ttu-id="ea3b6-103">Obtiene una interfaz que proporciona un método para asignar memoria que se usará para intercambiar el cuerpo de un método en el código de lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ea3b6-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea3b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea3b6-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea3b6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea3b6-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ea3b6-106">[in] El identificador del módulo en el que reside el método.</span><span class="sxs-lookup"><span data-stu-id="ea3b6-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="ea3b6-107">[out] Un puntero a un [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interfaz que proporciona un método para asignar la memoria.</span><span class="sxs-lookup"><span data-stu-id="ea3b6-107">[out] A pointer to an [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea3b6-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ea3b6-108">Remarks</span></span>  
 <span data-ttu-id="ea3b6-109">Un cuerpo de método en el código MSIL debe estar ubicado como una dirección virtual relativa (RVA) en relación con el módulo cargado, lo que significa que sigue el módulo dentro de 4 GB.</span><span class="sxs-lookup"><span data-stu-id="ea3b6-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="ea3b6-110">Para que sea más fácil para una herramienta para intercambiar el cuerpo de un método, el `GetILFunctionBodyAllocator` método garantiza que la memoria se asigna dentro de ese intervalo.</span><span class="sxs-lookup"><span data-stu-id="ea3b6-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea3b6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea3b6-111">Requirements</span></span>  
 <span data-ttu-id="ea3b6-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea3b6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea3b6-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ea3b6-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ea3b6-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea3b6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea3b6-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea3b6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea3b6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea3b6-116">See Also</span></span>  
 [<span data-ttu-id="ea3b6-117">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea3b6-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

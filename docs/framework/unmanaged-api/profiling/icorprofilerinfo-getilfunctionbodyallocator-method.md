---
description: 'Más información acerca de: ICorProfilerInfo:: Getilfunctionbodyallocator ((método)'
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
ms.openlocfilehash: 25d059d784fe64231d4d2ff3d23b4820443873cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647432"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="951a0-103">ICorProfilerInfo::GetILFunctionBodyAllocator (Método)</span><span class="sxs-lookup"><span data-stu-id="951a0-103">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>

<span data-ttu-id="951a0-104">Obtiene una interfaz que proporciona un método para asignar la memoria que se va a usar para intercambiar el cuerpo de un método en el código del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="951a0-104">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="951a0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="951a0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="951a0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="951a0-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="951a0-107">de IDENTIFICADOR del módulo en el que reside el método.</span><span class="sxs-lookup"><span data-stu-id="951a0-107">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="951a0-108">enuncia Puntero a una interfaz [IMethodMalloc](imethodmalloc-interface.md) que proporciona un método para asignar la memoria.</span><span class="sxs-lookup"><span data-stu-id="951a0-108">[out] A pointer to an [IMethodMalloc](imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="951a0-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="951a0-109">Remarks</span></span>  

 <span data-ttu-id="951a0-110">Un cuerpo de método en código MSIL debe estar ubicado como una dirección virtual relativa (RVA), relativa al módulo cargado, lo que significa que sigue el módulo en un plazo de 4 GB.</span><span class="sxs-lookup"><span data-stu-id="951a0-110">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="951a0-111">Para facilitar a una herramienta el intercambio del cuerpo de un método, el `GetILFunctionBodyAllocator` método garantiza que la memoria se asigna dentro de ese intervalo.</span><span class="sxs-lookup"><span data-stu-id="951a0-111">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="951a0-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="951a0-112">Requirements</span></span>  

 <span data-ttu-id="951a0-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="951a0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="951a0-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="951a0-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="951a0-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="951a0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="951a0-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="951a0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="951a0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="951a0-117">See also</span></span>

- [<span data-ttu-id="951a0-118">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="951a0-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

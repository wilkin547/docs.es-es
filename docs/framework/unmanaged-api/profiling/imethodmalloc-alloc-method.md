---
title: IMethodMalloc::Alloc (Método)
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66bd56a332dc34fd35f3129256cc0e3d6c5d4508
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636699"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="47831-102">IMethodMalloc::Alloc (Método)</span><span class="sxs-lookup"><span data-stu-id="47831-102">IMethodMalloc::Alloc Method</span></span>

<span data-ttu-id="47831-103">Intenta asignar una cantidad de memoria especificada para un nuevo cuerpo de función de lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="47831-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>

## <a name="syntax"></a><span data-ttu-id="47831-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47831-104">Syntax</span></span>

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a><span data-ttu-id="47831-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47831-105">Parameters</span></span>

`cb`\
<span data-ttu-id="47831-106">[in] El número de bytes que se asignan para el cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="47831-106">[in] The number of bytes to allocate for the method body.</span></span>

## <a name="remarks"></a><span data-ttu-id="47831-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47831-107">Remarks</span></span>

 <span data-ttu-id="47831-108">Se iniciará la memoria asignada en una dirección mayor que la dirección base del módulo que está asociado con este asignador.</span><span class="sxs-lookup"><span data-stu-id="47831-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="47831-109">En otras palabras, cada asignador se crea para un módulo determinado y se intentará asignar memoria en un desplazamiento positivo desde su dirección base.</span><span class="sxs-lookup"><span data-stu-id="47831-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="47831-110">Si `Alloc` no puede asignar el número solicitado de bytes en una dirección mayor que la dirección base del módulo, devuelve E_OUTOFMEMORY, independientemente de la cantidad de espacio de memoria disponible.</span><span class="sxs-lookup"><span data-stu-id="47831-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>

 <span data-ttu-id="47831-111">El `Alloc` método debe usarse junto con el [SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="47831-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="47831-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47831-112">Requirements</span></span>
 <span data-ttu-id="47831-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47831-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="47831-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="47831-114">**Header:** CorProf.idl, CorProf.h</span></span>

 <span data-ttu-id="47831-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47831-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="47831-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47831-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="47831-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="47831-117">See also</span></span>

- [<span data-ttu-id="47831-118">IMethodMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="47831-118">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)

---
description: 'Más información sobre: IMethodMalloc:: Alloc (método)'
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
ms.openlocfilehash: f8a41530e0e1a126fafa1816e6fed58d10df6587
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736959"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="e6466-103">IMethodMalloc::Alloc (Método)</span><span class="sxs-lookup"><span data-stu-id="e6466-103">IMethodMalloc::Alloc Method</span></span>

<span data-ttu-id="e6466-104">Intenta asignar una cantidad de memoria especificada para un nuevo cuerpo de la función del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="e6466-104">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6466-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6466-105">Syntax</span></span>

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a><span data-ttu-id="e6466-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6466-106">Parameters</span></span>

`cb`\
<span data-ttu-id="e6466-107">de Número de bytes que se van a asignar para el cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="e6466-107">[in] The number of bytes to allocate for the method body.</span></span>

## <a name="remarks"></a><span data-ttu-id="e6466-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e6466-108">Remarks</span></span>

 <span data-ttu-id="e6466-109">La memoria asignada comenzará en una dirección mayor que la dirección base del módulo que está asociado a este asignador.</span><span class="sxs-lookup"><span data-stu-id="e6466-109">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="e6466-110">En otras palabras, cada asignador se crea para un módulo determinado e intentará asignar memoria en un desplazamiento positivo desde su dirección base.</span><span class="sxs-lookup"><span data-stu-id="e6466-110">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="e6466-111">Si `Alloc` no puede asignar el número solicitado de bytes en una dirección mayor que la dirección base del módulo, devuelve E_OUTOFMEMORY, independientemente de la cantidad real de espacio de memoria disponible.</span><span class="sxs-lookup"><span data-stu-id="e6466-111">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>

 <span data-ttu-id="e6466-112">El `Alloc` método se debe usar junto con el método [ICorProfilerInfo:: SetILFunctionBody (](icorprofilerinfo-setilfunctionbody-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e6466-112">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e6466-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6466-113">Requirements</span></span>

 <span data-ttu-id="e6466-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6466-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="e6466-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e6466-115">**Header:** CorProf.idl, CorProf.h</span></span>

 <span data-ttu-id="e6466-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6466-116">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="e6466-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6466-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e6466-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6466-118">See also</span></span>

- [<span data-ttu-id="e6466-119">IMethodMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6466-119">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)

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
ms.openlocfilehash: 9a676989bdc6866f85fabe3e15b1e6b7b8b5a9a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000719"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="909a2-102">IMethodMalloc::Alloc (Método)</span><span class="sxs-lookup"><span data-stu-id="909a2-102">IMethodMalloc::Alloc Method</span></span>

<span data-ttu-id="909a2-103">Intenta asignar una cantidad de memoria especificada para un nuevo cuerpo de función de lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="909a2-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>

## <a name="syntax"></a><span data-ttu-id="909a2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="909a2-104">Syntax</span></span>

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a><span data-ttu-id="909a2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="909a2-105">Parameters</span></span>

`cb`\
<span data-ttu-id="909a2-106">[in] El número de bytes que se asignan para el cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="909a2-106">[in] The number of bytes to allocate for the method body.</span></span>

## <a name="remarks"></a><span data-ttu-id="909a2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="909a2-107">Remarks</span></span>

 <span data-ttu-id="909a2-108">Se iniciará la memoria asignada en una dirección mayor que la dirección base del módulo que está asociado con este asignador.</span><span class="sxs-lookup"><span data-stu-id="909a2-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="909a2-109">En otras palabras, cada asignador se crea para un módulo determinado y se intentará asignar memoria en un desplazamiento positivo desde su dirección base.</span><span class="sxs-lookup"><span data-stu-id="909a2-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="909a2-110">Si `Alloc` no puede asignar el número solicitado de bytes en una dirección mayor que la dirección base del módulo, devuelve E_OUTOFMEMORY, independientemente de la cantidad de espacio de memoria disponible.</span><span class="sxs-lookup"><span data-stu-id="909a2-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>

 <span data-ttu-id="909a2-111">El `Alloc` método debe usarse junto con el [SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="909a2-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="909a2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="909a2-112">Requirements</span></span>
 <span data-ttu-id="909a2-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="909a2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="909a2-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="909a2-114">**Header:** CorProf.idl, CorProf.h</span></span>

 <span data-ttu-id="909a2-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="909a2-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="909a2-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="909a2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="909a2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="909a2-117">See also</span></span>

- [<span data-ttu-id="909a2-118">IMethodMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="909a2-118">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)
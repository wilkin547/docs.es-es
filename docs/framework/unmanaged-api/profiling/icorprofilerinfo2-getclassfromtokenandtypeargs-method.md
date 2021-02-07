---
description: 'Más información acerca de: ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs ((método)'
title: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
ms.openlocfilehash: 810445d2617beff55e00df6bb30130d81c740ba4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760512"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="a6998-103">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs (Método)</span><span class="sxs-lookup"><span data-stu-id="a6998-103">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>

<span data-ttu-id="a6998-104">Obtiene el `ClassID` de un tipo mediante el token de metadatos especificado y los `ClassID` valores de cualquier argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="a6998-104">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6998-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6998-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6998-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a6998-106">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="a6998-107">de IDENTIFICADOR del módulo en el que reside el tipo.</span><span class="sxs-lookup"><span data-stu-id="a6998-107">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="a6998-108">de `mdTypeDef` Token de metadatos que hace referencia al tipo.</span><span class="sxs-lookup"><span data-stu-id="a6998-108">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="a6998-109">de El número de parámetros de tipo para el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="a6998-109">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="a6998-110">Este valor debe ser cero para los tipos no genéricos.</span><span class="sxs-lookup"><span data-stu-id="a6998-110">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="a6998-111">de Matriz de `ClassID` valores, cada uno de los cuales es un argumento del tipo.</span><span class="sxs-lookup"><span data-stu-id="a6998-111">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="a6998-112">El valor de `typeArgs` puede ser null si `cTypeArgs` está establecido en cero.</span><span class="sxs-lookup"><span data-stu-id="a6998-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="a6998-113">enuncia Puntero al `ClassID` del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="a6998-113">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6998-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a6998-114">Remarks</span></span>  

 <span data-ttu-id="a6998-115">La llamada al `GetClassFromTokenAndTypeArgs` método con un `mdTypeRef` token en lugar de `mdTypeDef` metadatos puede tener resultados imprevisibles; los llamadores deben resolver el `mdTypeRef` en un `mdTypeDef` cuando lo pasen.</span><span class="sxs-lookup"><span data-stu-id="a6998-115">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="a6998-116">Si el tipo todavía no está cargado, al llamar a `GetClassFromTokenAndTypeArgs` se desencadenará la carga, que es una operación peligrosa en muchos contextos.</span><span class="sxs-lookup"><span data-stu-id="a6998-116">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="a6998-117">Por ejemplo, si se llama a este método durante la carga de módulos u otros tipos, podría producirse un bucle infinito, ya que el tiempo de ejecución intenta cargar elementos de forma circular.</span><span class="sxs-lookup"><span data-stu-id="a6998-117">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="a6998-118">En general, `GetClassFromTokenAndTypeArgs` no se recomienda el uso de.</span><span class="sxs-lookup"><span data-stu-id="a6998-118">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="a6998-119">Si los perfiles están interesados en eventos de un tipo determinado, deben almacenar `ModuleID` y `mdTypeDef` de ese tipo, y usar [ICorProfilerInfo2:: GetClassIDInfo2 (](icorprofilerinfo2-getclassidinfo2-method.md) para comprobar si un determinado `ClassID` es el del tipo deseado.</span><span class="sxs-lookup"><span data-stu-id="a6998-119">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6998-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6998-120">Requirements</span></span>  

 <span data-ttu-id="a6998-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6998-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6998-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a6998-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a6998-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6998-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6998-124">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6998-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6998-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6998-125">See also</span></span>

- [<span data-ttu-id="a6998-126">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6998-126">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="a6998-127">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6998-127">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)

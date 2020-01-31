---
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
ms.openlocfilehash: e0663ff122397ba639a0a219e513be2f3f0cbbef
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862797"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="d808e-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs (Método)</span><span class="sxs-lookup"><span data-stu-id="d808e-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="d808e-103">Obtiene el `ClassID` de un tipo mediante el token de metadatos especificado y los valores `ClassID` de cualquier argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="d808e-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d808e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d808e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d808e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="d808e-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="d808e-106">de IDENTIFICADOR del módulo en el que reside el tipo.</span><span class="sxs-lookup"><span data-stu-id="d808e-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="d808e-107">de Un token de metadatos de `mdTypeDef` que hace referencia al tipo.</span><span class="sxs-lookup"><span data-stu-id="d808e-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="d808e-108">de El número de parámetros de tipo para el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="d808e-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="d808e-109">Este valor debe ser cero para los tipos no genéricos.</span><span class="sxs-lookup"><span data-stu-id="d808e-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="d808e-110">de Matriz de valores de `ClassID`, cada uno de los cuales es un argumento del tipo.</span><span class="sxs-lookup"><span data-stu-id="d808e-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="d808e-111">El valor de `typeArgs` puede ser NULL si `cTypeArgs` está establecido en cero.</span><span class="sxs-lookup"><span data-stu-id="d808e-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="d808e-112">enuncia Puntero a la `ClassID` del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="d808e-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d808e-113">Notas</span><span class="sxs-lookup"><span data-stu-id="d808e-113">Remarks</span></span>  
 <span data-ttu-id="d808e-114">Llamar al método `GetClassFromTokenAndTypeArgs` con un `mdTypeRef` en lugar de un token de metadatos de `mdTypeDef` puede tener resultados imprevisibles; los llamadores deben resolver el `mdTypeRef` en un `mdTypeDef` al pasarlo.</span><span class="sxs-lookup"><span data-stu-id="d808e-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="d808e-115">Si el tipo todavía no está cargado, al llamar a `GetClassFromTokenAndTypeArgs` se desencadenará la carga, que es una operación peligrosa en muchos contextos.</span><span class="sxs-lookup"><span data-stu-id="d808e-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="d808e-116">Por ejemplo, si se llama a este método durante la carga de módulos u otros tipos, podría producirse un bucle infinito, ya que el tiempo de ejecución intenta cargar elementos de forma circular.</span><span class="sxs-lookup"><span data-stu-id="d808e-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="d808e-117">En general, no se recomienda el uso de `GetClassFromTokenAndTypeArgs`.</span><span class="sxs-lookup"><span data-stu-id="d808e-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="d808e-118">Si los perfiles están interesados en eventos de un tipo determinado, deben almacenar el `ModuleID` y `mdTypeDef` de ese tipo y usar [ICorProfilerInfo2:: GetClassIDInfo2 (](icorprofilerinfo2-getclassidinfo2-method.md) para comprobar si un `ClassID` determinado es el del tipo deseado.</span><span class="sxs-lookup"><span data-stu-id="d808e-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d808e-119">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="d808e-119">Requirements</span></span>  
 <span data-ttu-id="d808e-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d808e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d808e-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d808e-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d808e-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d808e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d808e-123">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d808e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d808e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d808e-124">See also</span></span>

- [<span data-ttu-id="d808e-125">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d808e-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="d808e-126">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d808e-126">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)

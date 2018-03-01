---
title: "ICorProfilerInfo::GetObjectSize (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo.GetObjectSize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9425938042485c4330fe3fbc50cdabde6451b427
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="10e51-102">ICorProfilerInfo::GetObjectSize (Método)</span><span class="sxs-lookup"><span data-stu-id="10e51-102">ICorProfilerInfo::GetObjectSize Method</span></span>
<span data-ttu-id="10e51-103">Obtiene el tamaño de un objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="10e51-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10e51-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10e51-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10e51-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="10e51-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="10e51-106">[in] El identificador del objeto.</span><span class="sxs-lookup"><span data-stu-id="10e51-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="10e51-107">[out] Puntero al tamaño del objeto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="10e51-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10e51-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="10e51-108">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="10e51-109">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="10e51-109">This method is obsolete.</span></span> <span data-ttu-id="10e51-110">Devuelve COR_E_OVERFLOW para objetos de más de 4GB en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="10e51-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="10e51-111">Use la [icorprofilerinfo4:: Getobjectsize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="10e51-111">Use the  [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="10e51-112">A menudo, distintos objetos de los mismos tipos tienen el mismo tamaño.</span><span class="sxs-lookup"><span data-stu-id="10e51-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="10e51-113">Sin embargo, algunos tipos, como matrices o cadenas, pueden tener un tamaño diferente para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="10e51-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="10e51-114">El tamaño devuelto por la `GetObjectSize` método no incluye ningún relleno de alineación que puede aparecer después de que el objeto está en el montón de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="10e51-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="10e51-115">Si usas el `GetObjectSize` método para avanzar de objeto a objeto en el montón de elementos no utilizados, agregar alineación relleno manualmente, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="10e51-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
-   <span data-ttu-id="10e51-116">En Windows de 32 bits, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 y COR_PRF_GC_GEN_2 usan una alineación de 4 bytes, y COR_PRF_GC_LARGE_OBJECT_HEAP utiliza alineación de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="10e51-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
-   <span data-ttu-id="10e51-117">En Windows de 64 bits, la alineación siempre tiene 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="10e51-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10e51-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10e51-118">Requirements</span></span>  
 <span data-ttu-id="10e51-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10e51-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10e51-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="10e51-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="10e51-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10e51-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10e51-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10e51-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10e51-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="10e51-123">See Also</span></span>  
 [<span data-ttu-id="10e51-124">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="10e51-124">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

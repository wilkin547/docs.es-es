---
title: ICorProfilerInfo::GetObjectSize (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 4abcf9f4575b32dd125fd8a00783043900993c3e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724109"
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="270ce-102">ICorProfilerInfo::GetObjectSize (Método)</span><span class="sxs-lookup"><span data-stu-id="270ce-102">ICorProfilerInfo::GetObjectSize Method</span></span>

<span data-ttu-id="270ce-103">Obtiene el tamaño de un objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="270ce-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="270ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="270ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="270ce-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="270ce-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="270ce-106">de IDENTIFICADOR del objeto.</span><span class="sxs-lookup"><span data-stu-id="270ce-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="270ce-107">enuncia Puntero al tamaño del objeto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="270ce-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="270ce-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="270ce-108">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="270ce-109">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="270ce-109">This method is obsolete.</span></span> <span data-ttu-id="270ce-110">Devuelve COR_E_OVERFLOW para objetos superiores a 4 GB en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="270ce-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="270ce-111">Use el método  [ICorProfilerInfo4:: getobjectsize2 (](icorprofilerinfo4-getobjectsize2-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="270ce-111">Use the  [ICorProfilerInfo4::GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="270ce-112">A menudo, los distintos objetos de los mismos tipos tienen el mismo tamaño.</span><span class="sxs-lookup"><span data-stu-id="270ce-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="270ce-113">Sin embargo, algunos tipos, como matrices o cadenas, pueden tener un tamaño diferente para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="270ce-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="270ce-114">El tamaño devuelto por el `GetObjectSize` método no incluye ningún relleno de alineación que pueda aparecer después de que el objeto se encuentra en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="270ce-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="270ce-115">Si usa el `GetObjectSize` método para avanzar de objeto a objeto en el montón de recolección de elementos no utilizados, agregue el relleno de alineación manualmente, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="270ce-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
- <span data-ttu-id="270ce-116">En Windows de 32 bits, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 y COR_PRF_GC_GEN_2 utilizan la alineación de 4 bytes y COR_PRF_GC_LARGE_OBJECT_HEAP utiliza la alineación de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="270ce-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
- <span data-ttu-id="270ce-117">En Windows de 64 bits, la alineación es siempre de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="270ce-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="270ce-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="270ce-118">Requirements</span></span>  

 <span data-ttu-id="270ce-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="270ce-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="270ce-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="270ce-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="270ce-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="270ce-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="270ce-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="270ce-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="270ce-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="270ce-123">See also</span></span>

- [<span data-ttu-id="270ce-124">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="270ce-124">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

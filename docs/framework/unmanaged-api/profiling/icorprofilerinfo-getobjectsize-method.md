---
description: 'Más información acerca de: ICorProfilerInfo:: GetObjectSize ((método)'
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
ms.openlocfilehash: c762b43e87c6f25b301f3f677728ca8cbe19b138
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788636"
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="9efbf-103">ICorProfilerInfo::GetObjectSize (Método)</span><span class="sxs-lookup"><span data-stu-id="9efbf-103">ICorProfilerInfo::GetObjectSize Method</span></span>

<span data-ttu-id="9efbf-104">Obtiene el tamaño de un objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="9efbf-104">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9efbf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9efbf-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9efbf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9efbf-106">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="9efbf-107">de IDENTIFICADOR del objeto.</span><span class="sxs-lookup"><span data-stu-id="9efbf-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="9efbf-108">enuncia Puntero al tamaño del objeto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="9efbf-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9efbf-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9efbf-109">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9efbf-110">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="9efbf-110">This method is obsolete.</span></span> <span data-ttu-id="9efbf-111">Devuelve COR_E_OVERFLOW para objetos superiores a 4 GB en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="9efbf-111">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="9efbf-112">Use el método  [ICorProfilerInfo4:: getobjectsize2 (](icorprofilerinfo4-getobjectsize2-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="9efbf-112">Use the  [ICorProfilerInfo4::GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="9efbf-113">A menudo, los distintos objetos de los mismos tipos tienen el mismo tamaño.</span><span class="sxs-lookup"><span data-stu-id="9efbf-113">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="9efbf-114">Sin embargo, algunos tipos, como matrices o cadenas, pueden tener un tamaño diferente para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="9efbf-114">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="9efbf-115">El tamaño devuelto por el `GetObjectSize` método no incluye ningún relleno de alineación que pueda aparecer después de que el objeto se encuentra en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="9efbf-115">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="9efbf-116">Si usa el `GetObjectSize` método para avanzar de objeto a objeto en el montón de recolección de elementos no utilizados, agregue el relleno de alineación manualmente, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9efbf-116">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
- <span data-ttu-id="9efbf-117">En Windows de 32 bits, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 y COR_PRF_GC_GEN_2 utilizan la alineación de 4 bytes y COR_PRF_GC_LARGE_OBJECT_HEAP utiliza la alineación de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="9efbf-117">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
- <span data-ttu-id="9efbf-118">En Windows de 64 bits, la alineación es siempre de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="9efbf-118">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9efbf-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9efbf-119">Requirements</span></span>  

 <span data-ttu-id="9efbf-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9efbf-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9efbf-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9efbf-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9efbf-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9efbf-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9efbf-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9efbf-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9efbf-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="9efbf-124">See also</span></span>

- [<span data-ttu-id="9efbf-125">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9efbf-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

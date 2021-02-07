---
description: 'Más información sobre: IMetaDataEmit:: Setclasslayout ((método)'
title: IMetaDataEmit::SetClassLayout (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
ms.openlocfilehash: e0ce8e93137b9a32a13ca86ead539385523fa8a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706609"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="e80c4-103">IMetaDataEmit::SetClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="e80c4-103">IMetaDataEmit::SetClassLayout Method</span></span>

<span data-ttu-id="e80c4-104">Completa el diseño de los campos de una clase definida por una llamada anterior al [método DefineTypeDef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="e80c4-104">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e80c4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e80c4-105">Syntax</span></span>  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e80c4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e80c4-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="e80c4-107">de `mdTypeDef` Token que especifica la clase que se va a disponer.</span><span class="sxs-lookup"><span data-stu-id="e80c4-107">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="e80c4-108">de Tamaño de empaquetado: 1, 2, 4, 8 o 16 bytes.</span><span class="sxs-lookup"><span data-stu-id="e80c4-108">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="e80c4-109">El tamaño de empaquetado es el número de bytes entre los campos adyacentes.</span><span class="sxs-lookup"><span data-stu-id="e80c4-109">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="e80c4-110">de Matriz de estructuras [COR_FIELD_OFFSET](cor-field-offset-structure.md) , cada una de las cuales especifica un campo de la clase y el desplazamiento del campo dentro de la clase.</span><span class="sxs-lookup"><span data-stu-id="e80c4-110">[in] An array of [COR_FIELD_OFFSET](cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="e80c4-111">Finalice la matriz con `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="e80c4-111">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="e80c4-112">de Tamaño, en bytes, de la clase.</span><span class="sxs-lookup"><span data-stu-id="e80c4-112">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e80c4-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e80c4-113">Remarks</span></span>  

 <span data-ttu-id="e80c4-114">La clase se define inicialmente llamando al método [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md) y especificando uno de los tres diseños para los campos de la clase: automático, secuencial o explícito.</span><span class="sxs-lookup"><span data-stu-id="e80c4-114">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="e80c4-115">Normalmente, usaría el diseño automático y dejar que el tiempo de ejecución elija la mejor manera de diseñar los campos.</span><span class="sxs-lookup"><span data-stu-id="e80c4-115">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="e80c4-116">Sin embargo, es posible que desee que los campos estén dispuestos según la disposición que utiliza el código no administrado.</span><span class="sxs-lookup"><span data-stu-id="e80c4-116">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="e80c4-117">En este caso, elija diseño secuencial o explícito y llame `SetClassLayout` a para completar el diseño de los campos:</span><span class="sxs-lookup"><span data-stu-id="e80c4-117">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
- <span data-ttu-id="e80c4-118">Diseño secuencial: especifique el tamaño de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="e80c4-118">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="e80c4-119">Un campo está alineado según su tamaño natural o el tamaño de empaquetado, lo que sea el desplazamiento más pequeño del campo.</span><span class="sxs-lookup"><span data-stu-id="e80c4-119">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="e80c4-120">Establezca `rFieldOffsets` y `ulClassSize` en cero.</span><span class="sxs-lookup"><span data-stu-id="e80c4-120">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
- <span data-ttu-id="e80c4-121">Diseño explícito: especifique el desplazamiento de cada campo o especifique el tamaño de la clase y el tamaño de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="e80c4-121">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e80c4-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e80c4-122">Requirements</span></span>  

 <span data-ttu-id="e80c4-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e80c4-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e80c4-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e80c4-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e80c4-125">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e80c4-125">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e80c4-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e80c4-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e80c4-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e80c4-127">See also</span></span>

- [<span data-ttu-id="e80c4-128">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e80c4-128">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="e80c4-129">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e80c4-129">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

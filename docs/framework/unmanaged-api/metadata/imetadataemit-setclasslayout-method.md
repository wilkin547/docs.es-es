---
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
ms.openlocfilehash: ee10907fb7f5d90db1bdce845272cd3de38e35a6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718701"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="6b8e7-102">IMetaDataEmit::SetClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="6b8e7-102">IMetaDataEmit::SetClassLayout Method</span></span>

<span data-ttu-id="6b8e7-103">Completa el diseño de los campos de una clase definida por una llamada anterior al [método DefineTypeDef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="6b8e7-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b8e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b8e7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b8e7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6b8e7-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="6b8e7-106">de `mdTypeDef` Token que especifica la clase que se va a disponer.</span><span class="sxs-lookup"><span data-stu-id="6b8e7-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="6b8e7-107">de Tamaño de empaquetado: 1, 2, 4, 8 o 16 bytes.</span><span class="sxs-lookup"><span data-stu-id="6b8e7-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="6b8e7-108">El tamaño de empaquetado es el número de bytes entre los campos adyacentes.</span><span class="sxs-lookup"><span data-stu-id="6b8e7-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="6b8e7-109">de Matriz de estructuras [COR_FIELD_OFFSET](cor-field-offset-structure.md) , cada una de las cuales especifica un campo de la clase y el desplazamiento del campo dentro de la clase.</span><span class="sxs-lookup"><span data-stu-id="6b8e7-109">[in] An array of [COR_FIELD_OFFSET](cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="6b8e7-110">Finalice la matriz con `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="6b8e7-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="6b8e7-111">de Tamaño, en bytes, de la clase.</span><span class="sxs-lookup"><span data-stu-id="6b8e7-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b8e7-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b8e7-112">Remarks</span></span>  

 <span data-ttu-id="6b8e7-113">La clase se define inicialmente llamando al método [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md) y especificando uno de los tres diseños para los campos de la clase: automático, secuencial o explícito.</span><span class="sxs-lookup"><span data-stu-id="6b8e7-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="6b8e7-114">Normalmente, usaría el diseño automático y dejar que el tiempo de ejecución elija la mejor manera de diseñar los campos.</span><span class="sxs-lookup"><span data-stu-id="6b8e7-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="6b8e7-115">Sin embargo, es posible que desee que los campos estén dispuestos según la disposición que utiliza el código no administrado.</span><span class="sxs-lookup"><span data-stu-id="6b8e7-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="6b8e7-116">En este caso, elija diseño secuencial o explícito y llame `SetClassLayout` a para completar el diseño de los campos:</span><span class="sxs-lookup"><span data-stu-id="6b8e7-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
- <span data-ttu-id="6b8e7-117">Diseño secuencial: especifique el tamaño de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="6b8e7-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="6b8e7-118">Un campo está alineado según su tamaño natural o el tamaño de empaquetado, lo que sea el desplazamiento más pequeño del campo.</span><span class="sxs-lookup"><span data-stu-id="6b8e7-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="6b8e7-119">Establezca `rFieldOffsets` y `ulClassSize` en cero.</span><span class="sxs-lookup"><span data-stu-id="6b8e7-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
- <span data-ttu-id="6b8e7-120">Diseño explícito: especifique el desplazamiento de cada campo o especifique el tamaño de la clase y el tamaño de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="6b8e7-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b8e7-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b8e7-121">Requirements</span></span>  

 <span data-ttu-id="6b8e7-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b8e7-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b8e7-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6b8e7-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6b8e7-124">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6b8e7-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b8e7-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b8e7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b8e7-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b8e7-126">See also</span></span>

- [<span data-ttu-id="6b8e7-127">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b8e7-127">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="6b8e7-128">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b8e7-128">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

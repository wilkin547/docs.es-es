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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28eb8124d201f474ac8029a4c2b8a908755d6f8e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64584670"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="436c8-102">IMetaDataEmit::SetClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="436c8-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="436c8-103">Se completa el diseño de campos para una clase que se ha definido por una llamada anterior a [DefineTypeDef (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="436c8-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="436c8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="436c8-104">Syntax</span></span>  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="436c8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="436c8-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="436c8-106">[in] Un `mdTypeDef` símbolo (token) que especifica la clase que se coloquen.</span><span class="sxs-lookup"><span data-stu-id="436c8-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="436c8-107">[in] El tamaño de empaquetado: 1, 2, 4, 8 ó 16 bytes.</span><span class="sxs-lookup"><span data-stu-id="436c8-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="436c8-108">El tamaño de empaquetado es el número de bytes entre los campos adyacentes.</span><span class="sxs-lookup"><span data-stu-id="436c8-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="436c8-109">[in] Una matriz de [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) estructuras, cada uno de los cuales especifica un campo de la clase y el campo de desplazamiento dentro de la clase.</span><span class="sxs-lookup"><span data-stu-id="436c8-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="436c8-110">Finalice la matriz con `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="436c8-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="436c8-111">[in] El tamaño, en bytes, de la clase.</span><span class="sxs-lookup"><span data-stu-id="436c8-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="436c8-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="436c8-112">Remarks</span></span>  
 <span data-ttu-id="436c8-113">La clase inicialmente se define mediante una llamada a la [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) método y especifique uno de los tres diseños para los campos de la clase: automático, secuencial o explícito.</span><span class="sxs-lookup"><span data-stu-id="436c8-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="436c8-114">Normalmente, debe usar el diseño automático y dejar que el tiempo de ejecución a elegir la mejor manera de diseñar los campos.</span><span class="sxs-lookup"><span data-stu-id="436c8-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="436c8-115">Sin embargo, es posible que desea que los campos que disponen de acuerdo con la disposición en el código no administrado.</span><span class="sxs-lookup"><span data-stu-id="436c8-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="436c8-116">En este caso, elija un diseño secuencial o explícito y llame a `SetClassLayout` para completar el diseño de los campos:</span><span class="sxs-lookup"><span data-stu-id="436c8-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
- <span data-ttu-id="436c8-117">Diseño secuencial: Especifique el tamaño de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="436c8-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="436c8-118">Un campo se alinea según su tamaño natural o el tamaño de empaquetado, sea cual sea resultados en el desplazamiento del campo más pequeño.</span><span class="sxs-lookup"><span data-stu-id="436c8-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="436c8-119">Establecer `rFieldOffsets` y `ulClassSize` a cero.</span><span class="sxs-lookup"><span data-stu-id="436c8-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
- <span data-ttu-id="436c8-120">Diseño explícito: Especificar el desplazamiento de cada campo o especificar el tamaño de la clase y el tamaño de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="436c8-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="436c8-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="436c8-121">Requirements</span></span>  
 <span data-ttu-id="436c8-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="436c8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="436c8-123">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="436c8-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="436c8-124">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="436c8-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="436c8-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="436c8-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="436c8-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="436c8-126">See also</span></span>

- [<span data-ttu-id="436c8-127">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="436c8-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="436c8-128">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="436c8-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

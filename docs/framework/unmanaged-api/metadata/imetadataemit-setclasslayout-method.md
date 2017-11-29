---
title: "IMetaDataEmit::SetClassLayout (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetClassLayout
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a68d94cbea408bee90b117965f83f760ba7ea5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="7c486-102">IMetaDataEmit::SetClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="7c486-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="7c486-103">Complete el diseño de campos para una clase que se ha definido por una llamada anterior a [DefineTypeDef (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="7c486-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c486-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c486-104">Syntax</span></span>  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c486-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c486-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="7c486-106">[in] Un `mdTypeDef` símbolo (token) que especifica la clase que se coloquen.</span><span class="sxs-lookup"><span data-stu-id="7c486-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="7c486-107">[in] El tamaño de empaquetado: 1, 2, 4, 8 o 16 bytes.</span><span class="sxs-lookup"><span data-stu-id="7c486-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="7c486-108">El tamaño de empaquetado es el número de bytes entre los campos adyacentes.</span><span class="sxs-lookup"><span data-stu-id="7c486-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="7c486-109">[in] Una matriz de [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) estructuras, cada uno de los cuales especifica un campo de la clase y el campo de desplazamiento dentro de la clase.</span><span class="sxs-lookup"><span data-stu-id="7c486-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="7c486-110">Finalice la matriz con `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="7c486-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="7c486-111">[in] El tamaño, en bytes, de la clase.</span><span class="sxs-lookup"><span data-stu-id="7c486-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c486-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7c486-112">Remarks</span></span>  
 <span data-ttu-id="7c486-113">La clase inicialmente se define mediante una llamada a la [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) método y especificando uno de tres diseños para los campos de la clase: automático, secuencial o explícita.</span><span class="sxs-lookup"><span data-stu-id="7c486-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="7c486-114">Normalmente, debería usar el diseño automático y dejar que el tiempo de ejecución a elegir la mejor manera de diseñar los campos.</span><span class="sxs-lookup"><span data-stu-id="7c486-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="7c486-115">Sin embargo, puede que los campos que se dispone de acuerdo con la organización en el código no administrado.</span><span class="sxs-lookup"><span data-stu-id="7c486-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="7c486-116">En este caso, elija diseño secuencial o explícito y llame al método `SetClassLayout` para completar el diseño de los campos:</span><span class="sxs-lookup"><span data-stu-id="7c486-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
-   <span data-ttu-id="7c486-117">Un diseño secuencial: especifique el tamaño de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="7c486-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="7c486-118">Un campo se alinea según su tamaño natural o el tamaño de empaquetado, sea cual sea resultados en el desplazamiento más pequeño del campo.</span><span class="sxs-lookup"><span data-stu-id="7c486-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="7c486-119">Establecer `rFieldOffsets` y `ulClassSize` a cero.</span><span class="sxs-lookup"><span data-stu-id="7c486-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
-   <span data-ttu-id="7c486-120">Diseño explícito: especifique el desplazamiento de cada campo, o el tamaño de la clase y el tamaño de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="7c486-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c486-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c486-121">Requirements</span></span>  
 <span data-ttu-id="7c486-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c486-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c486-123">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c486-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c486-124">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c486-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c486-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c486-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c486-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c486-126">See Also</span></span>  
 [<span data-ttu-id="7c486-127">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c486-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="7c486-128">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c486-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

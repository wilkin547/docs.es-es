---
title: "IMetaDataImport::EnumMethodSemantics (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMethodSemantics
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0d5ec79701f73b8beb7759d72b972fc347a339c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="70cae-102">IMetaDataImport::EnumMethodSemantics (Método)</span><span class="sxs-lookup"><span data-stu-id="70cae-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="70cae-103">Enumera las propiedades y los eventos de cambio de propiedad con los que está relacionado el método especificado.</span><span class="sxs-lookup"><span data-stu-id="70cae-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70cae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70cae-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="70cae-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70cae-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="70cae-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="70cae-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="70cae-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="70cae-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="70cae-108">[in] Símbolo (token) de MethodDef que limita el ámbito de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="70cae-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="70cae-109">[out] La matriz que se utiliza para almacenar los eventos o propiedades.</span><span class="sxs-lookup"><span data-stu-id="70cae-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="70cae-110">[in] Tamaño máximo de la matriz `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="70cae-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="70cae-111">[out] El número de eventos o propiedades que se devuelven en `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="70cae-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70cae-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="70cae-112">Return Value</span></span>  
  
|<span data-ttu-id="70cae-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="70cae-113">HRESULT</span></span>|<span data-ttu-id="70cae-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="70cae-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="70cae-115">`EnumMethodSemantics`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="70cae-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="70cae-116">No hay ningún suceso o propiedades que enumerar.</span><span class="sxs-lookup"><span data-stu-id="70cae-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="70cae-117">En ese caso, `pcEventProp` es cero.</span><span class="sxs-lookup"><span data-stu-id="70cae-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70cae-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="70cae-118">Remarks</span></span>  
 <span data-ttu-id="70cae-119">Definen muchos tipos de common language runtime *propiedad* `Changed` eventos y `On` *propiedad* `Changed` métodos relacionados con sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="70cae-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="70cae-120">Por ejemplo, el <xref:System.Windows.Forms.Control?displayProperty=nameWithType> tipo define un <xref:System.Windows.Forms.Control.Font%2A> propiedad, un <xref:System.Windows.Forms.Control.FontChanged> evento y un <xref:System.Windows.Forms.Control.OnFontChanged%2A> método.</span><span class="sxs-lookup"><span data-stu-id="70cae-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="70cae-121">El método de descriptor de acceso set de la <xref:System.Windows.Forms.Control.Font%2A> propiedad llamadas <xref:System.Windows.Forms.Control.OnFontChanged%2A> método, que a su vez desencadena el <xref:System.Windows.Forms.Control.FontChanged> eventos.</span><span class="sxs-lookup"><span data-stu-id="70cae-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="70cae-122">Debería llamar a `EnumMethodSemantics` usando el MethodDef de <xref:System.Windows.Forms.Control.OnFontChanged%2A> para obtener referencias a la <xref:System.Windows.Forms.Control.Font%2A> propiedad y el <xref:System.Windows.Forms.Control.FontChanged> eventos.</span><span class="sxs-lookup"><span data-stu-id="70cae-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70cae-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70cae-123">Requirements</span></span>  
 <span data-ttu-id="70cae-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70cae-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70cae-125">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="70cae-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="70cae-126">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="70cae-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="70cae-127">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70cae-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70cae-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="70cae-128">See Also</span></span>  
 [<span data-ttu-id="70cae-129">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="70cae-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="70cae-130">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="70cae-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

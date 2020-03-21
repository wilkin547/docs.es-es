---
title: IMetaDataImport::EnumMethodSemantics (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
ms.openlocfilehash: f20652a7f86576e64646a1f63c3e2c48b55cf811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175465"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="0da52-102">IMetaDataImport::EnumMethodSemantics (Método)</span><span class="sxs-lookup"><span data-stu-id="0da52-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="0da52-103">Enumera las propiedades y los eventos de cambio de propiedad con los que está relacionado el método especificado.</span><span class="sxs-lookup"><span data-stu-id="0da52-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da52-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0da52-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0da52-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0da52-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0da52-106">[adentro, fuera] Un puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="0da52-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="0da52-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="0da52-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="0da52-108">[en] Un token MethodDef que limita el ámbito de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="0da52-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="0da52-109">[fuera] Matriz utilizada para almacenar los eventos o propiedades.</span><span class="sxs-lookup"><span data-stu-id="0da52-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0da52-110">[in] Tamaño máximo de la matriz `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="0da52-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="0da52-111">[fuera] El número de eventos `rEventProp`o propiedades devueltos en .</span><span class="sxs-lookup"><span data-stu-id="0da52-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0da52-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0da52-112">Return Value</span></span>  
  
|<span data-ttu-id="0da52-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0da52-113">HRESULT</span></span>|<span data-ttu-id="0da52-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="0da52-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0da52-115">`EnumMethodSemantics`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="0da52-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0da52-116">No hay eventos ni propiedades que enumerar.</span><span class="sxs-lookup"><span data-stu-id="0da52-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="0da52-117">En ese `pcEventProp` caso, es cero.</span><span class="sxs-lookup"><span data-stu-id="0da52-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0da52-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0da52-118">Remarks</span></span>  
 <span data-ttu-id="0da52-119">Muchos tipos de *Property* `Changed` Common Language `On`Runtime definen eventos Property y métodos *Property* `Changed` relacionados con sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="0da52-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="0da52-120">Por ejemplo, <xref:System.Windows.Forms.Control?displayProperty=nameWithType> el <xref:System.Windows.Forms.Control.Font%2A> tipo define <xref:System.Windows.Forms.Control.FontChanged> una propiedad, un evento y un <xref:System.Windows.Forms.Control.OnFontChanged%2A> método.</span><span class="sxs-lookup"><span data-stu-id="0da52-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="0da52-121">El método de <xref:System.Windows.Forms.Control.Font%2A> descriptor <xref:System.Windows.Forms.Control.OnFontChanged%2A> de acceso set de <xref:System.Windows.Forms.Control.FontChanged> la propiedad llama al método, que a su vez provoca el evento.</span><span class="sxs-lookup"><span data-stu-id="0da52-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="0da52-122">Se llamaría `EnumMethodSemantics` a través <xref:System.Windows.Forms.Control.OnFontChanged%2A> de la MethodDef para obtener referencias a la <xref:System.Windows.Forms.Control.Font%2A> propiedad y el <xref:System.Windows.Forms.Control.FontChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="0da52-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0da52-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0da52-123">Requirements</span></span>  
 <span data-ttu-id="0da52-124">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0da52-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0da52-125">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0da52-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0da52-126">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0da52-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0da52-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0da52-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0da52-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0da52-128">See also</span></span>

- [<span data-ttu-id="0da52-129">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0da52-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0da52-130">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0da52-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

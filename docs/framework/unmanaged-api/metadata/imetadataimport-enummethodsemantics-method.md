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
ms.openlocfilehash: 213cbd955e3d47a49abde579a54af48641e225ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491932"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="ad4f9-102">IMetaDataImport::EnumMethodSemantics (Método)</span><span class="sxs-lookup"><span data-stu-id="ad4f9-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="ad4f9-103">Enumera las propiedades y los eventos de cambio de propiedad con los que está relacionado el método especificado.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad4f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad4f9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad4f9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ad4f9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ad4f9-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ad4f9-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="ad4f9-108">de Un token MethodDef que limita el ámbito de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="ad4f9-109">enuncia Matriz que se usa para almacenar los eventos o propiedades.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ad4f9-110">[in] Tamaño máximo de la matriz `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="ad4f9-111">enuncia Número de eventos o propiedades devueltos en `rEventProp` .</span><span class="sxs-lookup"><span data-stu-id="ad4f9-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad4f9-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ad4f9-112">Return Value</span></span>  
  
|<span data-ttu-id="ad4f9-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ad4f9-113">HRESULT</span></span>|<span data-ttu-id="ad4f9-114">Description</span><span class="sxs-lookup"><span data-stu-id="ad4f9-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ad4f9-115">`EnumMethodSemantics`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ad4f9-116">No hay eventos ni propiedades para enumerar.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="ad4f9-117">En ese caso, `pcEventProp` es cero.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad4f9-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad4f9-118">Remarks</span></span>  
 <span data-ttu-id="ad4f9-119">Muchos tipos de Common Language Runtime *Property* definen `Changed` los eventos de propiedad y `On` *Property* `Changed` los métodos de propiedad relacionados con sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="ad4f9-120">Por ejemplo, el <xref:System.Windows.Forms.Control?displayProperty=nameWithType> tipo define una <xref:System.Windows.Forms.Control.Font%2A> propiedad, un <xref:System.Windows.Forms.Control.FontChanged> evento y un <xref:System.Windows.Forms.Control.OnFontChanged%2A> método.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="ad4f9-121">El método de descriptor de acceso set de la <xref:System.Windows.Forms.Control.Font%2A> propiedad llama al <xref:System.Windows.Forms.Control.OnFontChanged%2A> método, que a su vez provoca el <xref:System.Windows.Forms.Control.FontChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="ad4f9-122">Llamaría al `EnumMethodSemantics` uso de MethodDef para <xref:System.Windows.Forms.Control.OnFontChanged%2A> para obtener referencias a la <xref:System.Windows.Forms.Control.Font%2A> propiedad y al <xref:System.Windows.Forms.Control.FontChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad4f9-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad4f9-123">Requirements</span></span>  
 <span data-ttu-id="ad4f9-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad4f9-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad4f9-125">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ad4f9-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ad4f9-126">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ad4f9-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ad4f9-127">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad4f9-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad4f9-128">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="ad4f9-128">See also</span></span>

- [<span data-ttu-id="ad4f9-129">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad4f9-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ad4f9-130">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad4f9-130">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

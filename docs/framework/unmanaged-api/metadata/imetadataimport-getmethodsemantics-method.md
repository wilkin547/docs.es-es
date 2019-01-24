---
title: IMetaDataImport::GetMethodSemantics (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a12310f1281da99706589894a4793c2a28c5b938
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745997"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="e78c6-102">IMetaDataImport::GetMethodSemantics (Método)</span><span class="sxs-lookup"><span data-stu-id="e78c6-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="e78c6-103">Obtiene marcadores que indican la relación entre el método al que hace referencia el token de MethodDef especificado y la propiedad emparejada y el evento al que hace referencia EventProp especificado (token).</span><span class="sxs-lookup"><span data-stu-id="e78c6-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e78c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e78c6-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e78c6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e78c6-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="e78c6-106">[in] Un token de MethodDef que representa el método para obtener la información semántica de funciones.</span><span class="sxs-lookup"><span data-stu-id="e78c6-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="e78c6-107">[in] Un token que representa la propiedad emparejada y eventos que se va a obtener la función del método.</span><span class="sxs-lookup"><span data-stu-id="e78c6-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="e78c6-108">[out] Un puntero a los marcadores semántica asociada.</span><span class="sxs-lookup"><span data-stu-id="e78c6-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="e78c6-109">Este valor es una máscara de bits desde el [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="e78c6-109">This value is a bitmask from the [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e78c6-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e78c6-110">Remarks</span></span>  
 <span data-ttu-id="e78c6-111">El [IMetaDataEmit:: DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) método establece las marcas de semántica de un método.</span><span class="sxs-lookup"><span data-stu-id="e78c6-111">The [IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e78c6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e78c6-112">Requirements</span></span>  
 <span data-ttu-id="e78c6-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e78c6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e78c6-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="e78c6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e78c6-115">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e78c6-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e78c6-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e78c6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e78c6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e78c6-117">See also</span></span>
- [<span data-ttu-id="e78c6-118">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e78c6-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e78c6-119">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e78c6-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

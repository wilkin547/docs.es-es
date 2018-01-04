---
title: "IMetaDataImport::GetMethodSemantics (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMethodSemantics
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f8921c4f6a676c9647d4e8907a22f0d68b0b359
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="12eb9-102">IMetaDataImport::GetMethodSemantics (Método)</span><span class="sxs-lookup"><span data-stu-id="12eb9-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="12eb9-103">Obtiene marcadores que indica la relación entre el método al que hace referencia el token de MethodDef especificado y la propiedad emparejada y el evento al que hace referencia EventProp especificado símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="12eb9-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12eb9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12eb9-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12eb9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="12eb9-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="12eb9-106">[in] Símbolo (token) de MethodDef que representa el método para obtener la información semántica de funciones.</span><span class="sxs-lookup"><span data-stu-id="12eb9-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="12eb9-107">[in] Un token que representa la propiedad emparejada y el evento para el que se va a obtener la función del método.</span><span class="sxs-lookup"><span data-stu-id="12eb9-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="12eb9-108">[out] Un puntero a los marcadores de semántica asociada.</span><span class="sxs-lookup"><span data-stu-id="12eb9-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="12eb9-109">Este valor es una máscara de bits de la [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="12eb9-109">This value is a bitmask from the [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12eb9-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="12eb9-110">Remarks</span></span>  
 <span data-ttu-id="12eb9-111">El [IMetaDataEmit:: DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) método establece marcas de semántica de un método.</span><span class="sxs-lookup"><span data-stu-id="12eb9-111">The [IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12eb9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="12eb9-112">Requirements</span></span>  
 <span data-ttu-id="12eb9-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12eb9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12eb9-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="12eb9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12eb9-115">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="12eb9-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="12eb9-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12eb9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12eb9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="12eb9-117">See Also</span></span>  
 [<span data-ttu-id="12eb9-118">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="12eb9-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="12eb9-119">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="12eb9-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

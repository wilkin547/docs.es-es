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
ms.openlocfilehash: 4f4908f5d03687fb415c91325941aaab148832dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447748"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="bf5d5-102">IMetaDataImport::GetMethodSemantics (Método)</span><span class="sxs-lookup"><span data-stu-id="bf5d5-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="bf5d5-103">Obtiene marcadores que indica la relación entre el método al que hace referencia el token de MethodDef especificado y la propiedad emparejada y el evento al que hace referencia EventProp especificado símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="bf5d5-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf5d5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf5d5-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf5d5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf5d5-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="bf5d5-106">[in] Símbolo (token) de MethodDef que representa el método para obtener la información semántica de funciones.</span><span class="sxs-lookup"><span data-stu-id="bf5d5-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="bf5d5-107">[in] Un token que representa la propiedad emparejada y el evento para el que se va a obtener la función del método.</span><span class="sxs-lookup"><span data-stu-id="bf5d5-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="bf5d5-108">[out] Un puntero a los marcadores de semántica asociada.</span><span class="sxs-lookup"><span data-stu-id="bf5d5-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="bf5d5-109">Este valor es una máscara de bits de la [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="bf5d5-109">This value is a bitmask from the [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf5d5-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf5d5-110">Remarks</span></span>  
 <span data-ttu-id="bf5d5-111">El [IMetaDataEmit:: DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) método establece marcas de semántica de un método.</span><span class="sxs-lookup"><span data-stu-id="bf5d5-111">The [IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf5d5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf5d5-112">Requirements</span></span>  
 <span data-ttu-id="bf5d5-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf5d5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf5d5-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bf5d5-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf5d5-115">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bf5d5-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf5d5-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf5d5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf5d5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf5d5-117">See Also</span></span>  
 [<span data-ttu-id="bf5d5-118">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf5d5-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="bf5d5-119">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf5d5-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

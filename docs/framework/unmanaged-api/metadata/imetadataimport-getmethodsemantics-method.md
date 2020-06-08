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
ms.openlocfilehash: 2cfb66203d8f2d69ea188f6913a5ef34dd74791e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503606"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="ce820-102">IMetaDataImport::GetMethodSemantics (Método)</span><span class="sxs-lookup"><span data-stu-id="ce820-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="ce820-103">Obtiene las marcas que indican la relación entre el método al que hace referencia el token de MethodDef especificado y la propiedad emparejada y el evento a los que hace referencia el token de EventProp especificado.</span><span class="sxs-lookup"><span data-stu-id="ce820-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce820-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce820-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce820-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce820-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="ce820-106">de Token de MethodDef que representa el método para el que se va a obtener la información de la función semántica.</span><span class="sxs-lookup"><span data-stu-id="ce820-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="ce820-107">de Token que representa la propiedad emparejada y el evento para los que se va a obtener el rol del método.</span><span class="sxs-lookup"><span data-stu-id="ce820-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="ce820-108">enuncia Puntero a las marcas de semántica asociadas.</span><span class="sxs-lookup"><span data-stu-id="ce820-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="ce820-109">Este valor es una máscara de máscara de la enumeración [cormethodsemanticsattr (](cormethodsemanticsattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ce820-109">This value is a bitmask from the [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce820-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ce820-110">Remarks</span></span>  
 <span data-ttu-id="ce820-111">El método [IMetaDataEmit::D efineproperty](imetadataemit-defineproperty-method.md) establece las marcas semánticas de un método.</span><span class="sxs-lookup"><span data-stu-id="ce820-111">The [IMetaDataEmit::DefineProperty](imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce820-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce820-112">Requirements</span></span>  
 <span data-ttu-id="ce820-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce820-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce820-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ce820-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce820-115">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ce820-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce820-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce820-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce820-117">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="ce820-117">See also</span></span>

- [<span data-ttu-id="ce820-118">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce820-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ce820-119">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce820-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

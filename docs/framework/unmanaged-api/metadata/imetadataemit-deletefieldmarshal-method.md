---
title: IMetaDataEmit::DeleteFieldMarshal (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteFieldMarshal
helpviewer_keywords:
- IMetaDataEmit::DeleteFieldMarshal method [.NET Framework metadata]
- DeleteFieldMarshal method [.NET Framework metadata]
ms.assetid: 7c75aef9-c742-4b33-a14b-56ff94b0f725
topic_type:
- apiref
ms.openlocfilehash: 652169c67461c1663c005dd014290c4cf2d993ba
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434366"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="604a5-102">IMetaDataEmit::DeleteFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="604a5-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="604a5-103">Destruye la firma de metadatos de serialización de PInvoke para el objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="604a5-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="604a5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="604a5-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="604a5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="604a5-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="604a5-106">de `mdFieldDef` o `mdParamDef` token que representa el campo o el parámetro para el que se va a eliminar la firma de metadatos de serialización.</span><span class="sxs-lookup"><span data-stu-id="604a5-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="604a5-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="604a5-107">Requirements</span></span>  
 <span data-ttu-id="604a5-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="604a5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="604a5-109">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="604a5-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="604a5-110">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="604a5-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="604a5-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="604a5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604a5-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="604a5-112">See also</span></span>

- [<span data-ttu-id="604a5-113">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="604a5-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="604a5-114">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="604a5-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

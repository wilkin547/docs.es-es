---
description: 'Más información acerca de: IMetaDataEmit::D método eleteFieldMarshal'
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
ms.openlocfilehash: 966f2ae20ad9ff4b9c1c9eec32974bc89aa76d13
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783968"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="08ffb-103">IMetaDataEmit::DeleteFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="08ffb-103">IMetaDataEmit::DeleteFieldMarshal Method</span></span>

<span data-ttu-id="08ffb-104">Destruye la firma de metadatos de serialización de PInvoke para el objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="08ffb-104">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08ffb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08ffb-105">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08ffb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="08ffb-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="08ffb-107">de Un `mdFieldDef` `mdParamDef` token o que representa el campo o el parámetro para el que se va a eliminar la firma de metadatos de serialización.</span><span class="sxs-lookup"><span data-stu-id="08ffb-107">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08ffb-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08ffb-108">Requirements</span></span>  

 <span data-ttu-id="08ffb-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08ffb-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08ffb-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="08ffb-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08ffb-111">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08ffb-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08ffb-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08ffb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08ffb-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="08ffb-113">See also</span></span>

- [<span data-ttu-id="08ffb-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="08ffb-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="08ffb-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="08ffb-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

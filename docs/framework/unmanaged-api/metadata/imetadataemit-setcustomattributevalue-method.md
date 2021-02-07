---
description: 'Más información sobre: IMetaDataEmit:: Setcustomattributevalue ((método)'
title: IMetaDataEmit::SetCustomAttributeValue (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
ms.openlocfilehash: 1eede765f27b371deb670242086d59b3d4320530
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706583"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="8b649-103">IMetaDataEmit::SetCustomAttributeValue (Método)</span><span class="sxs-lookup"><span data-stu-id="8b649-103">IMetaDataEmit::SetCustomAttributeValue Method</span></span>

<span data-ttu-id="8b649-104">Establece o actualiza el valor de un atributo personalizado definido por una llamada anterior a [IMetaDataEmit::D efinecustomattribute](imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="8b649-104">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b649-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b649-105">Syntax</span></span>  
  
```cpp  
HRESULT SetCustomAttributeValue (
    [in]  mdCustomAttribute       pcv,
    [in]  void const              *pCustomAttribute,
    [in]  ULONG                   cbCustomAttribute
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b649-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8b649-106">Parameters</span></span>  

 `pcv`  
 <span data-ttu-id="8b649-107">de Token del atributo personalizado de destino.</span><span class="sxs-lookup"><span data-stu-id="8b649-107">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="8b649-108">de Puntero a la matriz que contiene el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="8b649-108">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="8b649-109">de Tamaño, en bytes, del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="8b649-109">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b649-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b649-110">Requirements</span></span>  

 <span data-ttu-id="8b649-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b649-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b649-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8b649-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b649-113">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b649-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b649-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b649-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b649-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b649-115">See also</span></span>

- [<span data-ttu-id="8b649-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b649-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8b649-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b649-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

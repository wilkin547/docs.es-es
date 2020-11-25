---
title: IMetaDataEmit::DeleteToken (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteToken
helpviewer_keywords:
- DeleteToken method [.NET Framework metadata]
- IMetaDataEmit::DeleteToken method [.NET Framework metadata]
ms.assetid: a4926d0a-261b-46b1-9994-82633661a64b
topic_type:
- apiref
ms.openlocfilehash: eaa465855c9e933286bcdd189e62048510088ec7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722081"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="021d9-102">IMetaDataEmit::DeleteToken (Método)</span><span class="sxs-lookup"><span data-stu-id="021d9-102">IMetaDataEmit::DeleteToken Method</span></span>

<span data-ttu-id="021d9-103">Elimina el token especificado del ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="021d9-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="021d9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="021d9-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteToken (
    [in]  mdToken     tkObj
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="021d9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="021d9-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="021d9-106">de El token que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="021d9-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="021d9-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="021d9-107">Requirements</span></span>  

 <span data-ttu-id="021d9-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="021d9-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="021d9-109">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="021d9-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="021d9-110">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="021d9-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="021d9-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="021d9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="021d9-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="021d9-112">See also</span></span>

- [<span data-ttu-id="021d9-113">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="021d9-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="021d9-114">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="021d9-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

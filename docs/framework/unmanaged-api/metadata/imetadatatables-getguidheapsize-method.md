---
title: IMetaDataTables::GetGuidHeapSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuidHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type:
- apiref
ms.openlocfilehash: 1b524067ac72dfd3bd19475f11d4ec12a307731d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702438"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="fc8f0-102">IMetaDataTables::GetGuidHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="fc8f0-102">IMetaDataTables::GetGuidHeapSize Method</span></span>

<span data-ttu-id="fc8f0-103">Obtiene el tamaño, en bytes, del montón GUID.</span><span class="sxs-lookup"><span data-stu-id="fc8f0-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc8f0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc8f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc8f0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc8f0-105">Parameters</span></span>  

 `pcbGuids`  
 <span data-ttu-id="fc8f0-106">enuncia Puntero al tamaño, en bytes, del montón GUID.</span><span class="sxs-lookup"><span data-stu-id="fc8f0-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc8f0-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc8f0-107">Requirements</span></span>  

 <span data-ttu-id="fc8f0-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc8f0-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc8f0-109">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fc8f0-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fc8f0-110">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fc8f0-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fc8f0-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc8f0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc8f0-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc8f0-112">See also</span></span>

- [<span data-ttu-id="fc8f0-113">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc8f0-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="fc8f0-114">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc8f0-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

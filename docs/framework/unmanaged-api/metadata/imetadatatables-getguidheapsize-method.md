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
ms.openlocfilehash: cf455b3fb34d8eed78ffaadffad621062c2b9b22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443495"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="07dbe-102">IMetaDataTables::GetGuidHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="07dbe-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="07dbe-103">Gets the size, in bytes, of the GUID heap.</span><span class="sxs-lookup"><span data-stu-id="07dbe-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07dbe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07dbe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07dbe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="07dbe-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="07dbe-106">[out] A pointer to the size, in bytes, of the GUID heap.</span><span class="sxs-lookup"><span data-stu-id="07dbe-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07dbe-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07dbe-107">Requirements</span></span>  
 <span data-ttu-id="07dbe-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07dbe-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07dbe-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="07dbe-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07dbe-110">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="07dbe-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="07dbe-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07dbe-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07dbe-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="07dbe-112">See also</span></span>

- [<span data-ttu-id="07dbe-113">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="07dbe-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="07dbe-114">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="07dbe-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

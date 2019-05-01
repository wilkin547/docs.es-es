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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 812794bc76d475c516effdc950ca6a0b877494c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042424"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="2b4b9-102">IMetaDataTables::GetGuidHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="2b4b9-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="2b4b9-103">Obtiene el tamaño, en bytes, del montón GUID.</span><span class="sxs-lookup"><span data-stu-id="2b4b9-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b4b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b4b9-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b4b9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2b4b9-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="2b4b9-106">[out] Un puntero al tamaño, en bytes, del montón GUID.</span><span class="sxs-lookup"><span data-stu-id="2b4b9-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b4b9-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b4b9-107">Requirements</span></span>  
 <span data-ttu-id="2b4b9-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b4b9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b4b9-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="2b4b9-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2b4b9-110">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2b4b9-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2b4b9-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b4b9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b4b9-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b4b9-112">See also</span></span>

- [<span data-ttu-id="2b4b9-113">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b4b9-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="2b4b9-114">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b4b9-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

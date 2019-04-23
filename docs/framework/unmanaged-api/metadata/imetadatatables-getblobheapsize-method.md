---
title: IMetaDataTables::GetBlobHeapSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d22e61d28e0fbf06fa1cfe9e9ac18a534726f01d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076460"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="b51ad-102">IMetaDataTables::GetBlobHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="b51ad-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="b51ad-103">Obtiene el tamaño, en bytes, del montón de objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="b51ad-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b51ad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b51ad-104">Syntax</span></span>  
  
```  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="b51ad-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b51ad-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="b51ad-106">[out] Un puntero al tamaño, en bytes, del montón de objetos binarios.</span><span class="sxs-lookup"><span data-stu-id="b51ad-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b51ad-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b51ad-107">Requirements</span></span>  
 <span data-ttu-id="b51ad-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b51ad-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b51ad-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b51ad-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b51ad-110">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b51ad-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b51ad-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b51ad-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b51ad-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b51ad-112">See also</span></span>

- [<span data-ttu-id="b51ad-113">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b51ad-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="b51ad-114">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b51ad-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

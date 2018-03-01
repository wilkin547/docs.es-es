---
title: "IMetaDataTables::GetBlobHeapSize (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 176d924ec117365408a31f1bfc38901a7ef2cf65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="ea5ed-102">IMetaDataTables::GetBlobHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="ea5ed-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="ea5ed-103">Obtiene el tamaño, en bytes, del montón de objetos binarios grandes (BLOB).</span><span class="sxs-lookup"><span data-stu-id="ea5ed-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea5ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea5ed-104">Syntax</span></span>  
  
```  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea5ed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea5ed-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="ea5ed-106">[out] Un puntero al tamaño, en bytes, del montón de objetos binarios.</span><span class="sxs-lookup"><span data-stu-id="ea5ed-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea5ed-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea5ed-107">Requirements</span></span>  
 <span data-ttu-id="ea5ed-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea5ed-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea5ed-109">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ea5ed-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea5ed-110">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea5ed-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea5ed-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea5ed-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea5ed-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea5ed-112">See Also</span></span>  
 [<span data-ttu-id="ea5ed-113">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea5ed-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="ea5ed-114">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea5ed-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

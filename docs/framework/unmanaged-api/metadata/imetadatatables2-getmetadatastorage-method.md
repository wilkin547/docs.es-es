---
title: "IMetaDataTables2::GetMetaDataStorage (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables2.GetMetaDataStorage
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b00d03f8bd4a355d309f1a1266ca68f73647e0dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="395b8-102">IMetaDataTables2::GetMetaDataStorage (Método)</span><span class="sxs-lookup"><span data-stu-id="395b8-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>
<span data-ttu-id="395b8-103">Obtiene el tamaño y el contenido de los metadatos almacenados en la sección especificada.</span><span class="sxs-lookup"><span data-stu-id="395b8-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="395b8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="395b8-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="395b8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="395b8-105">Parameters</span></span>  
 `ppvMd`  
 <span data-ttu-id="395b8-106">[entrada, salida] Un puntero a una sección de metadatos.</span><span class="sxs-lookup"><span data-stu-id="395b8-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="395b8-107">[out] El tamaño de la secuencia de metadatos.</span><span class="sxs-lookup"><span data-stu-id="395b8-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="395b8-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="395b8-108">Requirements</span></span>  
 <span data-ttu-id="395b8-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="395b8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="395b8-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="395b8-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="395b8-111">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="395b8-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="395b8-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="395b8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="395b8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="395b8-113">See Also</span></span>  
 [<span data-ttu-id="395b8-114">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="395b8-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 [<span data-ttu-id="395b8-115">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="395b8-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)

---
title: "IMetaDataEmit2::GetDeltaSaveSize (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.GetDeltaSaveSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0a1b3aec06d6593257c82d6e3c08d6a8e2430691
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="6a885-102">IMetaDataEmit2::GetDeltaSaveSize (Método)</span><span class="sxs-lookup"><span data-stu-id="6a885-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="6a885-103">Obtiene un valor que indica cualquier cambio de tamaño de los metadatos que es el resultado de la sesión actual de editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="6a885-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a885-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a885-104">Syntax</span></span>  
  
```  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a885-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6a885-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="6a885-106">[in] Uno de los [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) valores, que indica el nivel de precisión deseado.</span><span class="sxs-lookup"><span data-stu-id="6a885-106">[in] One of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="6a885-107">Para la versión 2.0 de .NET Framework, se omite este parámetro.</span><span class="sxs-lookup"><span data-stu-id="6a885-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="6a885-108">[out] El cambio en el tamaño de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="6a885-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a885-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a885-109">Requirements</span></span>  
 <span data-ttu-id="6a885-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a885-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a885-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6a885-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a885-112">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6a885-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6a885-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a885-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a885-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a885-114">See Also</span></span>  
 [<span data-ttu-id="6a885-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a885-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="6a885-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a885-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)

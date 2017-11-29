---
title: "IHostFilter::MarkToken (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostFilter.MarkToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9556880ad534f5c82d8d0e874129876478e2e63f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="64d49-102">IHostFilter::MarkToken (Método)</span><span class="sxs-lookup"><span data-stu-id="64d49-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="64d49-103">Indica que se procesará el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="64d49-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64d49-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64d49-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64d49-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="64d49-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="64d49-106">[in] El token de metadatos para procesarse.</span><span class="sxs-lookup"><span data-stu-id="64d49-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64d49-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64d49-107">Remarks</span></span>  
 <span data-ttu-id="64d49-108">Normalmente, deseará que un token que se puede procesar si se encuentra en el ámbito de metadatos.</span><span class="sxs-lookup"><span data-stu-id="64d49-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="64d49-109">El `MarkToken` método se pasa al motor de metadatos a través de la [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="64d49-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64d49-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64d49-110">Requirements</span></span>  
 <span data-ttu-id="64d49-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64d49-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64d49-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="64d49-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64d49-113">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="64d49-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="64d49-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64d49-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d49-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="64d49-115">See Also</span></span>  
 [<span data-ttu-id="64d49-116">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="64d49-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="64d49-117">IHostFilter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="64d49-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)

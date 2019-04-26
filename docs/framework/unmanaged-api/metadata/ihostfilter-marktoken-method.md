---
title: IHostFilter::MarkToken (Método)
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3214a21dda27fda01054e96400997b15d11f71b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905429"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="a9907-102">IHostFilter::MarkToken (Método)</span><span class="sxs-lookup"><span data-stu-id="a9907-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="a9907-103">Indica que se procesará el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="a9907-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9907-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9907-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9907-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9907-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="a9907-106">[in] El token de metadatos que se va a procesar.</span><span class="sxs-lookup"><span data-stu-id="a9907-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9907-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9907-107">Remarks</span></span>  
 <span data-ttu-id="a9907-108">Normalmente, desea que un token en procesarse si se encuentra en el ámbito de metadatos.</span><span class="sxs-lookup"><span data-stu-id="a9907-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="a9907-109">El `MarkToken` método se pasa al motor de metadatos a través de la [SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="a9907-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9907-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9907-110">Requirements</span></span>  
 <span data-ttu-id="a9907-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9907-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9907-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="a9907-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9907-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9907-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9907-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9907-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9907-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9907-115">See also</span></span>

- [<span data-ttu-id="a9907-116">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="a9907-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="a9907-117">IHostFilter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9907-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)

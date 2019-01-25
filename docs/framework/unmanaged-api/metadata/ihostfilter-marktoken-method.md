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
ms.openlocfilehash: a4a1761f088732cf19d55f42d66288bb281885f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589456"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="7e9aa-102">IHostFilter::MarkToken (Método)</span><span class="sxs-lookup"><span data-stu-id="7e9aa-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="7e9aa-103">Indica que se procesará el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="7e9aa-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e9aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e9aa-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e9aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e9aa-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="7e9aa-106">[in] El token de metadatos que se va a procesar.</span><span class="sxs-lookup"><span data-stu-id="7e9aa-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e9aa-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7e9aa-107">Remarks</span></span>  
 <span data-ttu-id="7e9aa-108">Normalmente, desea que un token en procesarse si se encuentra en el ámbito de metadatos.</span><span class="sxs-lookup"><span data-stu-id="7e9aa-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="7e9aa-109">El `MarkToken` método se pasa al motor de metadatos a través de la [SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="7e9aa-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e9aa-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e9aa-110">Requirements</span></span>  
 <span data-ttu-id="7e9aa-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e9aa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e9aa-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="7e9aa-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e9aa-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e9aa-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7e9aa-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e9aa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e9aa-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e9aa-115">See also</span></span>
- [<span data-ttu-id="7e9aa-116">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="7e9aa-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="7e9aa-117">IHostFilter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e9aa-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)

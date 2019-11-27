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
ms.openlocfilehash: 6f8df824ed36b7793d5f07e5b5cf51f65f9c8e24
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432243"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="92e56-102">IHostFilter::MarkToken (Método)</span><span class="sxs-lookup"><span data-stu-id="92e56-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="92e56-103">Indica que se procesará el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="92e56-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92e56-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92e56-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92e56-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="92e56-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="92e56-106">de Token de metadatos que se va a procesar.</span><span class="sxs-lookup"><span data-stu-id="92e56-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92e56-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="92e56-107">Remarks</span></span>  
 <span data-ttu-id="92e56-108">Normalmente, desea que se procese un token si está en el ámbito de metadatos.</span><span class="sxs-lookup"><span data-stu-id="92e56-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="92e56-109">El método `MarkToken` se pasa al motor de metadatos a través del método [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) .</span><span class="sxs-lookup"><span data-stu-id="92e56-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92e56-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92e56-110">Requirements</span></span>  
 <span data-ttu-id="92e56-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92e56-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92e56-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="92e56-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92e56-113">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="92e56-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="92e56-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92e56-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92e56-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="92e56-115">See also</span></span>

- [<span data-ttu-id="92e56-116">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="92e56-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="92e56-117">IHostFilter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="92e56-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)

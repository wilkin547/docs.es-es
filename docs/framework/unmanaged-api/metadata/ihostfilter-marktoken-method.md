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
ms.openlocfilehash: b4db3b115517f0a146aeab469f091008d31efc86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718233"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="9e68c-102">IHostFilter::MarkToken (Método)</span><span class="sxs-lookup"><span data-stu-id="9e68c-102">IHostFilter::MarkToken Method</span></span>

<span data-ttu-id="9e68c-103">Indica que se procesará el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="9e68c-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e68c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e68c-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e68c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9e68c-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="9e68c-106">de Token de metadatos que se va a procesar.</span><span class="sxs-lookup"><span data-stu-id="9e68c-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e68c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9e68c-107">Remarks</span></span>  

 <span data-ttu-id="9e68c-108">Normalmente, desea que se procese un token si está en el ámbito de metadatos.</span><span class="sxs-lookup"><span data-stu-id="9e68c-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="9e68c-109">El `MarkToken` método se pasa al motor de metadatos mediante el método [IMetaDataEmit:: SetHandler](imetadataemit-sethandler-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9e68c-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e68c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e68c-110">Requirements</span></span>  

 <span data-ttu-id="9e68c-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e68c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e68c-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9e68c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9e68c-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9e68c-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9e68c-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e68c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e68c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9e68c-115">See also</span></span>

- [<span data-ttu-id="9e68c-116">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="9e68c-116">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="9e68c-117">IHostFilter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9e68c-117">IHostFilter Interface</span></span>](ihostfilter-interface.md)

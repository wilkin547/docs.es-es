---
description: 'Más información sobre: Ihostfilter (:: MarkToken ((método)'
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
ms.openlocfilehash: c8f5ecdef56b77e1b0031a93d6d8f7de79de4c3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784189"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="77f2d-103">IHostFilter::MarkToken (Método)</span><span class="sxs-lookup"><span data-stu-id="77f2d-103">IHostFilter::MarkToken Method</span></span>

<span data-ttu-id="77f2d-104">Indica que se procesará el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="77f2d-104">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77f2d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77f2d-105">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77f2d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="77f2d-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="77f2d-107">de Token de metadatos que se va a procesar.</span><span class="sxs-lookup"><span data-stu-id="77f2d-107">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77f2d-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="77f2d-108">Remarks</span></span>  

 <span data-ttu-id="77f2d-109">Normalmente, desea que se procese un token si está en el ámbito de metadatos.</span><span class="sxs-lookup"><span data-stu-id="77f2d-109">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="77f2d-110">El `MarkToken` método se pasa al motor de metadatos mediante el método [IMetaDataEmit:: SetHandler](imetadataemit-sethandler-method.md) .</span><span class="sxs-lookup"><span data-stu-id="77f2d-110">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77f2d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77f2d-111">Requirements</span></span>  

 <span data-ttu-id="77f2d-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77f2d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77f2d-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="77f2d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77f2d-114">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="77f2d-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="77f2d-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77f2d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77f2d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="77f2d-116">See also</span></span>

- [<span data-ttu-id="77f2d-117">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="77f2d-117">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="77f2d-118">IHostFilter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="77f2d-118">IHostFilter Interface</span></span>](ihostfilter-interface.md)

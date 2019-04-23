---
title: IMetaDataFilter (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4196ff2cb2d4ebc401076f603a8a7fdc9b9c76ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143798"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="f419a-102">IMetaDataFilter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f419a-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="f419a-103">Proporciona métodos para marcar y filtrar los tokens de metadatos para evitar repetir acciones que ya se han realizado.</span><span class="sxs-lookup"><span data-stu-id="f419a-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f419a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f419a-104">Methods</span></span>  
  
|<span data-ttu-id="f419a-105">Método</span><span class="sxs-lookup"><span data-stu-id="f419a-105">Method</span></span>|<span data-ttu-id="f419a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f419a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f419a-107">IsTokenMarked (método)</span><span class="sxs-lookup"><span data-stu-id="f419a-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="f419a-108">Obtiene un valor que indica si se ha procesado el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="f419a-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="f419a-109">MarkToken (método)</span><span class="sxs-lookup"><span data-stu-id="f419a-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="f419a-110">Establece un valor que indica que se ha procesado el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="f419a-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="f419a-111">UnmarkAll (método)</span><span class="sxs-lookup"><span data-stu-id="f419a-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="f419a-112">Quita las marcas de procesamiento de todos los tokens en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="f419a-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f419a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f419a-113">Requirements</span></span>  
 <span data-ttu-id="f419a-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f419a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f419a-115">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="f419a-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f419a-116">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f419a-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f419a-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f419a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f419a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f419a-118">See also</span></span>

- [<span data-ttu-id="f419a-119">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="f419a-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

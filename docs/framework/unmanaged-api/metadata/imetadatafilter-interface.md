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
ms.openlocfilehash: ad77aba02c819749794534ca2ecd478661bc363f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444986"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="f9301-102">IMetaDataFilter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9301-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="f9301-103">Proporciona métodos para marcar y filtrar los tokens de metadatos para evitar repetir acciones que ya se han realizado.</span><span class="sxs-lookup"><span data-stu-id="f9301-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f9301-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f9301-104">Methods</span></span>  
  
|<span data-ttu-id="f9301-105">Método</span><span class="sxs-lookup"><span data-stu-id="f9301-105">Method</span></span>|<span data-ttu-id="f9301-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9301-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f9301-107">IsTokenMarked (método)</span><span class="sxs-lookup"><span data-stu-id="f9301-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="f9301-108">Obtiene un valor que indica si se ha procesado el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="f9301-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="f9301-109">MarkToken (método)</span><span class="sxs-lookup"><span data-stu-id="f9301-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="f9301-110">Establece un valor que indica que se ha procesado el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="f9301-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="f9301-111">UnmarkAll (método)</span><span class="sxs-lookup"><span data-stu-id="f9301-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="f9301-112">Quita las marcas de procesamiento de todos los tokens en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="f9301-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f9301-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f9301-113">Requirements</span></span>  
 <span data-ttu-id="f9301-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9301-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9301-115">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f9301-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f9301-116">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f9301-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f9301-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9301-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9301-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9301-118">See Also</span></span>  
 [<span data-ttu-id="f9301-119">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="f9301-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

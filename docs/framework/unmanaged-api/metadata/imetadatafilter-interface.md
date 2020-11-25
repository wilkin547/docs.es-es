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
ms.openlocfilehash: 2c22e45ca3d33b0a81ff0ecd90bf7574c45676bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701853"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="802e7-102">IMetaDataFilter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="802e7-102">IMetaDataFilter Interface</span></span>

<span data-ttu-id="802e7-103">Proporciona métodos para marcar y filtrar los tokens de metadatos para evitar repetir acciones que ya se han realizado.</span><span class="sxs-lookup"><span data-stu-id="802e7-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="802e7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="802e7-104">Methods</span></span>  
  
|<span data-ttu-id="802e7-105">Método</span><span class="sxs-lookup"><span data-stu-id="802e7-105">Method</span></span>|<span data-ttu-id="802e7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="802e7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="802e7-107">Método IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="802e7-107">IsTokenMarked Method</span></span>](imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="802e7-108">Obtiene un valor que indica si se ha procesado el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="802e7-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="802e7-109">MarkToken (Método)</span><span class="sxs-lookup"><span data-stu-id="802e7-109">MarkToken Method</span></span>](imetadatafilter-marktoken-method.md)|<span data-ttu-id="802e7-110">Establece un valor que indica que se ha procesado el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="802e7-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="802e7-111">Método UnmarkAll</span><span class="sxs-lookup"><span data-stu-id="802e7-111">UnmarkAll Method</span></span>](imetadatafilter-unmarkall-method.md)|<span data-ttu-id="802e7-112">Quita las marcas de procesamiento de todos los tokens en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="802e7-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="802e7-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="802e7-113">Requirements</span></span>  

 <span data-ttu-id="802e7-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="802e7-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="802e7-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="802e7-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="802e7-116">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="802e7-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="802e7-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="802e7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="802e7-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="802e7-118">See also</span></span>

- [<span data-ttu-id="802e7-119">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="802e7-119">Metadata Interfaces</span></span>](metadata-interfaces.md)

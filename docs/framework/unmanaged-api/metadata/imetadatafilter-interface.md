---
description: 'Más información acerca de: interfaz IMetaDataFilter'
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
ms.openlocfilehash: c994574207ccb26a5cb317e1673145a41f0d837d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677930"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="b06e4-103">IMetaDataFilter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b06e4-103">IMetaDataFilter Interface</span></span>

<span data-ttu-id="b06e4-104">Proporciona métodos para marcar y filtrar los tokens de metadatos para evitar repetir acciones que ya se han realizado.</span><span class="sxs-lookup"><span data-stu-id="b06e4-104">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b06e4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b06e4-105">Methods</span></span>  
  
|<span data-ttu-id="b06e4-106">Método</span><span class="sxs-lookup"><span data-stu-id="b06e4-106">Method</span></span>|<span data-ttu-id="b06e4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b06e4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b06e4-108">Método IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="b06e4-108">IsTokenMarked Method</span></span>](imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="b06e4-109">Obtiene un valor que indica si se ha procesado el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="b06e4-109">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="b06e4-110">MarkToken (Método)</span><span class="sxs-lookup"><span data-stu-id="b06e4-110">MarkToken Method</span></span>](imetadatafilter-marktoken-method.md)|<span data-ttu-id="b06e4-111">Establece un valor que indica que se ha procesado el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="b06e4-111">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="b06e4-112">Método UnmarkAll</span><span class="sxs-lookup"><span data-stu-id="b06e4-112">UnmarkAll Method</span></span>](imetadatafilter-unmarkall-method.md)|<span data-ttu-id="b06e4-113">Quita las marcas de procesamiento de todos los tokens en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="b06e4-113">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b06e4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b06e4-114">Requirements</span></span>  

 <span data-ttu-id="b06e4-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b06e4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b06e4-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b06e4-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b06e4-117">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b06e4-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b06e4-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b06e4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b06e4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b06e4-119">See also</span></span>

- [<span data-ttu-id="b06e4-120">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="b06e4-120">Metadata Interfaces</span></span>](metadata-interfaces.md)

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
ms.openlocfilehash: 821936d20a421739e8eb3d5df228888df7f022e3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503801"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="8ea42-102">IMetaDataFilter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8ea42-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="8ea42-103">Proporciona métodos para marcar y filtrar los tokens de metadatos para evitar repetir acciones que ya se han realizado.</span><span class="sxs-lookup"><span data-stu-id="8ea42-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8ea42-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8ea42-104">Methods</span></span>  
  
|<span data-ttu-id="8ea42-105">Método</span><span class="sxs-lookup"><span data-stu-id="8ea42-105">Method</span></span>|<span data-ttu-id="8ea42-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ea42-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8ea42-107">Método IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="8ea42-107">IsTokenMarked Method</span></span>](imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="8ea42-108">Obtiene un valor que indica si se ha procesado el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="8ea42-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="8ea42-109">MarkToken (Método)</span><span class="sxs-lookup"><span data-stu-id="8ea42-109">MarkToken Method</span></span>](imetadatafilter-marktoken-method.md)|<span data-ttu-id="8ea42-110">Establece un valor que indica que se ha procesado el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="8ea42-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="8ea42-111">Método UnmarkAll</span><span class="sxs-lookup"><span data-stu-id="8ea42-111">UnmarkAll Method</span></span>](imetadatafilter-unmarkall-method.md)|<span data-ttu-id="8ea42-112">Quita las marcas de procesamiento de todos los tokens en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="8ea42-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8ea42-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ea42-113">Requirements</span></span>  
 <span data-ttu-id="8ea42-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ea42-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ea42-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8ea42-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ea42-116">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8ea42-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ea42-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ea42-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ea42-118">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="8ea42-118">See also</span></span>

- [<span data-ttu-id="8ea42-119">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="8ea42-119">Metadata Interfaces</span></span>](metadata-interfaces.md)

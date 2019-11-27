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
ms.openlocfilehash: e8b15f478eb3b94b7cdcab3b69d54e7cc99be13b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440166"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="ed9fb-102">IMetaDataFilter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed9fb-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="ed9fb-103">Proporciona métodos para marcar y filtrar los tokens de metadatos para evitar repetir acciones que ya se han realizado.</span><span class="sxs-lookup"><span data-stu-id="ed9fb-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed9fb-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ed9fb-104">Methods</span></span>  
  
|<span data-ttu-id="ed9fb-105">Método</span><span class="sxs-lookup"><span data-stu-id="ed9fb-105">Method</span></span>|<span data-ttu-id="ed9fb-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed9fb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed9fb-107">IsTokenMarked (método)</span><span class="sxs-lookup"><span data-stu-id="ed9fb-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="ed9fb-108">Obtiene un valor que indica si se ha procesado el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="ed9fb-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="ed9fb-109">MarkToken (método)</span><span class="sxs-lookup"><span data-stu-id="ed9fb-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="ed9fb-110">Establece un valor que indica que se ha procesado el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="ed9fb-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="ed9fb-111">UnmarkAll (método)</span><span class="sxs-lookup"><span data-stu-id="ed9fb-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="ed9fb-112">Quita las marcas de procesamiento de todos los tokens en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="ed9fb-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ed9fb-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed9fb-113">Requirements</span></span>  
 <span data-ttu-id="ed9fb-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed9fb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed9fb-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ed9fb-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed9fb-116">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ed9fb-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed9fb-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed9fb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed9fb-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed9fb-118">See also</span></span>

- [<span data-ttu-id="ed9fb-119">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="ed9fb-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

---
title: IMetaDataEmit2 (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
ms.openlocfilehash: 7ceae6f7713ab0eb1feff550838325df0ea52de2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447915"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="2e221-102">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e221-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="2e221-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span><span class="sxs-lookup"><span data-stu-id="2e221-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2e221-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2e221-104">Methods</span></span>  
  
|<span data-ttu-id="2e221-105">Método</span><span class="sxs-lookup"><span data-stu-id="2e221-105">Method</span></span>|<span data-ttu-id="2e221-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e221-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e221-107">DefineGenericParam (método)</span><span class="sxs-lookup"><span data-stu-id="2e221-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="2e221-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span><span class="sxs-lookup"><span data-stu-id="2e221-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="2e221-109">DefineMethodSpec (método)</span><span class="sxs-lookup"><span data-stu-id="2e221-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="2e221-110">Creates a generic instance of a method, and gets a token to the definition.</span><span class="sxs-lookup"><span data-stu-id="2e221-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="2e221-111">GetDeltaSaveSize (método)</span><span class="sxs-lookup"><span data-stu-id="2e221-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="2e221-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span><span class="sxs-lookup"><span data-stu-id="2e221-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="2e221-113">ResetENCLog (método)</span><span class="sxs-lookup"><span data-stu-id="2e221-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="2e221-114">Resets the edit-and-continue log and starts a new session.</span><span class="sxs-lookup"><span data-stu-id="2e221-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="2e221-115">SaveDelta (método)</span><span class="sxs-lookup"><span data-stu-id="2e221-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="2e221-116">Saves changes from the current edit-and-continue session to the specified file.</span><span class="sxs-lookup"><span data-stu-id="2e221-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="2e221-117">SaveDeltaToMemory (método)</span><span class="sxs-lookup"><span data-stu-id="2e221-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="2e221-118">Saves changes from the current edit-and-continue session to memory.</span><span class="sxs-lookup"><span data-stu-id="2e221-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="2e221-119">SaveDeltaToStream (método)</span><span class="sxs-lookup"><span data-stu-id="2e221-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="2e221-120">Saves changes from the current edit-and-continue session to the specified stream.</span><span class="sxs-lookup"><span data-stu-id="2e221-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="2e221-121">SetGenericParamProps (método)</span><span class="sxs-lookup"><span data-stu-id="2e221-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="2e221-122">Sets property values for the generic parameter definition referenced by the specified token.</span><span class="sxs-lookup"><span data-stu-id="2e221-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e221-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e221-123">Requirements</span></span>  
 <span data-ttu-id="2e221-124">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e221-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e221-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2e221-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2e221-126">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2e221-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2e221-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e221-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e221-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e221-128">See also</span></span>

- [<span data-ttu-id="2e221-129">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="2e221-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="2e221-130">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e221-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)

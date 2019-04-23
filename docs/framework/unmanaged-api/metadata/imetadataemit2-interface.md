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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 87b5b60d75d5d28e100ec75192d0cacf51765927
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200199"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="59672-102">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="59672-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="59672-103">Extiende la [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaz principalmente para proporcionar la capacidad de trabajar con tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="59672-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="59672-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="59672-104">Methods</span></span>  
  
|<span data-ttu-id="59672-105">Método</span><span class="sxs-lookup"><span data-stu-id="59672-105">Method</span></span>|<span data-ttu-id="59672-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="59672-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="59672-107">DefineGenericParam (método)</span><span class="sxs-lookup"><span data-stu-id="59672-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="59672-108">Crea una definición para un parámetro de tipo genérico y obtiene un token para ese parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="59672-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="59672-109">DefineMethodSpec (método)</span><span class="sxs-lookup"><span data-stu-id="59672-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="59672-110">Crea una instancia de un método genérica y obtiene un token a la definición.</span><span class="sxs-lookup"><span data-stu-id="59672-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="59672-111">GetDeltaSaveSize (método)</span><span class="sxs-lookup"><span data-stu-id="59672-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="59672-112">Obtiene un valor que indica la diferencia de tamaño de los datos que es necesaria para expresar los cambios para la sesión actual de editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="59672-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="59672-113">ResetENCLog (método)</span><span class="sxs-lookup"><span data-stu-id="59672-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="59672-114">Restablece el registro de editar y continuar e inicia una nueva sesión.</span><span class="sxs-lookup"><span data-stu-id="59672-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="59672-115">SaveDelta (método)</span><span class="sxs-lookup"><span data-stu-id="59672-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="59672-116">Guarda los cambios de la sesión actual de editar y continuar en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="59672-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="59672-117">SaveDeltaToMemory (método)</span><span class="sxs-lookup"><span data-stu-id="59672-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="59672-118">Guarda los cambios de la sesión actual de editar y continuar en la memoria.</span><span class="sxs-lookup"><span data-stu-id="59672-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="59672-119">SaveDeltaToStream (método)</span><span class="sxs-lookup"><span data-stu-id="59672-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="59672-120">Guarda los cambios de la sesión actual de editar y continuar en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="59672-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="59672-121">SetGenericParamProps (método)</span><span class="sxs-lookup"><span data-stu-id="59672-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="59672-122">Establece los valores de propiedad de la definición de parámetro genérico al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="59672-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="59672-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59672-123">Requirements</span></span>  
 <span data-ttu-id="59672-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59672-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59672-125">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="59672-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="59672-126">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="59672-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="59672-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59672-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59672-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="59672-128">See also</span></span>

- [<span data-ttu-id="59672-129">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="59672-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="59672-130">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="59672-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)

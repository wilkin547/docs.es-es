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
# <a name="imetadataemit2-interface"></a><span data-ttu-id="7688b-102">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7688b-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="7688b-103">Extiende la interfaz [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) principalmente para proporcionar la capacidad de trabajar con tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="7688b-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7688b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7688b-104">Methods</span></span>  
  
|<span data-ttu-id="7688b-105">Método</span><span class="sxs-lookup"><span data-stu-id="7688b-105">Method</span></span>|<span data-ttu-id="7688b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7688b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7688b-107">DefineGenericParam (método)</span><span class="sxs-lookup"><span data-stu-id="7688b-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="7688b-108">Crea una definición para un parámetro de tipo genérico y obtiene un token para ese parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="7688b-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="7688b-109">DefineMethodSpec (método)</span><span class="sxs-lookup"><span data-stu-id="7688b-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="7688b-110">Crea una instancia genérica de un método y obtiene un token para la definición.</span><span class="sxs-lookup"><span data-stu-id="7688b-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="7688b-111">GetDeltaSaveSize (método)</span><span class="sxs-lookup"><span data-stu-id="7688b-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="7688b-112">Obtiene un valor que indica la diferencia de tamaño de los datos necesarios para expresar los cambios de la sesión de edición y continuación actual.</span><span class="sxs-lookup"><span data-stu-id="7688b-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="7688b-113">ResetENCLog (método)</span><span class="sxs-lookup"><span data-stu-id="7688b-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="7688b-114">Restablece el registro de edición y continuación e inicia una nueva sesión.</span><span class="sxs-lookup"><span data-stu-id="7688b-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="7688b-115">SaveDelta (método)</span><span class="sxs-lookup"><span data-stu-id="7688b-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="7688b-116">Guarda los cambios de la sesión de edición y continuación actual en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="7688b-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="7688b-117">SaveDeltaToMemory (método)</span><span class="sxs-lookup"><span data-stu-id="7688b-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="7688b-118">Guarda los cambios de la sesión de edición y continuación actual en la memoria.</span><span class="sxs-lookup"><span data-stu-id="7688b-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="7688b-119">SaveDeltaToStream (método)</span><span class="sxs-lookup"><span data-stu-id="7688b-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="7688b-120">Guarda los cambios de la sesión de edición y continuación actual en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="7688b-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="7688b-121">SetGenericParamProps (método)</span><span class="sxs-lookup"><span data-stu-id="7688b-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="7688b-122">Establece los valores de propiedad para la definición de parámetro genérico a la que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="7688b-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7688b-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7688b-123">Requirements</span></span>  
 <span data-ttu-id="7688b-124">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7688b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7688b-125">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7688b-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7688b-126">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7688b-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7688b-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7688b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7688b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="7688b-128">See also</span></span>

- [<span data-ttu-id="7688b-129">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="7688b-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="7688b-130">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7688b-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)

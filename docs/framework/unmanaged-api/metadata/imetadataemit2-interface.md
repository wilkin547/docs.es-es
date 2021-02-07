---
description: 'Más información acerca de: interfaz IMetaDataEmit2'
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
ms.openlocfilehash: db1880d64bf3b1e9084d6745251c174788a4afe7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745689"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="a8669-103">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8669-103">IMetaDataEmit2 Interface</span></span>

<span data-ttu-id="a8669-104">Extiende la interfaz [IMetaDataEmit](imetadataemit-interface.md) principalmente para proporcionar la capacidad de trabajar con tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="a8669-104">Extends the [IMetaDataEmit](imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8669-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a8669-105">Methods</span></span>  
  
|<span data-ttu-id="a8669-106">Método</span><span class="sxs-lookup"><span data-stu-id="a8669-106">Method</span></span>|<span data-ttu-id="a8669-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8669-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8669-108">Método DefineGenericParam</span><span class="sxs-lookup"><span data-stu-id="a8669-108">DefineGenericParam Method</span></span>](imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="a8669-109">Crea una definición para un parámetro de tipo genérico y obtiene un token para ese parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="a8669-109">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="a8669-110">Método DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="a8669-110">DefineMethodSpec Method</span></span>](imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="a8669-111">Crea una instancia genérica de un método y obtiene un token para la definición.</span><span class="sxs-lookup"><span data-stu-id="a8669-111">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="a8669-112">Método GetDeltaSaveSize</span><span class="sxs-lookup"><span data-stu-id="a8669-112">GetDeltaSaveSize Method</span></span>](imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="a8669-113">Obtiene un valor que indica la diferencia de tamaño de los datos necesarios para expresar los cambios de la sesión de edición y continuación actual.</span><span class="sxs-lookup"><span data-stu-id="a8669-113">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="a8669-114">Método ResetENCLog</span><span class="sxs-lookup"><span data-stu-id="a8669-114">ResetENCLog Method</span></span>](imetadataemit2-resetenclog-method.md)|<span data-ttu-id="a8669-115">Restablece el registro de edición y continuación e inicia una nueva sesión.</span><span class="sxs-lookup"><span data-stu-id="a8669-115">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="a8669-116">Método SaveDelta</span><span class="sxs-lookup"><span data-stu-id="a8669-116">SaveDelta Method</span></span>](imetadataemit2-savedelta-method.md)|<span data-ttu-id="a8669-117">Guarda los cambios de la sesión de edición y continuación actual en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="a8669-117">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="a8669-118">Método SaveDeltaToMemory</span><span class="sxs-lookup"><span data-stu-id="a8669-118">SaveDeltaToMemory Method</span></span>](imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="a8669-119">Guarda los cambios de la sesión de edición y continuación actual en la memoria.</span><span class="sxs-lookup"><span data-stu-id="a8669-119">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="a8669-120">Método SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="a8669-120">SaveDeltaToStream Method</span></span>](imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="a8669-121">Guarda los cambios de la sesión de edición y continuación actual en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="a8669-121">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="a8669-122">Método SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="a8669-122">SetGenericParamProps Method</span></span>](imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="a8669-123">Establece los valores de propiedad para la definición de parámetro genérico a la que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="a8669-123">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8669-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8669-124">Requirements</span></span>  

 <span data-ttu-id="a8669-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8669-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8669-126">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a8669-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8669-127">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8669-127">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8669-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8669-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8669-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8669-129">See also</span></span>

- [<span data-ttu-id="a8669-130">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="a8669-130">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="a8669-131">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8669-131">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)

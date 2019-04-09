---
title: IMetaDataDispenserEx (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx
helpviewer_keywords:
- IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96475086b1244ae75ed692dd10cb693af0be9af7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186958"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="b16b6-102">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b16b6-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="b16b6-103">Extiende la [IMetaDataDispenser (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interfaz para proporcionar la capacidad para controlar el funcionamiento de las API de metadatos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="b16b6-103">Extends the [IMetaDataDispenser Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b16b6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b16b6-104">Methods</span></span>  
  
|<span data-ttu-id="b16b6-105">Método</span><span class="sxs-lookup"><span data-stu-id="b16b6-105">Method</span></span>|<span data-ttu-id="b16b6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b16b6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b16b6-107">Método FindAssembly</span><span class="sxs-lookup"><span data-stu-id="b16b6-107">FindAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="b16b6-108">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="b16b6-108">This method is not implemented.</span></span> <span data-ttu-id="b16b6-109">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="b16b6-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="b16b6-110">Método FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="b16b6-110">FindAssemblyModule Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="b16b6-111">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="b16b6-111">This method is not implemented.</span></span> <span data-ttu-id="b16b6-112">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="b16b6-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="b16b6-113">Método GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="b16b6-113">GetCORSystemDirectory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="b16b6-114">Obtiene el directorio que contiene el actual common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b16b6-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="b16b6-115">Este método es compatible solo para su uso con los depuradores fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="b16b6-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="b16b6-116">Si se llama desde otro componente, devolverá E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="b16b6-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="b16b6-117">Método GetOption</span><span class="sxs-lookup"><span data-stu-id="b16b6-117">GetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|<span data-ttu-id="b16b6-118">Obtiene el valor de la opción especificada para el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="b16b6-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="b16b6-119">La opción controla cómo se controlan las llamadas al ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="b16b6-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="b16b6-120">Método OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="b16b6-120">OpenScopeOnITypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="b16b6-121">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="b16b6-121">This method is not implemented.</span></span> <span data-ttu-id="b16b6-122">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="b16b6-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="b16b6-123">Método SetOption</span><span class="sxs-lookup"><span data-stu-id="b16b6-123">SetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|<span data-ttu-id="b16b6-124">Establece la opción especificada en un valor especificado para el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="b16b6-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="b16b6-125">La opción controla cómo se controlan las llamadas al ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="b16b6-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b16b6-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b16b6-126">Requirements</span></span>  
 <span data-ttu-id="b16b6-127">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b16b6-127">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b16b6-128">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b16b6-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b16b6-129">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b16b6-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="b16b6-130">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b16b6-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b16b6-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="b16b6-131">See also</span></span>

- [<span data-ttu-id="b16b6-132">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="b16b6-132">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="b16b6-133">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b16b6-133">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="b16b6-134">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b16b6-134">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b16b6-135">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b16b6-135">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)

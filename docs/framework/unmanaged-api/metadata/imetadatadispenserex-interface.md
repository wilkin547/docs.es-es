---
description: 'Más información acerca de: interfaz IMetaDataDispenserEx'
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
ms.openlocfilehash: d940ac20eaad4b930ab17fb2d194d3b03bd4cf3c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753541"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="37b4b-103">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37b4b-103">IMetaDataDispenserEx Interface</span></span>

<span data-ttu-id="37b4b-104">Extiende la interfaz [IMetaDataDispenser interface](imetadatadispenser-interface.md) para proporcionar la capacidad de controlar el funcionamiento de las API de metadatos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="37b4b-104">Extends the [IMetaDataDispenser Interface](imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="37b4b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="37b4b-105">Methods</span></span>  
  
|<span data-ttu-id="37b4b-106">Método</span><span class="sxs-lookup"><span data-stu-id="37b4b-106">Method</span></span>|<span data-ttu-id="37b4b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="37b4b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="37b4b-108">Método FindAssembly</span><span class="sxs-lookup"><span data-stu-id="37b4b-108">FindAssembly Method</span></span>](imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="37b4b-109">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="37b4b-109">This method is not implemented.</span></span> <span data-ttu-id="37b4b-110">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="37b4b-110">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="37b4b-111">Método FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="37b4b-111">FindAssemblyModule Method</span></span>](imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="37b4b-112">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="37b4b-112">This method is not implemented.</span></span> <span data-ttu-id="37b4b-113">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="37b4b-113">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="37b4b-114">Método GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="37b4b-114">GetCORSystemDirectory Method</span></span>](imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="37b4b-115">Obtiene el directorio que contiene el Common Language Runtime actual (CLR).</span><span class="sxs-lookup"><span data-stu-id="37b4b-115">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="37b4b-116">Este método solo se admite para su uso en depuradores fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="37b4b-116">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="37b4b-117">Si se llama desde otro componente, devolverá E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="37b4b-117">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="37b4b-118">Método GetOption</span><span class="sxs-lookup"><span data-stu-id="37b4b-118">GetOption Method</span></span>](imetadatadispenserex-getoption-method.md)|<span data-ttu-id="37b4b-119">Obtiene el valor de la opción especificada para el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="37b4b-119">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="37b4b-120">La opción controla cómo se controlan las llamadas al ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="37b4b-120">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="37b4b-121">Método OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="37b4b-121">OpenScopeOnITypeInfo Method</span></span>](imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="37b4b-122">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="37b4b-122">This method is not implemented.</span></span> <span data-ttu-id="37b4b-123">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="37b4b-123">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="37b4b-124">Método SetOption</span><span class="sxs-lookup"><span data-stu-id="37b4b-124">SetOption Method</span></span>](imetadatadispenserex-setoption-method.md)|<span data-ttu-id="37b4b-125">Establece la opción especificada en un valor determinado para el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="37b4b-125">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="37b4b-126">La opción controla cómo se controlan las llamadas al ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="37b4b-126">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="37b4b-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37b4b-127">Requirements</span></span>  

 <span data-ttu-id="37b4b-128">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37b4b-128">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37b4b-129">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="37b4b-129">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37b4b-130">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="37b4b-130">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="37b4b-131">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37b4b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37b4b-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="37b4b-132">See also</span></span>

- [<span data-ttu-id="37b4b-133">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="37b4b-133">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="37b4b-134">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37b4b-134">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="37b4b-135">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37b4b-135">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="37b4b-136">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37b4b-136">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)

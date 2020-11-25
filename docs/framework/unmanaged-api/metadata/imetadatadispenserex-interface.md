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
ms.openlocfilehash: 60d321c1a87a5da433437c9d4587fa9f8947acf4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713384"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="9d5a0-102">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d5a0-102">IMetaDataDispenserEx Interface</span></span>

<span data-ttu-id="9d5a0-103">Extiende la interfaz [IMetaDataDispenser interface](imetadatadispenser-interface.md) para proporcionar la capacidad de controlar el funcionamiento de las API de metadatos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-103">Extends the [IMetaDataDispenser Interface](imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d5a0-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9d5a0-104">Methods</span></span>  
  
|<span data-ttu-id="9d5a0-105">Método</span><span class="sxs-lookup"><span data-stu-id="9d5a0-105">Method</span></span>|<span data-ttu-id="9d5a0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d5a0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d5a0-107">Método FindAssembly</span><span class="sxs-lookup"><span data-stu-id="9d5a0-107">FindAssembly Method</span></span>](imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="9d5a0-108">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-108">This method is not implemented.</span></span> <span data-ttu-id="9d5a0-109">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="9d5a0-110">Método FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="9d5a0-110">FindAssemblyModule Method</span></span>](imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="9d5a0-111">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-111">This method is not implemented.</span></span> <span data-ttu-id="9d5a0-112">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="9d5a0-113">Método GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="9d5a0-113">GetCORSystemDirectory Method</span></span>](imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="9d5a0-114">Obtiene el directorio que contiene el Common Language Runtime actual (CLR).</span><span class="sxs-lookup"><span data-stu-id="9d5a0-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="9d5a0-115">Este método solo se admite para su uso en depuradores fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="9d5a0-116">Si se llama desde otro componente, devolverá E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="9d5a0-117">Método GetOption</span><span class="sxs-lookup"><span data-stu-id="9d5a0-117">GetOption Method</span></span>](imetadatadispenserex-getoption-method.md)|<span data-ttu-id="9d5a0-118">Obtiene el valor de la opción especificada para el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="9d5a0-119">La opción controla cómo se controlan las llamadas al ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="9d5a0-120">Método OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="9d5a0-120">OpenScopeOnITypeInfo Method</span></span>](imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="9d5a0-121">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-121">This method is not implemented.</span></span> <span data-ttu-id="9d5a0-122">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="9d5a0-123">Método SetOption</span><span class="sxs-lookup"><span data-stu-id="9d5a0-123">SetOption Method</span></span>](imetadatadispenserex-setoption-method.md)|<span data-ttu-id="9d5a0-124">Establece la opción especificada en un valor determinado para el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="9d5a0-125">La opción controla cómo se controlan las llamadas al ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9d5a0-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d5a0-126">Requirements</span></span>  

 <span data-ttu-id="9d5a0-127">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d5a0-127">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d5a0-128">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9d5a0-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d5a0-129">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9d5a0-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9d5a0-130">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d5a0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d5a0-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9d5a0-131">See also</span></span>

- [<span data-ttu-id="9d5a0-132">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="9d5a0-132">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="9d5a0-133">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d5a0-133">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="9d5a0-134">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d5a0-134">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9d5a0-135">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d5a0-135">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)

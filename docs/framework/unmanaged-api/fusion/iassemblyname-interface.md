---
title: IAssemblyName (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 902ad9f67d06306e79666f0e10d85bdb9c65c377
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="84238-102">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="84238-102">IAssemblyName Interface</span></span>
<span data-ttu-id="84238-103">Proporciona métodos para describir y trabajar con la identidad única de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="84238-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="84238-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="84238-104">Methods</span></span>  
  
|<span data-ttu-id="84238-105">Método</span><span class="sxs-lookup"><span data-stu-id="84238-105">Method</span></span>|<span data-ttu-id="84238-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="84238-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="84238-107">Clone (método)</span><span class="sxs-lookup"><span data-stu-id="84238-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|<span data-ttu-id="84238-108">Crea una copia superficial de este `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="84238-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="84238-109">Finalize (método)</span><span class="sxs-lookup"><span data-stu-id="84238-109">Finalize Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|<span data-ttu-id="84238-110">Esto permite `IAssemblyName` objeto para liberar recursos y realizar otras operaciones de limpieza antes de llama a su destructor.</span><span class="sxs-lookup"><span data-stu-id="84238-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="84238-111">GetDisplayName (método)</span><span class="sxs-lookup"><span data-stu-id="84238-111">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|<span data-ttu-id="84238-112">Obtiene el nombre legible del ensamblado que hace referencia esta `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="84238-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="84238-113">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="84238-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|<span data-ttu-id="84238-114">Obtiene el nombre sencillo y sin cifrar del ensamblado que hace referencia esta `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="84238-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="84238-115">GetProperty (método)</span><span class="sxs-lookup"><span data-stu-id="84238-115">GetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|<span data-ttu-id="84238-116">Obtiene un puntero a la propiedad al que hace referencia especificado `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="84238-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="84238-117">GetVersion (método)</span><span class="sxs-lookup"><span data-stu-id="84238-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|<span data-ttu-id="84238-118">Obtiene la información de versión del ensamblado que hace referencia esta `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="84238-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="84238-119">IsEqual (método)</span><span class="sxs-lookup"><span data-stu-id="84238-119">IsEqual Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|<span data-ttu-id="84238-120">Determina si un determinado `IAssemblyName` es igual a este objeto `IAssemblyName`, en función de las marcas de comparación especificada.</span><span class="sxs-lookup"><span data-stu-id="84238-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="84238-121">SetProperty (método)</span><span class="sxs-lookup"><span data-stu-id="84238-121">SetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|<span data-ttu-id="84238-122">Establece el valor de la propiedad al que hace referencia especificado `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="84238-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="84238-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84238-123">Requirements</span></span>  
 <span data-ttu-id="84238-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84238-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84238-125">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="84238-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="84238-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84238-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84238-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="84238-127">See Also</span></span>  
 [<span data-ttu-id="84238-128">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="84238-128">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="84238-129">IAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="84238-129">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)

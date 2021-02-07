---
description: 'Más información acerca de: IAssemblyName (interfaz)'
title: IAssemblyName (Interfaz)
ms.date: 03/30/2017
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
ms.openlocfilehash: fb5949572adc533bab5ed26ee969267f430f36ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760711"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="be275-103">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="be275-103">IAssemblyName Interface</span></span>

<span data-ttu-id="be275-104">Proporciona métodos para describir y trabajar con la identidad única de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="be275-104">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be275-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="be275-105">Methods</span></span>  
  
|<span data-ttu-id="be275-106">Método</span><span class="sxs-lookup"><span data-stu-id="be275-106">Method</span></span>|<span data-ttu-id="be275-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="be275-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be275-108">Método Clone</span><span class="sxs-lookup"><span data-stu-id="be275-108">Clone Method</span></span>](iassemblyname-clone-method.md)|<span data-ttu-id="be275-109">Crea una copia superficial de este `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="be275-109">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="be275-110">Método Finalize</span><span class="sxs-lookup"><span data-stu-id="be275-110">Finalize Method</span></span>](iassemblyname-finalize-method.md)|<span data-ttu-id="be275-111">Permite `IAssemblyName` a este objeto liberar recursos y realizar otras operaciones de limpieza antes de que se llame a su destructor.</span><span class="sxs-lookup"><span data-stu-id="be275-111">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="be275-112">Método GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="be275-112">GetDisplayName Method</span></span>](iassemblyname-getdisplayname-method.md)|<span data-ttu-id="be275-113">Obtiene el nombre legible del ensamblado al que hace referencia este `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="be275-113">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="be275-114">Método GetName</span><span class="sxs-lookup"><span data-stu-id="be275-114">GetName Method</span></span>](iassemblyname-getname-method.md)|<span data-ttu-id="be275-115">Obtiene el nombre simple y sin cifrar del ensamblado al que hace referencia este `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="be275-115">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="be275-116">GetProperty (método)</span><span class="sxs-lookup"><span data-stu-id="be275-116">GetProperty Method</span></span>](iassemblyname-getproperty-method.md)|<span data-ttu-id="be275-117">Obtiene un puntero a la propiedad a la que hace referencia el especificado `PropertyId` .</span><span class="sxs-lookup"><span data-stu-id="be275-117">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="be275-118">Método GetVersion</span><span class="sxs-lookup"><span data-stu-id="be275-118">GetVersion Method</span></span>](iassemblyname-getversion-method.md)|<span data-ttu-id="be275-119">Obtiene la información de versión para el ensamblado al que hace referencia este `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="be275-119">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="be275-120">Método IsEqual</span><span class="sxs-lookup"><span data-stu-id="be275-120">IsEqual Method</span></span>](iassemblyname-isequal-method.md)|<span data-ttu-id="be275-121">Determina si un `IAssemblyName` objeto especificado es igual a este `IAssemblyName` , en función de las marcas de comparación especificadas.</span><span class="sxs-lookup"><span data-stu-id="be275-121">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="be275-122">Método SetProperty</span><span class="sxs-lookup"><span data-stu-id="be275-122">SetProperty Method</span></span>](iassemblyname-setproperty-method.md)|<span data-ttu-id="be275-123">Establece el valor de la propiedad a la que hace referencia el especificado `PropertyId` .</span><span class="sxs-lookup"><span data-stu-id="be275-123">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be275-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be275-124">Requirements</span></span>  

 <span data-ttu-id="be275-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be275-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be275-126">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="be275-126">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="be275-127">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be275-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be275-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="be275-128">See also</span></span>

- [<span data-ttu-id="be275-129">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="be275-129">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="be275-130">IAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="be275-130">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)

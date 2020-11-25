---
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
ms.openlocfilehash: f6feed9f59715f9a2801cd3a2a99a087957d4377
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715074"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="72fc2-102">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="72fc2-102">IAssemblyName Interface</span></span>

<span data-ttu-id="72fc2-103">Proporciona métodos para describir y trabajar con la identidad única de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="72fc2-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="72fc2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="72fc2-104">Methods</span></span>  
  
|<span data-ttu-id="72fc2-105">Método</span><span class="sxs-lookup"><span data-stu-id="72fc2-105">Method</span></span>|<span data-ttu-id="72fc2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="72fc2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="72fc2-107">Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="72fc2-107">Clone Method</span></span>](iassemblyname-clone-method.md)|<span data-ttu-id="72fc2-108">Crea una copia superficial de este `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="72fc2-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="72fc2-109">Método Finalize</span><span class="sxs-lookup"><span data-stu-id="72fc2-109">Finalize Method</span></span>](iassemblyname-finalize-method.md)|<span data-ttu-id="72fc2-110">Permite `IAssemblyName` a este objeto liberar recursos y realizar otras operaciones de limpieza antes de que se llame a su destructor.</span><span class="sxs-lookup"><span data-stu-id="72fc2-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="72fc2-111">GetDisplayName (Método)</span><span class="sxs-lookup"><span data-stu-id="72fc2-111">GetDisplayName Method</span></span>](iassemblyname-getdisplayname-method.md)|<span data-ttu-id="72fc2-112">Obtiene el nombre legible del ensamblado al que hace referencia este `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="72fc2-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="72fc2-113">GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="72fc2-113">GetName Method</span></span>](iassemblyname-getname-method.md)|<span data-ttu-id="72fc2-114">Obtiene el nombre simple y sin cifrar del ensamblado al que hace referencia este `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="72fc2-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="72fc2-115">Método GetProperty</span><span class="sxs-lookup"><span data-stu-id="72fc2-115">GetProperty Method</span></span>](iassemblyname-getproperty-method.md)|<span data-ttu-id="72fc2-116">Obtiene un puntero a la propiedad a la que hace referencia el especificado `PropertyId` .</span><span class="sxs-lookup"><span data-stu-id="72fc2-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="72fc2-117">GetVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="72fc2-117">GetVersion Method</span></span>](iassemblyname-getversion-method.md)|<span data-ttu-id="72fc2-118">Obtiene la información de versión para el ensamblado al que hace referencia este `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="72fc2-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="72fc2-119">Método IsEqual</span><span class="sxs-lookup"><span data-stu-id="72fc2-119">IsEqual Method</span></span>](iassemblyname-isequal-method.md)|<span data-ttu-id="72fc2-120">Determina si un `IAssemblyName` objeto especificado es igual a este `IAssemblyName` , en función de las marcas de comparación especificadas.</span><span class="sxs-lookup"><span data-stu-id="72fc2-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="72fc2-121">Método SetProperty</span><span class="sxs-lookup"><span data-stu-id="72fc2-121">SetProperty Method</span></span>](iassemblyname-setproperty-method.md)|<span data-ttu-id="72fc2-122">Establece el valor de la propiedad a la que hace referencia el especificado `PropertyId` .</span><span class="sxs-lookup"><span data-stu-id="72fc2-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="72fc2-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72fc2-123">Requirements</span></span>  

 <span data-ttu-id="72fc2-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72fc2-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72fc2-125">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="72fc2-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="72fc2-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72fc2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72fc2-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="72fc2-127">See also</span></span>

- [<span data-ttu-id="72fc2-128">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="72fc2-128">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="72fc2-129">IAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="72fc2-129">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)

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
ms.openlocfilehash: de49d66667033dfc6918b139f90cd5523661597f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134316"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="7c4af-102">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c4af-102">IAssemblyName Interface</span></span>
<span data-ttu-id="7c4af-103">Proporciona métodos para describir y trabajar con la identidad única de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7c4af-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c4af-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7c4af-104">Methods</span></span>  
  
|<span data-ttu-id="7c4af-105">Método</span><span class="sxs-lookup"><span data-stu-id="7c4af-105">Method</span></span>|<span data-ttu-id="7c4af-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c4af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c4af-107">Clone (método)</span><span class="sxs-lookup"><span data-stu-id="7c4af-107">Clone Method</span></span>](iassemblyname-clone-method.md)|<span data-ttu-id="7c4af-108">Crea una copia superficial de este objeto `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="7c4af-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="7c4af-109">Finalize (método)</span><span class="sxs-lookup"><span data-stu-id="7c4af-109">Finalize Method</span></span>](iassemblyname-finalize-method.md)|<span data-ttu-id="7c4af-110">Permite a este objeto `IAssemblyName` liberar recursos y realizar otras operaciones de limpieza antes de que se llame a su destructor.</span><span class="sxs-lookup"><span data-stu-id="7c4af-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="7c4af-111">GetDisplayName (método)</span><span class="sxs-lookup"><span data-stu-id="7c4af-111">GetDisplayName Method</span></span>](iassemblyname-getdisplayname-method.md)|<span data-ttu-id="7c4af-112">Obtiene el nombre legible del ensamblado al que hace referencia este objeto `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="7c4af-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="7c4af-113">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="7c4af-113">GetName Method</span></span>](iassemblyname-getname-method.md)|<span data-ttu-id="7c4af-114">Obtiene el nombre simple y sin cifrar del ensamblado al que hace referencia este objeto `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="7c4af-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="7c4af-115">GetProperty (método)</span><span class="sxs-lookup"><span data-stu-id="7c4af-115">GetProperty Method</span></span>](iassemblyname-getproperty-method.md)|<span data-ttu-id="7c4af-116">Obtiene un puntero a la propiedad a la que hace referencia el `PropertyId`especificado.</span><span class="sxs-lookup"><span data-stu-id="7c4af-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="7c4af-117">GetVersion (método)</span><span class="sxs-lookup"><span data-stu-id="7c4af-117">GetVersion Method</span></span>](iassemblyname-getversion-method.md)|<span data-ttu-id="7c4af-118">Obtiene la información de versión del ensamblado al que hace referencia este objeto `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="7c4af-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="7c4af-119">IsEqual (método)</span><span class="sxs-lookup"><span data-stu-id="7c4af-119">IsEqual Method</span></span>](iassemblyname-isequal-method.md)|<span data-ttu-id="7c4af-120">Determina si un objeto de `IAssemblyName` especificado es igual a este `IAssemblyName`, en función de las marcas de comparación especificadas.</span><span class="sxs-lookup"><span data-stu-id="7c4af-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="7c4af-121">SetProperty (método)</span><span class="sxs-lookup"><span data-stu-id="7c4af-121">SetProperty Method</span></span>](iassemblyname-setproperty-method.md)|<span data-ttu-id="7c4af-122">Establece el valor de la propiedad a la que hace referencia el `PropertyId`especificado.</span><span class="sxs-lookup"><span data-stu-id="7c4af-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c4af-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c4af-123">Requirements</span></span>  
 <span data-ttu-id="7c4af-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c4af-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c4af-125">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7c4af-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7c4af-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c4af-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c4af-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c4af-127">See also</span></span>

- [<span data-ttu-id="7c4af-128">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="7c4af-128">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="7c4af-129">IAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c4af-129">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)

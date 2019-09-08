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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aee9b986c1e26c1b2e34dac7151a00172451bbad
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796551"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="7ab38-102">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ab38-102">IAssemblyName Interface</span></span>
<span data-ttu-id="7ab38-103">Proporciona métodos para describir y trabajar con la identidad única de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7ab38-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ab38-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7ab38-104">Methods</span></span>  
  
|<span data-ttu-id="7ab38-105">Método</span><span class="sxs-lookup"><span data-stu-id="7ab38-105">Method</span></span>|<span data-ttu-id="7ab38-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7ab38-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ab38-107">Clone (método)</span><span class="sxs-lookup"><span data-stu-id="7ab38-107">Clone Method</span></span>](iassemblyname-clone-method.md)|<span data-ttu-id="7ab38-108">Crea una copia superficial de este `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="7ab38-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="7ab38-109">Finalize (método)</span><span class="sxs-lookup"><span data-stu-id="7ab38-109">Finalize Method</span></span>](iassemblyname-finalize-method.md)|<span data-ttu-id="7ab38-110">Permite a `IAssemblyName` este objeto liberar recursos y realizar otras operaciones de limpieza antes de que se llame a su destructor.</span><span class="sxs-lookup"><span data-stu-id="7ab38-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="7ab38-111">GetDisplayName (método)</span><span class="sxs-lookup"><span data-stu-id="7ab38-111">GetDisplayName Method</span></span>](iassemblyname-getdisplayname-method.md)|<span data-ttu-id="7ab38-112">Obtiene el nombre legible del ensamblado al que hace referencia este `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="7ab38-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="7ab38-113">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="7ab38-113">GetName Method</span></span>](iassemblyname-getname-method.md)|<span data-ttu-id="7ab38-114">Obtiene el nombre simple y sin cifrar del ensamblado al que hace `IAssemblyName` referencia este objeto.</span><span class="sxs-lookup"><span data-stu-id="7ab38-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="7ab38-115">GetProperty (método)</span><span class="sxs-lookup"><span data-stu-id="7ab38-115">GetProperty Method</span></span>](iassemblyname-getproperty-method.md)|<span data-ttu-id="7ab38-116">Obtiene un puntero a la propiedad a la que hace referencia `PropertyId`el especificado.</span><span class="sxs-lookup"><span data-stu-id="7ab38-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="7ab38-117">GetVersion (método)</span><span class="sxs-lookup"><span data-stu-id="7ab38-117">GetVersion Method</span></span>](iassemblyname-getversion-method.md)|<span data-ttu-id="7ab38-118">Obtiene la información de versión para el ensamblado al que `IAssemblyName` hace referencia este objeto.</span><span class="sxs-lookup"><span data-stu-id="7ab38-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="7ab38-119">IsEqual (método)</span><span class="sxs-lookup"><span data-stu-id="7ab38-119">IsEqual Method</span></span>](iassemblyname-isequal-method.md)|<span data-ttu-id="7ab38-120">Determina si un objeto `IAssemblyName` especificado es igual a este `IAssemblyName`, en función de las marcas de comparación especificadas.</span><span class="sxs-lookup"><span data-stu-id="7ab38-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="7ab38-121">SetProperty (método)</span><span class="sxs-lookup"><span data-stu-id="7ab38-121">SetProperty Method</span></span>](iassemblyname-setproperty-method.md)|<span data-ttu-id="7ab38-122">Establece el valor de la propiedad a la que hace referencia `PropertyId`el especificado.</span><span class="sxs-lookup"><span data-stu-id="7ab38-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ab38-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ab38-123">Requirements</span></span>  
 <span data-ttu-id="7ab38-124">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ab38-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ab38-125">**Encabezado**: Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7ab38-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7ab38-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ab38-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab38-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ab38-127">See also</span></span>

- [<span data-ttu-id="7ab38-128">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="7ab38-128">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="7ab38-129">IAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ab38-129">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)

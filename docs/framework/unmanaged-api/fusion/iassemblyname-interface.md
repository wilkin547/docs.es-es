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
ms.openlocfilehash: 0d8d59ef282818dd9852d0ff8d2ec2abd40986d0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097140"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="8f658-102">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f658-102">IAssemblyName Interface</span></span>
<span data-ttu-id="8f658-103">Proporciona métodos para describir y trabajar con la identidad única de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8f658-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f658-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8f658-104">Methods</span></span>  
  
|<span data-ttu-id="8f658-105">Método</span><span class="sxs-lookup"><span data-stu-id="8f658-105">Method</span></span>|<span data-ttu-id="8f658-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f658-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f658-107">Método Clone</span><span class="sxs-lookup"><span data-stu-id="8f658-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|<span data-ttu-id="8f658-108">Crea una copia superficial de este `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="8f658-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="8f658-109">Método Finalize</span><span class="sxs-lookup"><span data-stu-id="8f658-109">Finalize Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|<span data-ttu-id="8f658-110">Esto permite `IAssemblyName` objeto para liberar recursos y realizar otras operaciones de limpieza antes de llama a su destructor.</span><span class="sxs-lookup"><span data-stu-id="8f658-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="8f658-111">Método GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="8f658-111">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|<span data-ttu-id="8f658-112">Obtiene el nombre legible del ensamblado que hace referencia esta `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="8f658-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="8f658-113">Método GetName</span><span class="sxs-lookup"><span data-stu-id="8f658-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|<span data-ttu-id="8f658-114">Obtiene el nombre sencillo y sin cifrar del ensamblado que hace referencia esta `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="8f658-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="8f658-115">Método GetProperty</span><span class="sxs-lookup"><span data-stu-id="8f658-115">GetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|<span data-ttu-id="8f658-116">Obtiene un puntero a la propiedad al que hace referencia especificado `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="8f658-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="8f658-117">Método GetVersion</span><span class="sxs-lookup"><span data-stu-id="8f658-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|<span data-ttu-id="8f658-118">Obtiene la información de versión del ensamblado que hace referencia esta `IAssemblyName` objeto.</span><span class="sxs-lookup"><span data-stu-id="8f658-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="8f658-119">Método IsEqual</span><span class="sxs-lookup"><span data-stu-id="8f658-119">IsEqual Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|<span data-ttu-id="8f658-120">Determina si un `IAssemblyName` es igual a este objeto `IAssemblyName`, en función de las marcas de comparación especificado.</span><span class="sxs-lookup"><span data-stu-id="8f658-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="8f658-121">Método SetProperty</span><span class="sxs-lookup"><span data-stu-id="8f658-121">SetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|<span data-ttu-id="8f658-122">Establece el valor de la propiedad al que hace referencia especificado `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="8f658-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f658-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f658-123">Requirements</span></span>  
 <span data-ttu-id="8f658-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f658-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f658-125">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="8f658-125">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="8f658-126">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8f658-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8f658-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f658-127">See also</span></span>

- [<span data-ttu-id="8f658-128">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="8f658-128">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="8f658-129">IAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f658-129">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)

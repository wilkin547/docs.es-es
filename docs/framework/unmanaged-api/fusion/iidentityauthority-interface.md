---
title: IIdentityAuthority (Interfaz)
ms.date: 03/30/2017
api_name:
- IIdentityAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IIdentityAuthority
helpviewer_keywords:
- IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab8965ca5d6c9c96cea5f5b351547ce2d4dfacc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546285"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="d4149-102">IIdentityAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4149-102">IIdentityAuthority Interface</span></span>
<span data-ttu-id="d4149-103">Administra las claves de identidad para los objetos de código.</span><span class="sxs-lookup"><span data-stu-id="d4149-103">Manages identity keys for code objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d4149-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d4149-104">Methods</span></span>  
  
|<span data-ttu-id="d4149-105">Método</span><span class="sxs-lookup"><span data-stu-id="d4149-105">Method</span></span>|<span data-ttu-id="d4149-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4149-106">Description</span></span>|  
|------------|-----------------|  
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="d4149-107">Obtiene un valor que indica si los dos especifica [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instancias son iguales.</span><span class="sxs-lookup"><span data-stu-id="d4149-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="d4149-108">Obtiene un valor que indica si los dos especifica [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instancias son iguales.</span><span class="sxs-lookup"><span data-stu-id="d4149-108">Gets a value that indicates whether the two specified [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="d4149-109">Obtiene un valor que indica si las dos representaciones de identidad de definición de cadena especificada son iguales.</span><span class="sxs-lookup"><span data-stu-id="d4149-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|  
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="d4149-110">Obtiene un valor que indica si las dos representaciones de identidad de referencia de la cadena especificada son iguales.</span><span class="sxs-lookup"><span data-stu-id="d4149-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|  
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="d4149-111">Obtiene un puntero a un nuevo `IDefinitionIdentity` instancia que representa el objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="d4149-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="d4149-112">Obtiene un puntero a un nuevo `IReferenceIdentity` instancia que representa el objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="d4149-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="d4149-113">Obtiene una versión de cadena con formato del elemento especificado `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="d4149-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="d4149-114">Llena el búfer de carácter ancho especificado con una versión de cadena del elemento especificado `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="d4149-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="d4149-115">Obtiene un valor que indica si el texto especificado `IDefinitionIdentity` y `IReferenceIdentity` instancias hacen referencia al mismo objeto de código.</span><span class="sxs-lookup"><span data-stu-id="d4149-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|  
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="d4149-116">Obtiene un valor que indica si las cadenas especificadas hacen referencia al mismo objeto de código.</span><span class="sxs-lookup"><span data-stu-id="d4149-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|  
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="d4149-117">Obtiene un puntero a una clave de cadena recién creada para el elemento especificado `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="d4149-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="d4149-118">Obtiene un puntero a una clave de cadena recién creada para el elemento especificado `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="d4149-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="d4149-119">Obtiene un valor hash para el elemento especificado `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="d4149-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::HashReference`|<span data-ttu-id="d4149-120">Obtiene un valor hash para el elemento especificado `IreferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="d4149-120">Gets a hash value for the specified `IreferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="d4149-121">Obtiene una versión de cadena con formato del elemento especificado `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="d4149-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="d4149-122">Llena el búfer de carácter ancho especificado con una versión de cadena del elemento especificado `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="d4149-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="d4149-123">Obtiene un puntero de interfaz a un `IDefinitionIdentity` cadena con formato de instancia generado a partir de la especificada.</span><span class="sxs-lookup"><span data-stu-id="d4149-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|  
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="d4149-124">Obtiene un puntero de interfaz a un `IReferenceIdentity` cadena con formato de instancia generado a partir de la especificada.</span><span class="sxs-lookup"><span data-stu-id="d4149-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4149-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4149-125">Requirements</span></span>  
 <span data-ttu-id="d4149-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4149-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4149-127">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="d4149-127">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="d4149-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4149-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4149-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4149-129">See also</span></span>
- [<span data-ttu-id="d4149-130">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="d4149-130">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

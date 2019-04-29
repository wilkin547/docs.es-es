---
title: IAppIdAuthority (Interfaz)
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 724ee01e91f1e9f4e34d2262610152a977ed4f53
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697581"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="bbb33-102">IAppIdAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bbb33-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="bbb33-103">Proporciona métodos que generan y comparan las identidades de aplicaciones y las referencias de claves.</span><span class="sxs-lookup"><span data-stu-id="bbb33-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bbb33-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="bbb33-104">Methods</span></span>  
  
|<span data-ttu-id="bbb33-105">Método</span><span class="sxs-lookup"><span data-stu-id="bbb33-105">Method</span></span>|<span data-ttu-id="bbb33-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bbb33-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="bbb33-107">Obtiene un valor que indica si los dos especifica [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instancias son iguales.</span><span class="sxs-lookup"><span data-stu-id="bbb33-107">Gets a value that indicates whether the two specified [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="bbb33-108">Puede pasar el valor de marcador IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para pasar por alto la información de versión respectiva.</span><span class="sxs-lookup"><span data-stu-id="bbb33-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="bbb33-109">Obtiene un valor que indica si los dos especifica [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instancias son iguales.</span><span class="sxs-lookup"><span data-stu-id="bbb33-109">Gets a value that indicates whether the two specified [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="bbb33-110">Puede pasar el valor de marcador IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para pasar por alto la información de versión respectiva.</span><span class="sxs-lookup"><span data-stu-id="bbb33-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="bbb33-111">Obtiene un valor que indica si las dos definiciones de la cadena especificada son iguales.</span><span class="sxs-lookup"><span data-stu-id="bbb33-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="bbb33-112">Puede pasar el valor de marcador IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para pasar por alto la información de versión respectiva.</span><span class="sxs-lookup"><span data-stu-id="bbb33-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="bbb33-113">Obtiene un valor que indica si las dos referencias de cadena especificada son iguales.</span><span class="sxs-lookup"><span data-stu-id="bbb33-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="bbb33-114">Puede pasar el valor de marcador IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para pasar por alto la información de versión respectiva.</span><span class="sxs-lookup"><span data-stu-id="bbb33-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="bbb33-115">Obtiene un puntero de interfaz a una recién generado `IDefinitionAppId` instancia que representa el ensamblado en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="bbb33-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="bbb33-116">Obtiene un puntero de interfaz en otra recién creada `IReferenceAppId` que representa el ensamblado en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="bbb33-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="bbb33-117">Obtiene una versión de cadena del elemento especificado `IDefinitionAppId`, utilizando los valores de marcador especificado.</span><span class="sxs-lookup"><span data-stu-id="bbb33-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="bbb33-118">Obtiene un valor que indica si el texto especificado `IDefinitionAppId` y `IReferenceAppId` representan el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bbb33-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="bbb33-119">Obtiene un valor que indica si la cadena de referencia y la cadena de definición especificado representan el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bbb33-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="bbb33-120">Obtiene una clave de cadena que representa el parámetro `IDefinitionAppId` instancia.</span><span class="sxs-lookup"><span data-stu-id="bbb33-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="bbb33-121">Obtiene una clave de cadena que representa el parámetro `IReferenceAppId` instancia.</span><span class="sxs-lookup"><span data-stu-id="bbb33-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="bbb33-122">Obtiene una clave hash para el elemento especificado `IDefinitionAppId` instancia.</span><span class="sxs-lookup"><span data-stu-id="bbb33-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="bbb33-123">Obtiene una clave hash para el elemento especificado `IReferenceAppId` instancia.</span><span class="sxs-lookup"><span data-stu-id="bbb33-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="bbb33-124">Obtiene una versión de cadena del elemento especificado `IReferenceAppId`, utilizando los valores de marcador especificado.</span><span class="sxs-lookup"><span data-stu-id="bbb33-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="bbb33-125">Obtiene un puntero de interfaz a un `IDefinitionAppId` instancia que representa el ensamblado al que hace referencia la clave de cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="bbb33-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="bbb33-126">Obtiene un puntero de interfaz a un `IReferenceAppId` instancia que representa el ensamblado al que hace referencia la clave de cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="bbb33-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bbb33-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bbb33-127">Requirements</span></span>  
 <span data-ttu-id="bbb33-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbb33-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbb33-129">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="bbb33-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="bbb33-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbb33-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb33-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbb33-131">See also</span></span>

- [<span data-ttu-id="bbb33-132">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="bbb33-132">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

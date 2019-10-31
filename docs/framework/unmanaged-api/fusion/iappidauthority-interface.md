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
ms.openlocfilehash: 004e4f70e3385e7a71c356cce38e64d0253dcfa4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127136"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="62d3c-102">IAppIdAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62d3c-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="62d3c-103">Proporciona métodos que generan y comparan las claves de las identidades y referencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="62d3c-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62d3c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="62d3c-104">Methods</span></span>  
  
|<span data-ttu-id="62d3c-105">Método</span><span class="sxs-lookup"><span data-stu-id="62d3c-105">Method</span></span>|<span data-ttu-id="62d3c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="62d3c-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="62d3c-107">Obtiene un valor que indica si las dos instancias de [IDefinitionAppId](idefinitionappid-interface.md) especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="62d3c-107">Gets a value that indicates whether the two specified [IDefinitionAppId](idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="62d3c-108">Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.</span><span class="sxs-lookup"><span data-stu-id="62d3c-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="62d3c-109">Obtiene un valor que indica si las dos instancias de [IReferenceAppId](ireferenceappid-interface.md) especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="62d3c-109">Gets a value that indicates whether the two specified [IReferenceAppId](ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="62d3c-110">Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.</span><span class="sxs-lookup"><span data-stu-id="62d3c-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="62d3c-111">Obtiene un valor que indica si las dos definiciones de cadena especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="62d3c-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="62d3c-112">Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.</span><span class="sxs-lookup"><span data-stu-id="62d3c-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="62d3c-113">Obtiene un valor que indica si las dos referencias de cadena especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="62d3c-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="62d3c-114">Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.</span><span class="sxs-lookup"><span data-stu-id="62d3c-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="62d3c-115">Obtiene un puntero de interfaz a una instancia de `IDefinitionAppId` recién generada que representa el ensamblado en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="62d3c-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="62d3c-116">Obtiene un puntero de interfaz a un `IReferenceAppId` recién creado que representa el ensamblado en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="62d3c-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="62d3c-117">Obtiene una versión de cadena del `IDefinitionAppId`especificado, utilizando los valores de marca especificados.</span><span class="sxs-lookup"><span data-stu-id="62d3c-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="62d3c-118">Obtiene un valor que indica si el `IDefinitionAppId` y `IReferenceAppId` especificados representan el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="62d3c-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="62d3c-119">Obtiene un valor que indica si la cadena de definición especificada y la cadena de referencia representan el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="62d3c-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="62d3c-120">Obtiene una clave de cadena que representa la instancia de `IDefinitionAppId` especificada.</span><span class="sxs-lookup"><span data-stu-id="62d3c-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="62d3c-121">Obtiene una clave de cadena que representa la instancia de `IReferenceAppId` especificada.</span><span class="sxs-lookup"><span data-stu-id="62d3c-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="62d3c-122">Obtiene una clave hash para la instancia de `IDefinitionAppId` especificada.</span><span class="sxs-lookup"><span data-stu-id="62d3c-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="62d3c-123">Obtiene una clave hash para la instancia de `IReferenceAppId` especificada.</span><span class="sxs-lookup"><span data-stu-id="62d3c-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="62d3c-124">Obtiene una versión de cadena del `IReferenceAppId`especificado, utilizando los valores de marca especificados.</span><span class="sxs-lookup"><span data-stu-id="62d3c-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="62d3c-125">Obtiene un puntero de interfaz a una instancia de `IDefinitionAppId` que representa el ensamblado al que hace referencia la clave de cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="62d3c-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="62d3c-126">Obtiene un puntero de interfaz a una instancia de `IReferenceAppId` que representa el ensamblado al que hace referencia la clave de cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="62d3c-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="62d3c-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62d3c-127">Requirements</span></span>  
 <span data-ttu-id="62d3c-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62d3c-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62d3c-129">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="62d3c-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="62d3c-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62d3c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62d3c-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="62d3c-131">See also</span></span>

- [<span data-ttu-id="62d3c-132">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="62d3c-132">Fusion Interfaces</span></span>](fusion-interfaces.md)

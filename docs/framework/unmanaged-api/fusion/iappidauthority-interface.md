---
description: 'Más información acerca de: interfaz Iappidauthority ('
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
ms.openlocfilehash: 238885c7f080571b414511c24f9772dbc19b4683
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761010"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="5583b-103">IAppIdAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5583b-103">IAppIdAuthority Interface</span></span>

<span data-ttu-id="5583b-104">Proporciona métodos que generan y comparan las claves de las identidades y referencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5583b-104">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5583b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5583b-105">Methods</span></span>  
  
|<span data-ttu-id="5583b-106">Método</span><span class="sxs-lookup"><span data-stu-id="5583b-106">Method</span></span>|<span data-ttu-id="5583b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5583b-107">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="5583b-108">Obtiene un valor que indica si las dos instancias de [IDefinitionAppId](idefinitionappid-interface.md) especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="5583b-108">Gets a value that indicates whether the two specified [IDefinitionAppId](idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="5583b-109">Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5583b-109">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="5583b-110">Obtiene un valor que indica si las dos instancias de [IReferenceAppId](ireferenceappid-interface.md) especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="5583b-110">Gets a value that indicates whether the two specified [IReferenceAppId](ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="5583b-111">Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5583b-111">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="5583b-112">Obtiene un valor que indica si las dos definiciones de cadena especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="5583b-112">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="5583b-113">Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5583b-113">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="5583b-114">Obtiene un valor que indica si las dos referencias de cadena especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="5583b-114">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="5583b-115">Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5583b-115">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="5583b-116">Obtiene un puntero de interfaz a una instancia recién generada `IDefinitionAppId` que representa el ensamblado en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="5583b-116">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="5583b-117">Obtiene un puntero de interfaz a un que se acaba `IReferenceAppId` de crear que representa el ensamblado en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="5583b-117">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="5583b-118">Obtiene una versión de cadena del especificado `IDefinitionAppId` , utilizando los valores de marca especificados.</span><span class="sxs-lookup"><span data-stu-id="5583b-118">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="5583b-119">Obtiene un valor que indica si el especificado `IDefinitionAppId` y `IReferenceAppId` representa el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5583b-119">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="5583b-120">Obtiene un valor que indica si la cadena de definición especificada y la cadena de referencia representan el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5583b-120">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="5583b-121">Obtiene una clave de cadena que representa la `IDefinitionAppId` instancia de especificada.</span><span class="sxs-lookup"><span data-stu-id="5583b-121">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="5583b-122">Obtiene una clave de cadena que representa la `IReferenceAppId` instancia de especificada.</span><span class="sxs-lookup"><span data-stu-id="5583b-122">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="5583b-123">Obtiene una clave hash para la instancia de especificada `IDefinitionAppId` .</span><span class="sxs-lookup"><span data-stu-id="5583b-123">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="5583b-124">Obtiene una clave hash para la instancia de especificada `IReferenceAppId` .</span><span class="sxs-lookup"><span data-stu-id="5583b-124">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="5583b-125">Obtiene una versión de cadena del especificado `IReferenceAppId` , utilizando los valores de marca especificados.</span><span class="sxs-lookup"><span data-stu-id="5583b-125">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="5583b-126">Obtiene un puntero de interfaz a una `IDefinitionAppId` instancia de que representa el ensamblado al que hace referencia la clave de cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="5583b-126">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="5583b-127">Obtiene un puntero de interfaz a una `IReferenceAppId` instancia de que representa el ensamblado al que hace referencia la clave de cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="5583b-127">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5583b-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5583b-128">Requirements</span></span>  

 <span data-ttu-id="5583b-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5583b-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5583b-130">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="5583b-130">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="5583b-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5583b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5583b-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="5583b-132">See also</span></span>

- [<span data-ttu-id="5583b-133">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="5583b-133">Fusion Interfaces</span></span>](fusion-interfaces.md)

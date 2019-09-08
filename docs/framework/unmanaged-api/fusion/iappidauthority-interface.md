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
ms.openlocfilehash: 91ab2f71e7fb74f8e0e517b566d46d61c316ebe2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796839"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="10b16-102">IAppIdAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10b16-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="10b16-103">Proporciona métodos que generan y comparan las claves de las identidades y referencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10b16-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10b16-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="10b16-104">Methods</span></span>  
  
|<span data-ttu-id="10b16-105">Método</span><span class="sxs-lookup"><span data-stu-id="10b16-105">Method</span></span>|<span data-ttu-id="10b16-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="10b16-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="10b16-107">Obtiene un valor que indica si las dos instancias de [IDefinitionAppId](idefinitionappid-interface.md) especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="10b16-107">Gets a value that indicates whether the two specified [IDefinitionAppId](idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="10b16-108">Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.</span><span class="sxs-lookup"><span data-stu-id="10b16-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="10b16-109">Obtiene un valor que indica si las dos instancias de [IReferenceAppId](ireferenceappid-interface.md) especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="10b16-109">Gets a value that indicates whether the two specified [IReferenceAppId](ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="10b16-110">Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.</span><span class="sxs-lookup"><span data-stu-id="10b16-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="10b16-111">Obtiene un valor que indica si las dos definiciones de cadena especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="10b16-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="10b16-112">Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.</span><span class="sxs-lookup"><span data-stu-id="10b16-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="10b16-113">Obtiene un valor que indica si las dos referencias de cadena especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="10b16-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="10b16-114">Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.</span><span class="sxs-lookup"><span data-stu-id="10b16-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="10b16-115">Obtiene un puntero de interfaz a una instancia `IDefinitionAppId` recién generada que representa el ensamblado en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="10b16-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="10b16-116">Obtiene un puntero de interfaz a un que `IReferenceAppId` se acaba de crear que representa el ensamblado en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="10b16-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="10b16-117">Obtiene una versión de cadena del especificado `IDefinitionAppId`, utilizando los valores de marca especificados.</span><span class="sxs-lookup"><span data-stu-id="10b16-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="10b16-118">Obtiene un valor que indica si el especificado `IDefinitionAppId` y `IReferenceAppId` representa el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="10b16-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="10b16-119">Obtiene un valor que indica si la cadena de definición especificada y la cadena de referencia representan el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="10b16-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="10b16-120">Obtiene una clave de cadena que representa la `IDefinitionAppId` instancia de especificada.</span><span class="sxs-lookup"><span data-stu-id="10b16-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="10b16-121">Obtiene una clave de cadena que representa la `IReferenceAppId` instancia de especificada.</span><span class="sxs-lookup"><span data-stu-id="10b16-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="10b16-122">Obtiene una clave hash para la instancia `IDefinitionAppId` de especificada.</span><span class="sxs-lookup"><span data-stu-id="10b16-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="10b16-123">Obtiene una clave hash para la instancia `IReferenceAppId` de especificada.</span><span class="sxs-lookup"><span data-stu-id="10b16-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="10b16-124">Obtiene una versión de cadena del especificado `IReferenceAppId`, utilizando los valores de marca especificados.</span><span class="sxs-lookup"><span data-stu-id="10b16-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="10b16-125">Obtiene un puntero de interfaz a `IDefinitionAppId` una instancia de que representa el ensamblado al que hace referencia la clave de cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="10b16-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="10b16-126">Obtiene un puntero de interfaz a `IReferenceAppId` una instancia de que representa el ensamblado al que hace referencia la clave de cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="10b16-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10b16-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10b16-127">Requirements</span></span>  
 <span data-ttu-id="10b16-128">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10b16-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10b16-129">**Encabezado**: Isolation. h</span><span class="sxs-lookup"><span data-stu-id="10b16-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="10b16-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10b16-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10b16-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="10b16-131">See also</span></span>

- [<span data-ttu-id="10b16-132">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="10b16-132">Fusion Interfaces</span></span>](fusion-interfaces.md)

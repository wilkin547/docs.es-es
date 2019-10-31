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
ms.openlocfilehash: 3e2d2335e37ced9139ea44092f10b19566894681
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127090"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="afc6a-102">IIdentityAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="afc6a-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="afc6a-103">Administra claves de identidad para objetos de código.</span><span class="sxs-lookup"><span data-stu-id="afc6a-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="afc6a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="afc6a-104">Methods</span></span>

|<span data-ttu-id="afc6a-105">Método</span><span class="sxs-lookup"><span data-stu-id="afc6a-105">Method</span></span>|<span data-ttu-id="afc6a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="afc6a-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="afc6a-107">Obtiene un valor que indica si las dos instancias de [IDefinitionIdentity](idefinitionidentity-interface.md) especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="afc6a-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="afc6a-108">Obtiene un valor que indica si las dos instancias de [IReferenceIdentity](ireferenceidentity-interface.md) especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="afc6a-108">Gets a value that indicates whether the two specified [IReferenceIdentity](ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="afc6a-109">Obtiene un valor que indica si las dos representaciones de identidad de definición de cadena especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="afc6a-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="afc6a-110">Obtiene un valor que indica si las dos representaciones de identidad de referencia de cadena especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="afc6a-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="afc6a-111">Obtiene un puntero a una nueva instancia de `IDefinitionIdentity` que representa el objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="afc6a-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="afc6a-112">Obtiene un puntero a una nueva instancia de `IReferenceIdentity` que representa el objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="afc6a-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="afc6a-113">Obtiene una versión de cadena con formato del `IDefinitionIdentity`especificado.</span><span class="sxs-lookup"><span data-stu-id="afc6a-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="afc6a-114">Rellena el búfer de caracteres anchos especificado con una versión de cadena del `IDefinitionIdentity`especificado.</span><span class="sxs-lookup"><span data-stu-id="afc6a-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="afc6a-115">Obtiene un valor que indica si las instancias de `IDefinitionIdentity` y `IReferenceIdentity` especificadas hacen referencia al mismo objeto de código.</span><span class="sxs-lookup"><span data-stu-id="afc6a-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="afc6a-116">Obtiene un valor que indica si las cadenas especificadas hacen referencia al mismo objeto de código.</span><span class="sxs-lookup"><span data-stu-id="afc6a-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="afc6a-117">Obtiene un puntero a una clave de cadena recién creada para el `IDefinitionIdentity`especificado.</span><span class="sxs-lookup"><span data-stu-id="afc6a-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="afc6a-118">Obtiene un puntero a una clave de cadena recién creada para el `IReferenceIdentity`especificado.</span><span class="sxs-lookup"><span data-stu-id="afc6a-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="afc6a-119">Obtiene un valor hash para el `IDefinitionIdentity`especificado.</span><span class="sxs-lookup"><span data-stu-id="afc6a-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="afc6a-120">Obtiene un valor hash para el `IReferenceIdentity`especificado.</span><span class="sxs-lookup"><span data-stu-id="afc6a-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="afc6a-121">Obtiene una versión de cadena con formato del `IReferenceIdentity`especificado.</span><span class="sxs-lookup"><span data-stu-id="afc6a-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="afc6a-122">Rellena el búfer de caracteres anchos especificado con una versión de cadena del `IReferenceIdentity`especificado.</span><span class="sxs-lookup"><span data-stu-id="afc6a-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="afc6a-123">Obtiene un puntero de interfaz a una instancia de `IDefinitionIdentity` generada a partir de la cadena con formato especificada.</span><span class="sxs-lookup"><span data-stu-id="afc6a-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="afc6a-124">Obtiene un puntero de interfaz a una instancia de `IReferenceIdentity` generada a partir de la cadena con formato especificada.</span><span class="sxs-lookup"><span data-stu-id="afc6a-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="afc6a-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="afc6a-125">Requirements</span></span>

<span data-ttu-id="afc6a-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afc6a-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="afc6a-127">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="afc6a-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="afc6a-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afc6a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="afc6a-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="afc6a-129">See also</span></span>

- [<span data-ttu-id="afc6a-130">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="afc6a-130">Fusion Interfaces</span></span>](fusion-interfaces.md)

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
ms.openlocfilehash: 7421e0d0e1a1f0e1a5fbe0d0eb7d5a0ab2a48b9a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796421"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="32c11-102">IIdentityAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="32c11-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="32c11-103">Administra claves de identidad para objetos de código.</span><span class="sxs-lookup"><span data-stu-id="32c11-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="32c11-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="32c11-104">Methods</span></span>

|<span data-ttu-id="32c11-105">Método</span><span class="sxs-lookup"><span data-stu-id="32c11-105">Method</span></span>|<span data-ttu-id="32c11-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="32c11-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="32c11-107">Obtiene un valor que indica si las dos instancias de [IDefinitionIdentity](idefinitionidentity-interface.md) especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="32c11-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="32c11-108">Obtiene un valor que indica si las dos instancias de [IReferenceIdentity](ireferenceidentity-interface.md) especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="32c11-108">Gets a value that indicates whether the two specified [IReferenceIdentity](ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="32c11-109">Obtiene un valor que indica si las dos representaciones de identidad de definición de cadena especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="32c11-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="32c11-110">Obtiene un valor que indica si las dos representaciones de identidad de referencia de cadena especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="32c11-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="32c11-111">Obtiene un puntero a una nueva `IDefinitionIdentity` instancia de que representa el objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="32c11-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="32c11-112">Obtiene un puntero a una nueva `IReferenceIdentity` instancia de que representa el objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="32c11-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="32c11-113">Obtiene una versión de cadena con formato del `IDefinitionIdentity`especificado.</span><span class="sxs-lookup"><span data-stu-id="32c11-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="32c11-114">Rellena el búfer de caracteres anchos especificado con una versión de cadena del `IDefinitionIdentity`especificado.</span><span class="sxs-lookup"><span data-stu-id="32c11-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="32c11-115">Obtiene un valor que indica si las instancias `IDefinitionIdentity` y `IReferenceIdentity` especificadas hacen referencia al mismo objeto de código.</span><span class="sxs-lookup"><span data-stu-id="32c11-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="32c11-116">Obtiene un valor que indica si las cadenas especificadas hacen referencia al mismo objeto de código.</span><span class="sxs-lookup"><span data-stu-id="32c11-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="32c11-117">Obtiene un puntero a una clave de cadena recién creada para el `IDefinitionIdentity`especificado.</span><span class="sxs-lookup"><span data-stu-id="32c11-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="32c11-118">Obtiene un puntero a una clave de cadena recién creada para el `IReferenceIdentity`especificado.</span><span class="sxs-lookup"><span data-stu-id="32c11-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="32c11-119">Obtiene un valor hash para el especificado `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="32c11-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="32c11-120">Obtiene un valor hash para el especificado `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="32c11-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="32c11-121">Obtiene una versión de cadena con formato del `IReferenceIdentity`especificado.</span><span class="sxs-lookup"><span data-stu-id="32c11-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="32c11-122">Rellena el búfer de caracteres anchos especificado con una versión de cadena del `IReferenceIdentity`especificado.</span><span class="sxs-lookup"><span data-stu-id="32c11-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="32c11-123">Obtiene un puntero de interfaz a `IDefinitionIdentity` una instancia de generada a partir de la cadena con formato especificada.</span><span class="sxs-lookup"><span data-stu-id="32c11-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="32c11-124">Obtiene un puntero de interfaz a `IReferenceIdentity` una instancia de generada a partir de la cadena con formato especificada.</span><span class="sxs-lookup"><span data-stu-id="32c11-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="32c11-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="32c11-125">Requirements</span></span>

<span data-ttu-id="32c11-126">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32c11-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="32c11-127">**Encabezado**: Isolation. h</span><span class="sxs-lookup"><span data-stu-id="32c11-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="32c11-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32c11-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="32c11-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="32c11-129">See also</span></span>

- [<span data-ttu-id="32c11-130">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="32c11-130">Fusion Interfaces</span></span>](fusion-interfaces.md)

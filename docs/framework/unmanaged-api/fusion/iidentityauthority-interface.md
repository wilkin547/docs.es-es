---
description: 'Más información acerca de: interfaz Iidentityauthority ('
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
ms.openlocfilehash: 3064a3d95ebe9a098a7cac0766f18654c6fab8b9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800143"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="5c3cf-103">IIdentityAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c3cf-103">IIdentityAuthority Interface</span></span>

<span data-ttu-id="5c3cf-104">Administra claves de identidad para objetos de código.</span><span class="sxs-lookup"><span data-stu-id="5c3cf-104">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="5c3cf-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5c3cf-105">Methods</span></span>

|<span data-ttu-id="5c3cf-106">Método</span><span class="sxs-lookup"><span data-stu-id="5c3cf-106">Method</span></span>|<span data-ttu-id="5c3cf-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c3cf-107">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="5c3cf-108">Obtiene un valor que indica si las dos instancias de [IDefinitionIdentity](idefinitionidentity-interface.md) especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="5c3cf-108">Gets a value that indicates whether the two specified [IDefinitionIdentity](idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="5c3cf-109">Obtiene un valor que indica si las dos instancias de [IReferenceIdentity](ireferenceidentity-interface.md) especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="5c3cf-109">Gets a value that indicates whether the two specified [IReferenceIdentity](ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="5c3cf-110">Obtiene un valor que indica si las dos representaciones de identidad de definición de cadena especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="5c3cf-110">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="5c3cf-111">Obtiene un valor que indica si las dos representaciones de identidad de referencia de cadena especificadas son iguales.</span><span class="sxs-lookup"><span data-stu-id="5c3cf-111">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="5c3cf-112">Obtiene un puntero a una nueva `IDefinitionIdentity` instancia de que representa el objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="5c3cf-112">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="5c3cf-113">Obtiene un puntero a una nueva `IReferenceIdentity` instancia de que representa el objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="5c3cf-113">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="5c3cf-114">Obtiene una versión de cadena con formato del especificado `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="5c3cf-114">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="5c3cf-115">Rellena el búfer de caracteres anchos especificado con una versión de cadena del especificado `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="5c3cf-115">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="5c3cf-116">Obtiene un valor que indica si las `IDefinitionIdentity` instancias y especificadas `IReferenceIdentity` hacen referencia al mismo objeto de código.</span><span class="sxs-lookup"><span data-stu-id="5c3cf-116">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="5c3cf-117">Obtiene un valor que indica si las cadenas especificadas hacen referencia al mismo objeto de código.</span><span class="sxs-lookup"><span data-stu-id="5c3cf-117">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="5c3cf-118">Obtiene un puntero a una clave de cadena recién creada para el especificado `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="5c3cf-118">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="5c3cf-119">Obtiene un puntero a una clave de cadena recién creada para el especificado `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="5c3cf-119">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="5c3cf-120">Obtiene un valor hash para el especificado `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="5c3cf-120">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="5c3cf-121">Obtiene un valor hash para el especificado `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="5c3cf-121">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="5c3cf-122">Obtiene una versión de cadena con formato del especificado `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="5c3cf-122">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="5c3cf-123">Rellena el búfer de caracteres anchos especificado con una versión de cadena del especificado `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="5c3cf-123">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="5c3cf-124">Obtiene un puntero de interfaz a una `IDefinitionIdentity` instancia de generada a partir de la cadena con formato especificada.</span><span class="sxs-lookup"><span data-stu-id="5c3cf-124">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="5c3cf-125">Obtiene un puntero de interfaz a una `IReferenceIdentity` instancia de generada a partir de la cadena con formato especificada.</span><span class="sxs-lookup"><span data-stu-id="5c3cf-125">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="5c3cf-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c3cf-126">Requirements</span></span>

<span data-ttu-id="5c3cf-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c3cf-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="5c3cf-128">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="5c3cf-128">**Header:** Isolation.h</span></span>

<span data-ttu-id="5c3cf-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c3cf-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5c3cf-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c3cf-130">See also</span></span>

- [<span data-ttu-id="5c3cf-131">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="5c3cf-131">Fusion Interfaces</span></span>](fusion-interfaces.md)

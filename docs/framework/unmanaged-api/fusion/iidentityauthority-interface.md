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
ms.openlocfilehash: 263dc0f9d686440aaa23e359c26db1b4d3d09b1e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375978"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="ce30f-102">IIdentityAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce30f-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="ce30f-103">Administra las claves de identidad para los objetos de código.</span><span class="sxs-lookup"><span data-stu-id="ce30f-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="ce30f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ce30f-104">Methods</span></span>

|<span data-ttu-id="ce30f-105">Método</span><span class="sxs-lookup"><span data-stu-id="ce30f-105">Method</span></span>|<span data-ttu-id="ce30f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce30f-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="ce30f-107">Obtiene un valor que indica si los dos especifica [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instancias son iguales.</span><span class="sxs-lookup"><span data-stu-id="ce30f-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="ce30f-108">Obtiene un valor que indica si los dos especifica [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instancias son iguales.</span><span class="sxs-lookup"><span data-stu-id="ce30f-108">Gets a value that indicates whether the two specified [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="ce30f-109">Obtiene un valor que indica si las dos representaciones de identidad de definición de cadena especificada son iguales.</span><span class="sxs-lookup"><span data-stu-id="ce30f-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="ce30f-110">Obtiene un valor que indica si las dos representaciones de identidad de referencia de la cadena especificada son iguales.</span><span class="sxs-lookup"><span data-stu-id="ce30f-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="ce30f-111">Obtiene un puntero a un nuevo `IDefinitionIdentity` instancia que representa el objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="ce30f-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="ce30f-112">Obtiene un puntero a un nuevo `IReferenceIdentity` instancia que representa el objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="ce30f-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="ce30f-113">Obtiene una versión de cadena con formato del elemento especificado `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ce30f-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="ce30f-114">Llena el búfer de carácter ancho especificado con una versión de cadena del elemento especificado `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ce30f-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="ce30f-115">Obtiene un valor que indica si el texto especificado `IDefinitionIdentity` y `IReferenceIdentity` instancias hacen referencia al mismo objeto de código.</span><span class="sxs-lookup"><span data-stu-id="ce30f-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="ce30f-116">Obtiene un valor que indica si las cadenas especificadas hacen referencia al mismo objeto de código.</span><span class="sxs-lookup"><span data-stu-id="ce30f-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="ce30f-117">Obtiene un puntero a una clave de cadena recién creada para el elemento especificado `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ce30f-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="ce30f-118">Obtiene un puntero a una clave de cadena recién creada para el elemento especificado `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ce30f-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="ce30f-119">Obtiene un valor hash para el elemento especificado `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ce30f-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="ce30f-120">Obtiene un valor hash para el elemento especificado `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ce30f-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="ce30f-121">Obtiene una versión de cadena con formato del elemento especificado `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ce30f-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="ce30f-122">Llena el búfer de carácter ancho especificado con una versión de cadena del elemento especificado `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ce30f-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="ce30f-123">Obtiene un puntero de interfaz a un `IDefinitionIdentity` cadena con formato de instancia generado a partir de la especificada.</span><span class="sxs-lookup"><span data-stu-id="ce30f-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="ce30f-124">Obtiene un puntero de interfaz a un `IReferenceIdentity` cadena con formato de instancia generado a partir de la especificada.</span><span class="sxs-lookup"><span data-stu-id="ce30f-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="ce30f-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce30f-125">Requirements</span></span>

<span data-ttu-id="ce30f-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce30f-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="ce30f-127">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="ce30f-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="ce30f-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce30f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ce30f-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce30f-129">See also</span></span>

- [<span data-ttu-id="ce30f-130">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="ce30f-130">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

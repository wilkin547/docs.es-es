---
title: IIdentityAuthority (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IIdentityAuthority
api_location: fusion.dll
api_type: COM
f1_keywords: IIdentityAuthority
helpviewer_keywords: IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c3f38d932fa0376186e2c22232d21857d5fa128f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="ac474-102">IIdentityAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac474-102">IIdentityAuthority Interface</span></span>
<span data-ttu-id="ac474-103">Administra las claves de identidad para los objetos de código.</span><span class="sxs-lookup"><span data-stu-id="ac474-103">Manages identity keys for code objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ac474-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ac474-104">Methods</span></span>  
  
|<span data-ttu-id="ac474-105">Método</span><span class="sxs-lookup"><span data-stu-id="ac474-105">Method</span></span>|<span data-ttu-id="ac474-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac474-106">Description</span></span>|  
|------------|-----------------|  
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="ac474-107">Obtiene un valor que indica si las dos especificadas [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instancias son iguales.</span><span class="sxs-lookup"><span data-stu-id="ac474-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="ac474-108">Obtiene un valor que indica si las dos especificadas [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instancias son iguales.</span><span class="sxs-lookup"><span data-stu-id="ac474-108">Gets a value that indicates whether the two specified [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="ac474-109">Obtiene un valor que indica si las dos representaciones de identidad de definición de la cadena especificada son iguales.</span><span class="sxs-lookup"><span data-stu-id="ac474-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|  
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="ac474-110">Obtiene un valor que indica si las dos representaciones de identidad de referencia de la cadena especificada son iguales.</span><span class="sxs-lookup"><span data-stu-id="ac474-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|  
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="ac474-111">Obtiene un puntero a una nueva `IDefinitionIdentity` instancia que representa el objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="ac474-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="ac474-112">Obtiene un puntero a una nueva `IReferenceIdentity` instancia que representa el objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="ac474-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="ac474-113">Obtiene una versión de cadena con formato del elemento especificado `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ac474-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="ac474-114">Llena el búfer de carácter ancho especificado con una versión de cadena del elemento especificado `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ac474-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="ac474-115">Obtiene un valor que indica si el texto especificado `IDefinitionIdentity` y `IReferenceIdentity` instancias hacen referencia al mismo objeto de código.</span><span class="sxs-lookup"><span data-stu-id="ac474-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|  
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="ac474-116">Obtiene un valor que indica si las cadenas especificadas hacen referencia al mismo objeto de código.</span><span class="sxs-lookup"><span data-stu-id="ac474-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|  
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="ac474-117">Obtiene un puntero a una clave de cadena recién creada para el elemento especificado `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ac474-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="ac474-118">Obtiene un puntero a una clave de cadena recién creada para el elemento especificado `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ac474-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="ac474-119">Obtiene un valor hash para el elemento especificado `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ac474-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::HashReference`|<span data-ttu-id="ac474-120">Obtiene un valor hash para el elemento especificado `IreferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ac474-120">Gets a hash value for the specified `IreferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="ac474-121">Obtiene una versión de cadena con formato del elemento especificado `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ac474-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="ac474-122">Llena el búfer de carácter ancho especificado con una versión de cadena del elemento especificado `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ac474-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="ac474-123">Obtiene un puntero de interfaz a un `IDefinitionIdentity` instancia generada a partir de lo especificado la cadena con formato.</span><span class="sxs-lookup"><span data-stu-id="ac474-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|  
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="ac474-124">Obtiene un puntero de interfaz a un `IReferenceIdentity` instancia generada a partir de lo especificado la cadena con formato.</span><span class="sxs-lookup"><span data-stu-id="ac474-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac474-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac474-125">Requirements</span></span>  
 <span data-ttu-id="ac474-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac474-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac474-127">**Encabezado:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="ac474-127">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="ac474-128">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac474-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac474-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac474-129">See Also</span></span>  
 [<span data-ttu-id="ac474-130">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="ac474-130">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

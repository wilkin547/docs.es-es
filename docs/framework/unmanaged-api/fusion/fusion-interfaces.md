---
title: Interfaces de Fusion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9226eba1b9f03138180430b2abb960f43f4b4260
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="fusion-interfaces"></a><span data-ttu-id="87515-102">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="87515-102">Fusion Interfaces</span></span>
<span data-ttu-id="87515-103">Esta sección describen las interfaces no administradas que utiliza la API de fusión para tener acceso a las propiedades de recursos de la aplicación y a encontrar las versiones correctas de estos recursos para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="87515-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="87515-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="87515-104">In This Section</span></span>  
 [<span data-ttu-id="87515-105">IAppIdAuthority (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87515-105">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 <span data-ttu-id="87515-106">Proporciona métodos que generan y comparan las identidades de la aplicación y referencias de claves.</span><span class="sxs-lookup"><span data-stu-id="87515-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="87515-107">IAssemblyCache (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87515-107">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 <span data-ttu-id="87515-108">Proporciona una representación de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="87515-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="87515-109">IAssemblyCacheItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87515-109">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 <span data-ttu-id="87515-110">Representa un único ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="87515-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="87515-111">IAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87515-111">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 <span data-ttu-id="87515-112">Representa un enumerador para una matriz de `IAssemblyName` objetos.</span><span class="sxs-lookup"><span data-stu-id="87515-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="87515-113">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87515-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 <span data-ttu-id="87515-114">Proporciona métodos para describir y trabajar con la identidad única de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="87515-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="87515-115">IDefinitionAppId (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87515-115">IDefinitionAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md)  
 <span data-ttu-id="87515-116">Representa un identificador único para el código que define la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="87515-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="87515-117">IDefinitionIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87515-117">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 <span data-ttu-id="87515-118">Representa la firma única del código que define la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="87515-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="87515-119">IEnumDefinitionIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87515-119">IEnumDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="87515-120">Actúa como el enumerador para una colección de `IDefinitionIdentity` objetos.</span><span class="sxs-lookup"><span data-stu-id="87515-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="87515-121">IEnumIDENTITY_ATTRIBUTE (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87515-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)  
 <span data-ttu-id="87515-122">Actúa como un enumerador para los atributos del objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="87515-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="87515-123">IEnumReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87515-123">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 <span data-ttu-id="87515-124">Actúa como un enumerador para una colección de `IReferenceIdentity` objetos.</span><span class="sxs-lookup"><span data-stu-id="87515-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="87515-125">IIdentityAuthority (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87515-125">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 <span data-ttu-id="87515-126">Administra las claves de identidad para los objetos de código.</span><span class="sxs-lookup"><span data-stu-id="87515-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="87515-127">IInstallReferenceEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87515-127">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 <span data-ttu-id="87515-128">Representa un enumerador para los ensamblados instalados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="87515-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="87515-129">IInstallReferenceItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87515-129">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 <span data-ttu-id="87515-130">Representa un elemento instalado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="87515-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="87515-131">IReferenceAppId (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87515-131">IReferenceAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md)  
 <span data-ttu-id="87515-132">Representa una referencia al identificador único para la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="87515-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="87515-133">IReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87515-133">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)  
 <span data-ttu-id="87515-134">Representa una referencia a la firma única de un objeto de código.</span><span class="sxs-lookup"><span data-stu-id="87515-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="87515-135">Referencia</span><span class="sxs-lookup"><span data-stu-id="87515-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="87515-136">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="87515-136">Related Sections</span></span>  
 [<span data-ttu-id="87515-137">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="87515-137">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
  
 [<span data-ttu-id="87515-138">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="87515-138">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [<span data-ttu-id="87515-139">Estructuras de fusión</span><span class="sxs-lookup"><span data-stu-id="87515-139">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)

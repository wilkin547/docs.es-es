---
description: 'Más información sobre: interfaces de fusión'
title: Interfaces de Fusion
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
ms.openlocfilehash: 3b6ca64b40ebc1a7b38129d897059ca628d3914c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761070"
---
# <a name="fusion-interfaces"></a><span data-ttu-id="8c5ad-103">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="8c5ad-103">Fusion Interfaces</span></span>

<span data-ttu-id="8c5ad-104">En esta sección se describen las interfaces no administradas que utiliza la API de fusión para tener acceso a las propiedades de los recursos de una aplicación y para buscar las versiones correctas de los recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-104">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c5ad-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8c5ad-105">In This Section</span></span>  

 [<span data-ttu-id="8c5ad-106">IAppIdAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c5ad-106">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)  
 <span data-ttu-id="8c5ad-107">Proporciona métodos que generan y comparan las claves de las identidades y referencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-107">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="8c5ad-108">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c5ad-108">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)  
 <span data-ttu-id="8c5ad-109">Proporciona una representación de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-109">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="8c5ad-110">IAssemblyCacheItem (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c5ad-110">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)  
 <span data-ttu-id="8c5ad-111">Representa un ensamblado único en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-111">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="8c5ad-112">IAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c5ad-112">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)  
 <span data-ttu-id="8c5ad-113">Representa un enumerador para una matriz de `IAssemblyName` objetos.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-113">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="8c5ad-114">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c5ad-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)  
 <span data-ttu-id="8c5ad-115">Proporciona métodos para describir y trabajar con la identidad única de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-115">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="8c5ad-116">IDefinitionAppId (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c5ad-116">IDefinitionAppId Interface</span></span>](idefinitionappid-interface.md)  
 <span data-ttu-id="8c5ad-117">Representa un identificador único para el código que define la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-117">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="8c5ad-118">IDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c5ad-118">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)  
 <span data-ttu-id="8c5ad-119">Representa la firma única del código que define la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-119">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="8c5ad-120">IEnumDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c5ad-120">IEnumDefinitionIdentity Interface</span></span>](ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="8c5ad-121">Actúa como enumerador para una colección de `IDefinitionIdentity` objetos.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-121">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="8c5ad-122">IEnumIDENTITY_ATTRIBUTE (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c5ad-122">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)  
 <span data-ttu-id="8c5ad-123">Actúa como un enumerador para los atributos del objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-123">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="8c5ad-124">IEnumReferenceIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c5ad-124">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)  
 <span data-ttu-id="8c5ad-125">Actúa como un enumerador para una colección de `IReferenceIdentity` objetos.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-125">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="8c5ad-126">IIdentityAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c5ad-126">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)  
 <span data-ttu-id="8c5ad-127">Administra claves de identidad para objetos de código.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-127">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="8c5ad-128">IInstallReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c5ad-128">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)  
 <span data-ttu-id="8c5ad-129">Representa un enumerador para los ensamblados a los que se hace referencia instalados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-129">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="8c5ad-130">IInstallReferenceItem (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c5ad-130">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)  
 <span data-ttu-id="8c5ad-131">Representa un elemento instalado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-131">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="8c5ad-132">IReferenceAppId (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c5ad-132">IReferenceAppId Interface</span></span>](ireferenceappid-interface.md)  
 <span data-ttu-id="8c5ad-133">Representa una referencia al identificador único de la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-133">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="8c5ad-134">IReferenceIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c5ad-134">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)  
 <span data-ttu-id="8c5ad-135">Representa una referencia a la firma única de un objeto de código.</span><span class="sxs-lookup"><span data-stu-id="8c5ad-135">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8c5ad-136">Referencia</span><span class="sxs-lookup"><span data-stu-id="8c5ad-136">Reference</span></span>  

 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="8c5ad-137">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="8c5ad-137">Related Sections</span></span>  

 [<span data-ttu-id="8c5ad-138">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="8c5ad-138">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)  
  
 [<span data-ttu-id="8c5ad-139">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="8c5ad-139">Fusion Enumerations</span></span>](fusion-enumerations.md)  
  
 [<span data-ttu-id="8c5ad-140">Estructuras de fusión</span><span class="sxs-lookup"><span data-stu-id="8c5ad-140">Fusion Structures</span></span>](fusion-structures.md)

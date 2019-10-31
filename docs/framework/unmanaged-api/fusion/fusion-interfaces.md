---
title: Interfaces de Fusion
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
ms.openlocfilehash: 81c66825e69d9526abddfe06133426a2274ad08f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108195"
---
# <a name="fusion-interfaces"></a><span data-ttu-id="2ad0c-102">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="2ad0c-102">Fusion Interfaces</span></span>
<span data-ttu-id="2ad0c-103">En esta sección se describen las interfaces no administradas que utiliza la API de fusión para tener acceso a las propiedades de los recursos de una aplicación y para buscar las versiones correctas de los recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ad0c-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2ad0c-104">In This Section</span></span>  
 [<span data-ttu-id="2ad0c-105">IAppIdAuthority (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ad0c-105">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)  
 <span data-ttu-id="2ad0c-106">Proporciona métodos que generan y comparan las claves de las identidades y referencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="2ad0c-107">IAssemblyCache (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ad0c-107">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)  
 <span data-ttu-id="2ad0c-108">Proporciona una representación de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="2ad0c-109">IAssemblyCacheItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ad0c-109">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)  
 <span data-ttu-id="2ad0c-110">Representa un ensamblado único en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="2ad0c-111">IAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ad0c-111">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)  
 <span data-ttu-id="2ad0c-112">Representa un enumerador para una matriz de objetos `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="2ad0c-113">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ad0c-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)  
 <span data-ttu-id="2ad0c-114">Proporciona métodos para describir y trabajar con la identidad única de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="2ad0c-115">IDefinitionAppId (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ad0c-115">IDefinitionAppId Interface</span></span>](idefinitionappid-interface.md)  
 <span data-ttu-id="2ad0c-116">Representa un identificador único para el código que define la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="2ad0c-117">IDefinitionIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ad0c-117">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)  
 <span data-ttu-id="2ad0c-118">Representa la firma única del código que define la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="2ad0c-119">IEnumDefinitionIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ad0c-119">IEnumDefinitionIdentity Interface</span></span>](ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="2ad0c-120">Actúa como enumerador para una colección de objetos `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="2ad0c-121">IEnumIDENTITY_ATTRIBUTE (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ad0c-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)  
 <span data-ttu-id="2ad0c-122">Actúa como un enumerador para los atributos del objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="2ad0c-123">IEnumReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ad0c-123">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)  
 <span data-ttu-id="2ad0c-124">Actúa como un enumerador para una colección de objetos `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="2ad0c-125">IIdentityAuthority (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ad0c-125">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)  
 <span data-ttu-id="2ad0c-126">Administra claves de identidad para objetos de código.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="2ad0c-127">IInstallReferenceEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ad0c-127">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)  
 <span data-ttu-id="2ad0c-128">Representa un enumerador para los ensamblados a los que se hace referencia instalados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="2ad0c-129">IInstallReferenceItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ad0c-129">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)  
 <span data-ttu-id="2ad0c-130">Representa un elemento instalado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="2ad0c-131">IReferenceAppId (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ad0c-131">IReferenceAppId Interface</span></span>](ireferenceappid-interface.md)  
 <span data-ttu-id="2ad0c-132">Representa una referencia al identificador único de la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="2ad0c-133">IReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ad0c-133">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)  
 <span data-ttu-id="2ad0c-134">Representa una referencia a la firma única de un objeto de código.</span><span class="sxs-lookup"><span data-stu-id="2ad0c-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2ad0c-135">Referencia</span><span class="sxs-lookup"><span data-stu-id="2ad0c-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="2ad0c-136">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="2ad0c-136">Related Sections</span></span>  
 [<span data-ttu-id="2ad0c-137">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="2ad0c-137">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)  
  
 [<span data-ttu-id="2ad0c-138">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="2ad0c-138">Fusion Enumerations</span></span>](fusion-enumerations.md)  
  
 [<span data-ttu-id="2ad0c-139">Estructuras de fusión</span><span class="sxs-lookup"><span data-stu-id="2ad0c-139">Fusion Structures</span></span>](fusion-structures.md)

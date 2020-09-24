---
title: Configurar clases de criptografía
description: Comprenda cómo los administradores de equipos pueden configurar los algoritmos criptográficos y las implementaciones de algoritmo predeterminados que usan .NET y las aplicaciones.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: 5262dfca914fd5306297ea9535bcef3d2088d107
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165213"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="21494-103">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="21494-103">Configuring Cryptography Classes</span></span>

<span data-ttu-id="21494-104">El Windows SDK permite a los administradores del equipo configurar los algoritmos criptográficos y las implementaciones de algoritmo predeterminados que usan las aplicaciones .NET Framework y escritas correctamente.</span><span class="sxs-lookup"><span data-stu-id="21494-104">The Windows SDK allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="21494-105">Por ejemplo, una empresa que tenga su propia implementación de un algoritmo criptográfico puede hacer que esa implementación sea la predeterminada en lugar de la implementación incluida en el Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="21494-105">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="21494-106">Aunque las aplicaciones administradas que usan criptografía siempre pueden optar por enlazar explícitamente a una implementación concreta, se recomienda que creen objetos criptográficos mediante el sistema de configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="21494-106">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="21494-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="21494-107">In This Section</span></span>  

 [<span data-ttu-id="21494-108">Asignar nombres de algoritmo a clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="21494-108">Mapping Algorithm Names to Cryptography Classes</span></span>](map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="21494-109">Describe cómo asignar un nombre de algoritmo a una clase de criptografía.</span><span class="sxs-lookup"><span data-stu-id="21494-109">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="21494-110">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="21494-110">Mapping Object Identifiers to Cryptography Algorithms</span></span>](map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="21494-111">Describe cómo asignar un identificador de objeto a un algoritmo criptográfico.</span><span class="sxs-lookup"><span data-stu-id="21494-111">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="21494-112">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="21494-112">Related Sections</span></span>  

 [<span data-ttu-id="21494-113">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="21494-113">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)  
 <span data-ttu-id="21494-114">Proporciona información general sobre los servicios criptográficos proporcionados por el Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="21494-114">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="21494-115">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="21494-115">Cryptography Settings Schema</span></span>](./file-schema/cryptography/index.md)  
 <span data-ttu-id="21494-116">Describe los elementos que asignan nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="21494-116">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

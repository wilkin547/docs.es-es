---
title: Configurar clases de criptografía
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: 77f26405792ac782f2a04e174e8165a09b7f22f6
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567337"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="9567a-102">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="9567a-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="9567a-103">El Windows SDK permite a los administradores del equipo configurar los algoritmos criptográficos y las implementaciones de algoritmo predeterminados que usan las aplicaciones .NET Framework y escritas correctamente.</span><span class="sxs-lookup"><span data-stu-id="9567a-103">The Windows SDK allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="9567a-104">Por ejemplo, una empresa que tenga su propia implementación de un algoritmo criptográfico puede hacer que esa implementación sea la predeterminada en lugar de la implementación incluida en el Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="9567a-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="9567a-105">Aunque las aplicaciones administradas que usan criptografía siempre pueden optar por enlazar explícitamente a una implementación concreta, se recomienda que creen objetos criptográficos mediante el sistema de configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="9567a-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9567a-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9567a-106">In This Section</span></span>  
 [<span data-ttu-id="9567a-107">Asignar nombres de algoritmo a clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="9567a-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="9567a-108">Describe cómo asignar un nombre de algoritmo a una clase de criptografía.</span><span class="sxs-lookup"><span data-stu-id="9567a-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="9567a-109">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="9567a-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="9567a-110">Describe cómo asignar un identificador de objeto a un algoritmo criptográfico.</span><span class="sxs-lookup"><span data-stu-id="9567a-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9567a-111">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="9567a-111">Related Sections</span></span>  
 [<span data-ttu-id="9567a-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="9567a-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="9567a-113">Proporciona información general sobre los servicios criptográficos proporcionados por el Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="9567a-113">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="9567a-114">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="9567a-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="9567a-115">Describe los elementos que asignan nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="9567a-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

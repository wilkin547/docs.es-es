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
ms.openlocfilehash: e53f4c5c9e24fb25b43b7f27b80ab984214eeac2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "69927766"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="1ae60-102">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="1ae60-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="1ae60-103">El Windows SDK permite a los administradores del equipo configurar los algoritmos criptográficos y las implementaciones de algoritmo predeterminados que usan las aplicaciones .NET Framework y escritas correctamente.</span><span class="sxs-lookup"><span data-stu-id="1ae60-103">The Windows SDK allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="1ae60-104">Por ejemplo, una empresa que tenga su propia implementación de un algoritmo criptográfico puede hacer que esa implementación sea la predeterminada en lugar de la implementación incluida en el Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="1ae60-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="1ae60-105">Aunque las aplicaciones administradas que usan criptografía siempre pueden optar por enlazar explícitamente a una implementación concreta, se recomienda que creen objetos criptográficos mediante el sistema de configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="1ae60-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ae60-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1ae60-106">In This Section</span></span>  
 [<span data-ttu-id="1ae60-107">Asignar nombres de algoritmo a clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="1ae60-107">Mapping Algorithm Names to Cryptography Classes</span></span>](map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="1ae60-108">Describe cómo asignar un nombre de algoritmo a una clase de criptografía.</span><span class="sxs-lookup"><span data-stu-id="1ae60-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="1ae60-109">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="1ae60-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="1ae60-110">Describe cómo asignar un identificador de objeto a un algoritmo criptográfico.</span><span class="sxs-lookup"><span data-stu-id="1ae60-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1ae60-111">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="1ae60-111">Related Sections</span></span>  
 [<span data-ttu-id="1ae60-112">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="1ae60-112">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)  
 <span data-ttu-id="1ae60-113">Proporciona información general sobre los servicios criptográficos proporcionados por el Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="1ae60-113">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="1ae60-114">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="1ae60-114">Cryptography Settings Schema</span></span>](./file-schema/cryptography/index.md)  
 <span data-ttu-id="1ae60-115">Describe los elementos que asignan nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="1ae60-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

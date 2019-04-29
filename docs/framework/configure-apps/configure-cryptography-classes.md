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
ms.openlocfilehash: ba11eed316e227ceae4cb5acecb2b081fa8868f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705537"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="2dfdc-102">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="2dfdc-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="2dfdc-103">El [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] permite a los administradores de equipo configurar los algoritmos criptográficos predeterminados y las implementaciones de algoritmos que usan .NET Framework y aplicaciones escritas de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="2dfdc-103">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="2dfdc-104">Por ejemplo, una empresa que tiene su propia implementación de un algoritmo criptográfico puede hacer que la implementación el valor predeterminado en lugar de la implementación se incluye en el [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2dfdc-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span> <span data-ttu-id="2dfdc-105">Aunque siempre pueden elegir las aplicaciones administradas que utilizan criptografía enlazar explícitamente una implementación determinada, se recomienda que creen objetos criptográficos mediante el sistema de configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="2dfdc-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2dfdc-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2dfdc-106">In This Section</span></span>  
 [<span data-ttu-id="2dfdc-107">Asignar nombres de algoritmo a clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="2dfdc-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="2dfdc-108">Describe cómo asignar un nombre de algoritmo a una clase de criptografía.</span><span class="sxs-lookup"><span data-stu-id="2dfdc-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="2dfdc-109">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="2dfdc-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="2dfdc-110">Describe cómo asignar un identificador de objeto a un algoritmo de criptografía.</span><span class="sxs-lookup"><span data-stu-id="2dfdc-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2dfdc-111">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="2dfdc-111">Related Sections</span></span>  
 [<span data-ttu-id="2dfdc-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="2dfdc-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="2dfdc-113">Proporciona información general de servicios criptográficos proporcionados por el [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2dfdc-113">Provides an overview of cryptographic services provided by the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span>  
  
 [<span data-ttu-id="2dfdc-114">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="2dfdc-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="2dfdc-115">Describe los elementos que asignan nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="2dfdc-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

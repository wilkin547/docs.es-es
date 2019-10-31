---
title: Proteger aplicaciones de ADO.NET
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: c99c56afca475caafe32cca3f50d074fb82e0e00
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73196720"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="4fd3e-102">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4fd3e-102">Securing ADO.NET Applications</span></span>
<span data-ttu-id="4fd3e-103">Para escribir una aplicación de ADO.NET segura es necesario algo más que evitar los errores de codificación más comunes, como no validar los datos proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="4fd3e-104">Una aplicación que tiene acceso a datos tiene muchos puntos débiles potenciales que un agresor puede aprovechar para obtener, manipular o destruir datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="4fd3e-105">Por eso es importante comprender todos los aspectos de la seguridad, desde el proceso de modelo de amenazas durante la fase de diseño de su aplicación hasta la implementación y el posterior mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
 <span data-ttu-id="4fd3e-106">.NET Framework ofrece muchas clases, servicios y herramientas que resultan muy útiles para proteger y administrar aplicaciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="4fd3e-107">Common Language Runtime (CLR) proporciona un entorno de seguridad de tipos en el que ejecutar el código, junto con la seguridad de acceso del código (CAS) para restringir aún más los permisos del código administrado.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="4fd3e-108">Si se siguen las recomendaciones de codificación del acceso seguro a datos, se reduce el daño que podría provocar un posible agresor.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
 <span data-ttu-id="4fd3e-109">El código seguro no protege de la vulnerabilidad de seguridad que provoca el propio usuario cuando trabaja con recursos no administrados como bases de datos.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="4fd3e-110">La mayoría de las bases de datos, como SQL Server, tienen sus propios sistemas de seguridad, que contribuyen a mejorarla cuando se implementan correctamente.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="4fd3e-111">Sin embargo, incluso un origen de datos con un robusto sistema de seguridad puede sufrir un ataque si no se ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4fd3e-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4fd3e-112">In This Section</span></span>  
 [<span data-ttu-id="4fd3e-113">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="4fd3e-113">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="4fd3e-114">Proporciona recomendaciones para diseñar aplicaciones seguras de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="4fd3e-115">Acceso seguro a datos</span><span class="sxs-lookup"><span data-stu-id="4fd3e-115">Secure Data Access</span></span>](secure-data-access.md)  
 <span data-ttu-id="4fd3e-116">Describe cómo trabajar con datos de un origen de datos protegido.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="4fd3e-117">Aplicaciones cliente seguras</span><span class="sxs-lookup"><span data-stu-id="4fd3e-117">Secure Client Applications</span></span>](secure-client-applications.md)  
 <span data-ttu-id="4fd3e-118">Describe consideraciones de seguridad para aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="4fd3e-119">Seguridad de acceso del código y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4fd3e-119">Code Access Security and ADO.NET</span></span>](code-access-security.md)  
 <span data-ttu-id="4fd3e-120">Describe cómo se puede proteger el código de ADO.NET mediante la seguridad de acceso del código.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="4fd3e-121">También explica cómo trabajar con confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="4fd3e-122">Privacidad y seguridad de datos</span><span class="sxs-lookup"><span data-stu-id="4fd3e-122">Privacy and Data Security</span></span>](privacy-and-data-security.md)  
 <span data-ttu-id="4fd3e-123">Describe las opciones de cifrado para las aplicaciones de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4fd3e-124">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="4fd3e-124">Related Sections</span></span>  
 [<span data-ttu-id="4fd3e-125">Seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4fd3e-125">SQL Server Security</span></span>](./sql/sql-server-security.md)  
 <span data-ttu-id="4fd3e-126">Describe las características de seguridad de SQL Server desde la perspectiva del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-126">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="4fd3e-127">Consideraciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="4fd3e-127">Security Considerations</span></span>](./ef/security-considerations.md)  
 <span data-ttu-id="4fd3e-128">Describe la seguridad de las aplicaciones de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-128">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="4fd3e-129">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4fd3e-129">Security</span></span>](../../../standard/security/index.md)  
 <span data-ttu-id="4fd3e-130">Contiene vínculos a temas en los que describen todos los aspectos de la seguridad en .NET.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-130">Contains links to topics describing all aspects of security in .NET.</span></span>  
  
 <span data-ttu-id="4fd3e-131">[Herramientas de seguridad](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="4fd3e-131">[Security Tools](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span></span>  
 <span data-ttu-id="4fd3e-132">Herramientas de .NET Framework para proteger y administrar las directivas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-132">.NET Framework tools for securing and administering security policy.</span></span>  
  
 <span data-ttu-id="4fd3e-133">[Recursos para crear aplicaciones seguras](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4fd3e-133">[Resources for Creating Secure Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span></span>  
 <span data-ttu-id="4fd3e-134">Proporciona vínculos a temas para crear aplicaciones seguras.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-134">Provides links to topics for creating secure applications.</span></span>  
  
 [<span data-ttu-id="4fd3e-135">Bibliografía sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="4fd3e-135">Security Bibliography</span></span>](/visualstudio/ide/securing-applications)  
 <span data-ttu-id="4fd3e-136">Proporciona vínculos a recursos externos disponibles en línea e impresos.</span><span class="sxs-lookup"><span data-stu-id="4fd3e-136">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fd3e-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fd3e-137">See also</span></span>

- [<span data-ttu-id="4fd3e-138">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4fd3e-138">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="4fd3e-139">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4fd3e-139">ADO.NET Overview</span></span>](ado-net-overview.md)

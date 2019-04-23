---
title: Proteger aplicaciones de ADO.NET
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: 32d3de15242aaf9cfacd9371289a5a0a675f884b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149388"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="7d8e8-102">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7d8e8-102">Securing ADO.NET Applications</span></span>
<span data-ttu-id="7d8e8-103">Para escribir una aplicación de ADO.NET segura es necesario algo más que evitar los errores de codificación más comunes, como no validar los datos proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="7d8e8-104">Una aplicación que tiene acceso a datos tiene muchos puntos débiles potenciales que un agresor puede aprovechar para obtener, manipular o destruir datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="7d8e8-105">Por eso es importante comprender todos los aspectos de la seguridad, desde el proceso de modelo de amenazas durante la fase de diseño de su aplicación hasta la implementación y el posterior mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
 <span data-ttu-id="7d8e8-106">.NET Framework ofrece muchas clases, servicios y herramientas que resultan muy útiles para proteger y administrar aplicaciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="7d8e8-107">Common Language Runtime (CLR) proporciona un entorno de seguridad de tipos en el que ejecutar el código, junto con la seguridad de acceso del código (CAS) para restringir aún más los permisos del código administrado.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="7d8e8-108">Si se siguen las recomendaciones de codificación del acceso seguro a datos, se reduce el daño que podría provocar un posible agresor.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
 <span data-ttu-id="7d8e8-109">El código seguro no protege de la vulnerabilidad de seguridad que provoca el propio usuario cuando trabaja con recursos no administrados como bases de datos.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="7d8e8-110">La mayoría de las bases de datos, como SQL Server, tienen sus propios sistemas de seguridad, que contribuyen a mejorarla cuando se implementan correctamente.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="7d8e8-111">Sin embargo, incluso un origen de datos con un robusto sistema de seguridad puede sufrir un ataque si no se ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7d8e8-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7d8e8-112">In This Section</span></span>  
 [<span data-ttu-id="7d8e8-113">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="7d8e8-113">Security Overview</span></span>](../../../../docs/framework/data/adonet/security-overview.md)  
 <span data-ttu-id="7d8e8-114">Proporciona recomendaciones para diseñar aplicaciones seguras de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="7d8e8-115">Acceso seguro a datos</span><span class="sxs-lookup"><span data-stu-id="7d8e8-115">Secure Data Access</span></span>](../../../../docs/framework/data/adonet/secure-data-access.md)  
 <span data-ttu-id="7d8e8-116">Describe cómo trabajar con datos de un origen de datos protegido.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="7d8e8-117">Aplicaciones cliente seguras</span><span class="sxs-lookup"><span data-stu-id="7d8e8-117">Secure Client Applications</span></span>](../../../../docs/framework/data/adonet/secure-client-applications.md)  
 <span data-ttu-id="7d8e8-118">Describe consideraciones de seguridad para aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="7d8e8-119">Seguridad de acceso del código y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7d8e8-119">Code Access Security and ADO.NET</span></span>](../../../../docs/framework/data/adonet/code-access-security.md)  
 <span data-ttu-id="7d8e8-120">Describe cómo se puede proteger el código de ADO.NET mediante la seguridad de acceso del código.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="7d8e8-121">También explica cómo trabajar con confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="7d8e8-122">Privacidad y seguridad de datos</span><span class="sxs-lookup"><span data-stu-id="7d8e8-122">Privacy and Data Security</span></span>](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 <span data-ttu-id="7d8e8-123">Describe las opciones de cifrado para las aplicaciones de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7d8e8-124">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="7d8e8-124">Related Sections</span></span>  
 [<span data-ttu-id="7d8e8-125">Seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d8e8-125">SQL Server Security</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 <span data-ttu-id="7d8e8-126">Describe las características de seguridad de SQL Server desde la perspectiva del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-126">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="7d8e8-127">Consideraciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="7d8e8-127">Security Considerations</span></span>](../../../../docs/framework/data/adonet/ef/security-considerations.md)  
 <span data-ttu-id="7d8e8-128">Describe la seguridad de las aplicaciones de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-128">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="7d8e8-129">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7d8e8-129">Security</span></span>](../../../../docs/standard/security/index.md)  
 <span data-ttu-id="7d8e8-130">Contiene vínculos a temas en los que describen todos los aspectos de la seguridad en .NET.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-130">Contains links to topics describing all aspects of security in .NET.</span></span>  
  
 <span data-ttu-id="7d8e8-131">[Herramientas de seguridad](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="7d8e8-131">[Security Tools](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span></span>  
 <span data-ttu-id="7d8e8-132">Herramientas de .NET Framework para proteger y administrar las directivas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-132">.NET Framework tools for securing and administering security policy.</span></span>  
  
 <span data-ttu-id="7d8e8-133">[Recursos para crear aplicaciones seguras](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7d8e8-133">[Resources for Creating Secure Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span></span>  
 <span data-ttu-id="7d8e8-134">Proporciona vínculos a temas para crear aplicaciones seguras.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-134">Provides links to topics for creating secure applications.</span></span>  
  
 [<span data-ttu-id="7d8e8-135">Bibliografía sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="7d8e8-135">Security Bibliography</span></span>](/visualstudio/ide/security-bibliography)  
 <span data-ttu-id="7d8e8-136">Proporciona vínculos a recursos externos disponibles en línea e impresos.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-136">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d8e8-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d8e8-137">See also</span></span>

- [<span data-ttu-id="7d8e8-138">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7d8e8-138">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
- [<span data-ttu-id="7d8e8-139">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="7d8e8-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

---
title: Proteger aplicaciones
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: af184f64b43c2d3dc39f8c0add08940d3b002c24
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550760"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="a14ff-102">Protección de aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a14ff-102">Securing ADO.NET applications</span></span>

<span data-ttu-id="a14ff-103">Para escribir una aplicación de ADO.NET segura es necesario algo más que evitar los errores de codificación más comunes, como no validar los datos proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a14ff-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="a14ff-104">Una aplicación que tiene acceso a los datos tiene muchos puntos de error potenciales que un atacante puede aprovechar para recuperar, manipular o destruir información confidencial.</span><span class="sxs-lookup"><span data-stu-id="a14ff-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="a14ff-105">Por eso es importante comprender todos los aspectos de la seguridad, desde el proceso de modelo de amenazas durante la fase de diseño de su aplicación hasta la implementación y el posterior mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="a14ff-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
<span data-ttu-id="a14ff-106">.NET Framework ofrece muchas clases, servicios y herramientas que resultan muy útiles para proteger y administrar aplicaciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="a14ff-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="a14ff-107">Common Language Runtime (CLR) proporciona un entorno de seguridad de tipos en el que ejecutar el código, junto con la seguridad de acceso del código (CAS) para restringir aún más los permisos del código administrado.</span><span class="sxs-lookup"><span data-stu-id="a14ff-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="a14ff-108">Si se siguen las recomendaciones de codificación del acceso seguro a datos, se reduce el daño que podría provocar un posible agresor.</span><span class="sxs-lookup"><span data-stu-id="a14ff-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
<span data-ttu-id="a14ff-109">El código seguro no protege de la vulnerabilidad de seguridad que provoca el propio usuario cuando trabaja con recursos no administrados como bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a14ff-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="a14ff-110">La mayoría de las bases de datos, como SQL Server, tienen sus propios sistemas de seguridad, que contribuyen a mejorarla cuando se implementan correctamente.</span><span class="sxs-lookup"><span data-stu-id="a14ff-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="a14ff-111">Sin embargo, incluso un origen de datos con un robusto sistema de seguridad puede sufrir un ataque si no se ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a14ff-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a14ff-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a14ff-112">In this section</span></span>

 [<span data-ttu-id="a14ff-113">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="a14ff-113">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="a14ff-114">Proporciona recomendaciones para diseñar aplicaciones seguras de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="a14ff-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="a14ff-115">Acceso seguro a datos</span><span class="sxs-lookup"><span data-stu-id="a14ff-115">Secure Data Access</span></span>](secure-data-access.md)  
 <span data-ttu-id="a14ff-116">Describe cómo trabajar con datos de un origen de datos protegido.</span><span class="sxs-lookup"><span data-stu-id="a14ff-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="a14ff-117">Aplicaciones cliente seguras</span><span class="sxs-lookup"><span data-stu-id="a14ff-117">Secure Client Applications</span></span>](secure-client-applications.md)  
 <span data-ttu-id="a14ff-118">Describe consideraciones de seguridad para aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="a14ff-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="a14ff-119">Seguridad de acceso del código y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a14ff-119">Code Access Security and ADO.NET</span></span>](code-access-security.md)  
 <span data-ttu-id="a14ff-120">Describe cómo se puede proteger el código de ADO.NET mediante la seguridad de acceso del código.</span><span class="sxs-lookup"><span data-stu-id="a14ff-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="a14ff-121">También explica cómo trabajar con confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a14ff-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="a14ff-122">Privacidad y seguridad de datos</span><span class="sxs-lookup"><span data-stu-id="a14ff-122">Privacy and Data Security</span></span>](privacy-and-data-security.md)  
 <span data-ttu-id="a14ff-123">Describe las opciones de cifrado para las aplicaciones de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="a14ff-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a14ff-124">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="a14ff-124">Related sections</span></span>

 [<span data-ttu-id="a14ff-125">Guía de seguridad de DataSet y DataTable</span><span class="sxs-lookup"><span data-stu-id="a14ff-125">DataSet and DataTable security guidance</span></span>](dataset-datatable-dataview/security-guidance.md)  
 <span data-ttu-id="a14ff-126">Proporciona instrucciones de seguridad para <xref:System.Data.DataSet> y <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="a14ff-126">Provides security guidance for <xref:System.Data.DataSet> and <xref:System.Data.DataTable>.</span></span>

 [<span data-ttu-id="a14ff-127">Seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a14ff-127">SQL Server Security</span></span>](./sql/sql-server-security.md)  
 <span data-ttu-id="a14ff-128">Describe las características de seguridad de SQL Server desde la perspectiva del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="a14ff-128">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="a14ff-129">Consideraciones sobre la seguridad</span><span class="sxs-lookup"><span data-stu-id="a14ff-129">Security Considerations</span></span>](./ef/security-considerations.md)  
 <span data-ttu-id="a14ff-130">Describe la seguridad de las aplicaciones de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="a14ff-130">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="a14ff-131">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a14ff-131">Security</span></span>](../../../standard/security/index.md)  
 <span data-ttu-id="a14ff-132">Contiene vínculos a artículos en los que se describen todos los aspectos de seguridad de .NET.</span><span class="sxs-lookup"><span data-stu-id="a14ff-132">Contains links to articles describing all aspects of security in .NET.</span></span>  
  
 <span data-ttu-id="a14ff-133">[Herramientas de seguridad](/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="a14ff-133">[Security Tools](/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span></span>  
 <span data-ttu-id="a14ff-134">Herramientas de .NET Framework para proteger y administrar las directivas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a14ff-134">.NET Framework tools for securing and administering security policy.</span></span>  
  
 <span data-ttu-id="a14ff-135">[Recursos para crear aplicaciones seguras](/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a14ff-135">[Resources for Creating Secure Applications](/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span></span>  
 <span data-ttu-id="a14ff-136">Proporciona vínculos a artículos para crear aplicaciones seguras.</span><span class="sxs-lookup"><span data-stu-id="a14ff-136">Provides links to articles for creating secure applications.</span></span>  
  
 [<span data-ttu-id="a14ff-137">Bibliografía sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="a14ff-137">Security Bibliography</span></span>](/visualstudio/ide/securing-applications)  
 <span data-ttu-id="a14ff-138">Proporciona vínculos a recursos externos disponibles en línea e impresos.</span><span class="sxs-lookup"><span data-stu-id="a14ff-138">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a14ff-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="a14ff-139">See also</span></span>

- [<span data-ttu-id="a14ff-140">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a14ff-140">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="a14ff-141">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a14ff-141">ADO.NET Overview</span></span>](ado-net-overview.md)

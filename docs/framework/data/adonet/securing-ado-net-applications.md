---
description: Más información acerca de cómo proteger aplicaciones ADO.NET
title: Proteger aplicaciones
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: 4e4d219d1f4249846943d019e174abd6d43687c7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718881"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="560f6-103">Protección de aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="560f6-103">Securing ADO.NET applications</span></span>

<span data-ttu-id="560f6-104">Para escribir una aplicación de ADO.NET segura es necesario algo más que evitar los errores de codificación más comunes, como no validar los datos proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="560f6-104">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="560f6-105">Una aplicación que tiene acceso a los datos tiene muchos puntos de error potenciales que un atacante puede aprovechar para recuperar, manipular o destruir información confidencial.</span><span class="sxs-lookup"><span data-stu-id="560f6-105">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="560f6-106">Por eso es importante comprender todos los aspectos de la seguridad, desde el proceso de modelo de amenazas durante la fase de diseño de su aplicación hasta la implementación y el posterior mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="560f6-106">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
<span data-ttu-id="560f6-107">.NET Framework ofrece muchas clases, servicios y herramientas que resultan muy útiles para proteger y administrar aplicaciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="560f6-107">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="560f6-108">Common Language Runtime (CLR) proporciona un entorno de seguridad de tipos en el que ejecutar el código, junto con la seguridad de acceso del código (CAS) para restringir aún más los permisos del código administrado.</span><span class="sxs-lookup"><span data-stu-id="560f6-108">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="560f6-109">Si se siguen las recomendaciones de codificación del acceso seguro a datos, se reduce el daño que podría provocar un posible agresor.</span><span class="sxs-lookup"><span data-stu-id="560f6-109">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
<span data-ttu-id="560f6-110">El código seguro no protege de la vulnerabilidad de seguridad que provoca el propio usuario cuando trabaja con recursos no administrados como bases de datos.</span><span class="sxs-lookup"><span data-stu-id="560f6-110">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="560f6-111">La mayoría de las bases de datos, como SQL Server, tienen sus propios sistemas de seguridad, que contribuyen a mejorarla cuando se implementan correctamente.</span><span class="sxs-lookup"><span data-stu-id="560f6-111">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="560f6-112">Sin embargo, incluso un origen de datos con un robusto sistema de seguridad puede sufrir un ataque si no se ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="560f6-112">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="560f6-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="560f6-113">In this section</span></span>

 [<span data-ttu-id="560f6-114">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="560f6-114">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="560f6-115">Proporciona recomendaciones para diseñar aplicaciones seguras de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="560f6-115">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="560f6-116">Acceso seguro a datos</span><span class="sxs-lookup"><span data-stu-id="560f6-116">Secure Data Access</span></span>](secure-data-access.md)  
 <span data-ttu-id="560f6-117">Describe cómo trabajar con datos de un origen de datos protegido.</span><span class="sxs-lookup"><span data-stu-id="560f6-117">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="560f6-118">Aplicaciones cliente seguras</span><span class="sxs-lookup"><span data-stu-id="560f6-118">Secure Client Applications</span></span>](secure-client-applications.md)  
 <span data-ttu-id="560f6-119">Describe consideraciones de seguridad para aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="560f6-119">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="560f6-120">Seguridad de acceso del código y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="560f6-120">Code Access Security and ADO.NET</span></span>](code-access-security.md)  
 <span data-ttu-id="560f6-121">Describe cómo se puede proteger el código de ADO.NET mediante la seguridad de acceso del código.</span><span class="sxs-lookup"><span data-stu-id="560f6-121">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="560f6-122">También explica cómo trabajar con confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="560f6-122">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="560f6-123">Privacidad y seguridad de datos</span><span class="sxs-lookup"><span data-stu-id="560f6-123">Privacy and Data Security</span></span>](privacy-and-data-security.md)  
 <span data-ttu-id="560f6-124">Describe las opciones de cifrado para las aplicaciones de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="560f6-124">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="560f6-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="560f6-125">Related sections</span></span>

 [<span data-ttu-id="560f6-126">Guía de seguridad de DataSet y DataTable</span><span class="sxs-lookup"><span data-stu-id="560f6-126">DataSet and DataTable security guidance</span></span>](dataset-datatable-dataview/security-guidance.md)  
 <span data-ttu-id="560f6-127">Proporciona instrucciones de seguridad para <xref:System.Data.DataSet> y <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="560f6-127">Provides security guidance for <xref:System.Data.DataSet> and <xref:System.Data.DataTable>.</span></span>

 [<span data-ttu-id="560f6-128">Seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="560f6-128">SQL Server Security</span></span>](./sql/sql-server-security.md)  
 <span data-ttu-id="560f6-129">Describe las características de seguridad de SQL Server desde la perspectiva del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="560f6-129">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="560f6-130">Consideraciones sobre la seguridad</span><span class="sxs-lookup"><span data-stu-id="560f6-130">Security Considerations</span></span>](./ef/security-considerations.md)  
 <span data-ttu-id="560f6-131">Describe la seguridad de las aplicaciones de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="560f6-131">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="560f6-132">Seguridad</span><span class="sxs-lookup"><span data-stu-id="560f6-132">Security</span></span>](../../../standard/security/index.md)  
 <span data-ttu-id="560f6-133">Contiene vínculos a artículos en los que se describen todos los aspectos de seguridad de .NET.</span><span class="sxs-lookup"><span data-stu-id="560f6-133">Contains links to articles describing all aspects of security in .NET.</span></span>  
  
 <span data-ttu-id="560f6-134">[Herramientas de seguridad](/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="560f6-134">[Security Tools](/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span></span>  
 <span data-ttu-id="560f6-135">Herramientas de .NET Framework para proteger y administrar las directivas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="560f6-135">.NET Framework tools for securing and administering security policy.</span></span>  
  
 <span data-ttu-id="560f6-136">[Recursos para crear aplicaciones seguras](/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="560f6-136">[Resources for Creating Secure Applications](/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span></span>  
 <span data-ttu-id="560f6-137">Proporciona vínculos a artículos para crear aplicaciones seguras.</span><span class="sxs-lookup"><span data-stu-id="560f6-137">Provides links to articles for creating secure applications.</span></span>  
  
 [<span data-ttu-id="560f6-138">Bibliografía sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="560f6-138">Security Bibliography</span></span>](/visualstudio/ide/securing-applications)  
 <span data-ttu-id="560f6-139">Proporciona vínculos a recursos externos disponibles en línea e impresos.</span><span class="sxs-lookup"><span data-stu-id="560f6-139">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="560f6-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="560f6-140">See also</span></span>

- [<span data-ttu-id="560f6-141">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="560f6-141">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="560f6-142">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="560f6-142">ADO.NET Overview</span></span>](ado-net-overview.md)

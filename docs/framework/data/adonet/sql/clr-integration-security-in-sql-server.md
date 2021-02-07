---
description: 'Más información sobre: seguridad de la integración CLR en SQL Server'
title: Seguridad de integración de CLR en SQL Server
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: 5de552c0f5b869712d2038b53abd50b8ded04747
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718543"
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="e133e-103">Seguridad de integración de CLR en SQL Server</span><span class="sxs-lookup"><span data-stu-id="e133e-103">CLR Integration Security in SQL Server</span></span>

<span data-ttu-id="e133e-104">Microsoft SQL Server proporciona la integración del componente Common Language Runtime (CLR) de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e133e-104">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="e133e-105">La integración de CLR permite escribir procedimientos almacenados, desencadenadores, tipos definidos por el usuario, funciones definidas por el usuario, agregados definidos por el usuario y funciones con valores de tabla de secuencias, mediante el uso de cualquier lenguaje de .NET Framework, como Microsoft Visual Basic .NET o Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="e133e-105">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="e133e-106">El CLR admite un modelo de seguridad llamado seguridad de acceso del código (CAS) para el código administrado.</span><span class="sxs-lookup"><span data-stu-id="e133e-106">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="e133e-107">En este modelo, se conceden permisos a los ensamblados en función de la evidencia que proporciona el código en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="e133e-107">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="e133e-108">SQL Server integra el modelo de seguridad basado en usuario de SQL Server con el modelo de seguridad basado en el acceso del código de CLR.</span><span class="sxs-lookup"><span data-stu-id="e133e-108">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="e133e-109">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="e133e-109">External Resources</span></span>  

 <span data-ttu-id="e133e-110">Para obtener más información sobre la integración de CLR con SQL Server, vea los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="e133e-110">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="e133e-111">Resource</span><span class="sxs-lookup"><span data-stu-id="e133e-111">Resource</span></span>|<span data-ttu-id="e133e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e133e-112">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="e133e-113">Seguridad de acceso del código</span><span class="sxs-lookup"><span data-stu-id="e133e-113">Code Access Security</span></span>](../../../misc/code-access-security.md)|<span data-ttu-id="e133e-114">Contiene temas que describen CAS en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e133e-114">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="e133e-115">Seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="e133e-115">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)|<span data-ttu-id="e133e-116">Describe el modelo de seguridad para el código administrado que se ejecuta en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e133e-116">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e133e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e133e-117">See also</span></span>

- [<span data-ttu-id="e133e-118">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e133e-118">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="e133e-119">Escenarios de seguridad de aplicaciones en SQL Server</span><span class="sxs-lookup"><span data-stu-id="e133e-119">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="e133e-120">Integración con Common Language Runtime de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e133e-120">SQL Server Common Language Runtime Integration</span></span>](sql-server-common-language-runtime-integration.md)
- [<span data-ttu-id="e133e-121">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e133e-121">ADO.NET Overview</span></span>](../ado-net-overview.md)

---
title: Seguridad de integración de CLR en SQL Server
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: dfd99155e42f426eeb01c89c433955cc2e3f0178
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2018
ms.locfileid: "49454361"
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="70d3a-102">Seguridad de integración de CLR en SQL Server</span><span class="sxs-lookup"><span data-stu-id="70d3a-102">CLR Integration Security in SQL Server</span></span>
<span data-ttu-id="70d3a-103">Microsoft SQL Server proporciona la integración del componente Common Language Runtime (CLR) de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="70d3a-103">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="70d3a-104">La integración de CLR permite escribir procedimientos almacenados, desencadenadores, tipos definidos por el usuario, funciones definidas por el usuario, agregados definidos por el usuario y funciones con valores de tabla de secuencias, mediante el uso de cualquier lenguaje de .NET Framework, como Microsoft Visual Basic .NET o Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="70d3a-104">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="70d3a-105">El CLR admite un modelo de seguridad llamado seguridad de acceso del código (CAS) para el código administrado.</span><span class="sxs-lookup"><span data-stu-id="70d3a-105">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="70d3a-106">En este modelo, se conceden permisos a los ensamblados en función de la evidencia que proporciona el código en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="70d3a-106">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="70d3a-107">SQL Server integra el modelo de seguridad basado en usuario de SQL Server con el modelo de seguridad basado en el acceso del código de CLR.</span><span class="sxs-lookup"><span data-stu-id="70d3a-107">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="70d3a-108">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="70d3a-108">External Resources</span></span>  
 <span data-ttu-id="70d3a-109">Para obtener más información sobre la integración de CLR con SQL Server, vea los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="70d3a-109">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="70d3a-110">Recurso</span><span class="sxs-lookup"><span data-stu-id="70d3a-110">Resource</span></span>|<span data-ttu-id="70d3a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="70d3a-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="70d3a-112">Seguridad de acceso del código</span><span class="sxs-lookup"><span data-stu-id="70d3a-112">Code Access Security</span></span>](../../../../../docs/framework/misc/code-access-security.md)|<span data-ttu-id="70d3a-113">Contiene temas que describen CAS en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="70d3a-113">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="70d3a-114">Seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="70d3a-114">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)|<span data-ttu-id="70d3a-115">Describe el modelo de seguridad para el código administrado que se ejecuta en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="70d3a-115">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70d3a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="70d3a-116">See Also</span></span>  
 [<span data-ttu-id="70d3a-117">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="70d3a-117">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="70d3a-118">Escenarios de seguridad de aplicaciones en SQL Server</span><span class="sxs-lookup"><span data-stu-id="70d3a-118">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="70d3a-119">Integración con Common Language Runtime de SQL Server</span><span class="sxs-lookup"><span data-stu-id="70d3a-119">SQL Server Common Language Runtime Integration</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 [<span data-ttu-id="70d3a-120">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="70d3a-120">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)

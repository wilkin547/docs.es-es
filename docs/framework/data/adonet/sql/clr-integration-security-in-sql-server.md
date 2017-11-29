---
title: "Seguridad de integración de CLR en SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: de4f4b1ae5ba252778d9463cba43a9ccb419600a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="9ea17-102">Seguridad de integración de CLR en SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ea17-102">CLR Integration Security in SQL Server</span></span>
<span data-ttu-id="9ea17-103">Microsoft SQL Server proporciona la integración del componente Common Language Runtime (CLR) de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ea17-103">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="9ea17-104">La integración de CLR permite escribir procedimientos almacenados, desencadenadores, tipos definidos por el usuario, funciones definidas por el usuario, agregados definidos por el usuario y funciones con valores de tabla de secuencias, mediante el uso de cualquier lenguaje de .NET Framework, como Microsoft Visual Basic .NET o Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="9ea17-104">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="9ea17-105">El CLR admite un modelo de seguridad llamado seguridad de acceso del código (CAS) para el código administrado.</span><span class="sxs-lookup"><span data-stu-id="9ea17-105">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="9ea17-106">En este modelo, se conceden permisos a los ensamblados en función de la evidencia que proporciona el código en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="9ea17-106">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="9ea17-107">SQL Server integra el modelo de seguridad basado en usuario de SQL Server con el modelo de seguridad basado en el acceso del código de CLR.</span><span class="sxs-lookup"><span data-stu-id="9ea17-107">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="9ea17-108">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="9ea17-108">External Resources</span></span>  
 <span data-ttu-id="9ea17-109">Para obtener más información sobre la integración de CLR con SQL Server, vea los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="9ea17-109">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="9ea17-110">Recurso</span><span class="sxs-lookup"><span data-stu-id="9ea17-110">Resource</span></span>|<span data-ttu-id="9ea17-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ea17-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="9ea17-112">Seguridad de acceso del código</span><span class="sxs-lookup"><span data-stu-id="9ea17-112">Code Access Security</span></span>](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03)|<span data-ttu-id="9ea17-113">Contiene temas que describen CAS en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ea17-113">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="9ea17-114">Seguridad de la integración de CLR</span><span class="sxs-lookup"><span data-stu-id="9ea17-114">CLR Integration Security</span></span>](http://go.microsoft.com/fwlink/?LinkId=59998)|<span data-ttu-id="9ea17-115">Describe el modelo de seguridad para el código administrado que se ejecuta en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9ea17-115">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ea17-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ea17-116">See Also</span></span>  
 [<span data-ttu-id="9ea17-117">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9ea17-117">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="9ea17-118">Escenarios de seguridad de la aplicación en SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ea17-118">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="9ea17-119">Integración Common Language Runtime SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ea17-119">SQL Server Common Language Runtime Integration</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 [<span data-ttu-id="9ea17-120">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="9ea17-120">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

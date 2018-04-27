---
title: Seguridad de SQL Server
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
caps.latest.revision: 8
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: eb9eb073eb2227ce98d4adb93b8f4b60575cf1b7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="sql-server-security"></a><span data-ttu-id="a917e-102">Seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a917e-102">SQL Server Security</span></span>
<span data-ttu-id="a917e-103">SQL Server incluye diferentes características que admiten la creación de aplicaciones de base de datos seguras.</span><span class="sxs-lookup"><span data-stu-id="a917e-103">SQL Server has many features that support creating secure database applications.</span></span>  
  
 <span data-ttu-id="a917e-104">Las consideraciones comunes de seguridad, como el robo de datos o el vandalismo, se aplican independientemente de la versión de SQL Server que se utilice.</span><span class="sxs-lookup"><span data-stu-id="a917e-104">Common security considerations, such as data theft or vandalism, apply regardless of the version of SQL Server you are using.</span></span> <span data-ttu-id="a917e-105">La integridad de los datos también se debe considerar como un problema de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a917e-105">Data integrity should also be considered as a security issue.</span></span> <span data-ttu-id="a917e-106">Si los datos no están protegidos, es posible que acaben perdiendo su valor si se permite la manipulación de datos ad hot y los datos se modifican sin intención o de forma malintencionada con valores incorrectos o bien se eliminan por completo.</span><span class="sxs-lookup"><span data-stu-id="a917e-106">If data is not protected, it is possible that it could become worthless if ad hoc data manipulation is permitted and the data is inadvertently or maliciously modified with incorrect values or deleted entirely.</span></span> <span data-ttu-id="a917e-107">Además, a menudo existen requisitos legales que se deben cumplir, como el almacenamiento correcto de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="a917e-107">In addition, there are often legal requirements that must be adhered to, such as the correct storage of confidential information.</span></span> <span data-ttu-id="a917e-108">El almacenamiento de determinados tipos de datos personales está totalmente prohibido, en función de las leyes que se apliquen en una jurisdicción determinada.</span><span class="sxs-lookup"><span data-stu-id="a917e-108">Storing some kinds of personal data is proscribed entirely, depending on the laws that apply in a particular jurisdiction.</span></span>  
  
 <span data-ttu-id="a917e-109">Cada versión de SQL Server incluye diferentes características de seguridad, al igual que cada versión de Windows, y las versiones posteriores cuentan con funcionalidad mejorada con respecto a las anteriores.</span><span class="sxs-lookup"><span data-stu-id="a917e-109">Each version of SQL Server has different security features, as does each version of Windows, with later versions having enhanced functionality over earlier ones.</span></span> <span data-ttu-id="a917e-110">Es importante comprender que las características de seguridad no pueden garantizar por sí solas una aplicación de base de datos segura.</span><span class="sxs-lookup"><span data-stu-id="a917e-110">It is important to understand that security features alone cannot guarantee a secure database application.</span></span> <span data-ttu-id="a917e-111">Cada aplicación de base de datos es única en lo que respecta a los requisitos, el entorno de ejecución, el modelo de implementación, la ubicación física y el rellenado por parte del usuario.</span><span class="sxs-lookup"><span data-stu-id="a917e-111">Each database application is unique in its requirements, execution environment, deployment model, physical location, and user population.</span></span> <span data-ttu-id="a917e-112">Algunas aplicaciones que son locales en cuanto al ámbito pueden necesitar una seguridad mínima, en tanto que otras aplicaciones locales o las aplicaciones implementadas en Internet pueden precisar medidas estrictas de seguridad y supervisión y evaluación continuas.</span><span class="sxs-lookup"><span data-stu-id="a917e-112">Some applications that are local in scope may need only minimal security whereas other local applications or applications deployed over the Internet may require stringent security measures and ongoing monitoring and evaluation.</span></span>  
  
 <span data-ttu-id="a917e-113">Los requisitos de seguridad de una aplicación de base de datos de SQL Server se deben tener en cuenta en tiempo de diseño, no a posteriori.</span><span class="sxs-lookup"><span data-stu-id="a917e-113">The security requirements of a SQL Server database application should be considered at design time, not as an afterthought.</span></span> <span data-ttu-id="a917e-114">La evaluación de las amenazas en las primeras fases del ciclo de desarrollo permite reducir al mínimo los posibles daños cuando se detecte una vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="a917e-114">Evaluating threats early in the development cycle gives you the opportunity to mitigate potential damage wherever a vulnerability is detected.</span></span>  
  
 <span data-ttu-id="a917e-115">Sin embargo, a pesar de que el diseño inicial de la aplicación resulte adecuado, pueden surgir nuevas amenazas a medida que evoluciona el sistema.</span><span class="sxs-lookup"><span data-stu-id="a917e-115">Even if the initial design of an application is sound, new threats may emerge as the system evolves.</span></span> <span data-ttu-id="a917e-116">La creación de varias líneas de defensa en torno a la base de datos permite reducir al mínimo los daños producidos por una infracción de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a917e-116">By creating multiple lines of defense around your database, you can minimize the damage inflicted by a security breach.</span></span> <span data-ttu-id="a917e-117">La primera línea de defensa consiste en reducir el área de ataque; para ello, no se deben conceder más permisos que los estrictamente necesarios.</span><span class="sxs-lookup"><span data-stu-id="a917e-117">Your first line of defense is to reduce the attack surface area by never to granting more permissions than are absolutely necessary.</span></span>  
  
 <span data-ttu-id="a917e-118">Los temas de esta sección describen brevemente las características de seguridad de SQL Server de interés para los programadores, con vínculos a temas relevantes en los Libros en pantalla de SQL Server y otros recursos que proporcionan información más detallada.</span><span class="sxs-lookup"><span data-stu-id="a917e-118">The topics in this section briefly describe the security features in SQL Server that are relevant for developers, with links to relevant topics in SQL Server Books Online and other resources that provide more detailed coverage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a917e-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a917e-119">In This Section</span></span>  
 [<span data-ttu-id="a917e-120">Información general sobre la seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a917e-120">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 <span data-ttu-id="a917e-121">Describe la arquitectura y las características de seguridad de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a917e-121">Describes the architecture and security features of SQL Server.</span></span>  
  
 [<span data-ttu-id="a917e-122">Escenarios de seguridad de aplicaciones en SQL Server</span><span class="sxs-lookup"><span data-stu-id="a917e-122">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 <span data-ttu-id="a917e-123">Contiene temas que describen diferentes escenarios de seguridad de aplicaciones para aplicaciones de ADO.NET y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a917e-123">Contains topics discussing various application security scenarios for ADO.NET and SQL Server applications.</span></span>  
  
 [<span data-ttu-id="a917e-124">Seguridad de SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="a917e-124">SQL Server Express Security</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-express-security.md)  
 <span data-ttu-id="a917e-125">Describe las consideraciones de seguridad para SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="a917e-125">Describes security considerations for SQL Server Express.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a917e-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="a917e-126">Related Sections</span></span>  
[<span data-ttu-id="a917e-127">Centro de seguridad para el motor de base de datos SQL Server y base de datos SQL Azure</span><span class="sxs-lookup"><span data-stu-id="a917e-127">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](/sql/relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database)  
<span data-ttu-id="a917e-128">Describe las consideraciones de seguridad para SQL Server y base de datos de SQL Azure.</span><span class="sxs-lookup"><span data-stu-id="a917e-128">Describes security considerations for SQL Server and Azure SQL Database.</span></span>

[<span data-ttu-id="a917e-129">Consideraciones de seguridad para una instalación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a917e-129">Security Considerations for a SQL Server Installation</span></span>](/sql/sql-server/install/security-considerations-for-a-sql-server-installation)  
<span data-ttu-id="a917e-130">Describe cuestiones de seguridad a tener en cuenta antes de instalar SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a917e-130">Describes security concerns to consider before installing SQL Server.</span></span>

## <a name="see-also"></a><span data-ttu-id="a917e-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a917e-131">See Also</span></span>  
 [<span data-ttu-id="a917e-132">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a917e-132">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="a917e-133">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a917e-133">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  

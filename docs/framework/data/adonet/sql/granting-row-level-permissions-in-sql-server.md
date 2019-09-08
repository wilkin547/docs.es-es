---
title: Conceder permisos de nivel de fila en SQL Server
ms.date: 03/30/2017
ms.assetid: a55aaa12-34ab-41cd-9dec-fd255b29258c
ms.openlocfilehash: df5fcb4a6c73e12bec2ab17501fdfb02cf672324
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782356"
---
# <a name="granting-row-level-permissions-in-sql-server"></a><span data-ttu-id="f505a-102">Conceder permisos de nivel de fila en SQL Server</span><span class="sxs-lookup"><span data-stu-id="f505a-102">Granting Row-Level Permissions in SQL Server</span></span>

<span data-ttu-id="f505a-103">En algunos casos, existe un requisito para controlar el acceso a los datos a un nivel más detallado que el que se deriva simplemente de conceder, revocar o denegar permisos.</span><span class="sxs-lookup"><span data-stu-id="f505a-103">In some scenarios, there is a requirement to control access to data at a more granular level than what simply granting, revoking, or denying permissions provides.</span></span> <span data-ttu-id="f505a-104">Por ejemplo, una aplicación de bases de datos de hospital puede requerir que se restrinja el acceso a los médicos individuales solo a la información relacionada con sus pacientes.</span><span class="sxs-lookup"><span data-stu-id="f505a-104">For example, a hospital database application may require individual Doctors to be restricted to accessing information related to only their patients.</span></span> <span data-ttu-id="f505a-105">Requisitos similares se producen en muchos ámbitos, como en aplicaciones financieras, legales, gubernamentales y militares.</span><span class="sxs-lookup"><span data-stu-id="f505a-105">Similar requirements exist in many environments, including finance, law, government, and military applications.</span></span> <span data-ttu-id="f505a-106">Para ayudar a resolver estos escenarios, SQL Server 2016 ofrece una característica de [seguridad por filas](/sql/relational-databases/security/row-level-security) que simplifica y centraliza la lógica de acceso por filas en una directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f505a-106">To help address these scenarios, SQL Server 2016 provides a [Row-Level Security](/sql/relational-databases/security/row-level-security) feature that simplifies and centralizes row-level access logic in a security policy.</span></span> <span data-ttu-id="f505a-107">Para las versiones anteriores de SQL Server, se puede lograr una funcionalidad similar con vistas para aplicar el filtrado por filas.</span><span class="sxs-lookup"><span data-stu-id="f505a-107">For earlier versions of SQL Server, similar functionality can be achieved by using views to enact row-level filtering.</span></span>

## <a name="implementing-row-level-filtering"></a><span data-ttu-id="f505a-108">Implementación de filtros por filas</span><span class="sxs-lookup"><span data-stu-id="f505a-108">Implementing Row-level Filtering</span></span>

<span data-ttu-id="f505a-109">El filtrado por filas se usa para la información de almacenamiento de aplicaciones en una tabla única como en el ejemplo anterior del hospital.</span><span class="sxs-lookup"><span data-stu-id="f505a-109">Row-level filtering is used for applications storing information in a single table like in the hospital example above.</span></span> <span data-ttu-id="f505a-110">Para implementar el filtrado por filas, cada fila tiene una columna que define un parámetro diferenciador, como un nombre de usuario, una etiqueta u otro identificador.</span><span class="sxs-lookup"><span data-stu-id="f505a-110">To implement row-level filtering each row has a column that defines a differentiating parameter, such as a user name, label or other identifier.</span></span> <span data-ttu-id="f505a-111">Para crear una vista o una directiva de seguridad en la tabla, que filtre las filas a las que puede tener acceso el usuario.</span><span class="sxs-lookup"><span data-stu-id="f505a-111">You create either a security policy or a view on the table, which filters the rows that the user can access.</span></span> <span data-ttu-id="f505a-112">Después, cree procedimientos almacenados parametrizados, que controlan los tipos de consultas que el usuario puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="f505a-112">You then create parameterized stored procedures, which control the types of queries the user can execute.</span></span>

<span data-ttu-id="f505a-113">En el siguiente ejemplo se describe cómo configurar el filtrado por filas basándose en un usuario o nombre de inicio de sesión:</span><span class="sxs-lookup"><span data-stu-id="f505a-113">The following example describes how to configure row-level filtering based on a user or login name:</span></span>

- <span data-ttu-id="f505a-114">Crear la tabla agregando una columna para almacenar el nombre.</span><span class="sxs-lookup"><span data-stu-id="f505a-114">Create the table, adding a column to store the name.</span></span>

- <span data-ttu-id="f505a-115">Habilite el filtrado por filas:</span><span class="sxs-lookup"><span data-stu-id="f505a-115">Enable row-level filtering:</span></span>

  - <span data-ttu-id="f505a-116">Si usa SQL Server 2016 o posterior, o la [Base de datos SQL de Azure](https://docs.microsoft.com/azure/sql-database/), cree una directiva de seguridad que agregue un predicado en la tabla restringiendo las filas devueltas a aquellas que coinciden con el usuario de base de datos actual (mediante la función integrada CURRENT_USER()) o el nombre de inicio de sesión actual (mediante la función integrada de SUSER_SNAME()):</span><span class="sxs-lookup"><span data-stu-id="f505a-116">If you are using SQL Server 2016 or higher, or [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/), create a security policy that adds a predicate on the table restricting the rows returned to those that match either the current database user (using the CURRENT_USER() built-in function) or the current login name (using the SUSER_SNAME() built-in function):</span></span>

      ```sql
      CREATE SCHEMA Security
      GO

      CREATE FUNCTION Security.userAccessPredicate(@UserName sysname)
          RETURNS TABLE
          WITH SCHEMABINDING
      AS
          RETURN SELECT 1 AS accessResult
          WHERE @UserName = SUSER_SNAME()
      GO

      CREATE SECURITY POLICY Security.userAccessPolicy
          ADD FILTER PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable,
          ADD BLOCK PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable
      GO
      ```

  - <span data-ttu-id="f505a-117">Si usa una versión de SQL Server anterior a 2016, puede lograr una funcionalidad similar con una vista:</span><span class="sxs-lookup"><span data-stu-id="f505a-117">If you are using a version of SQL Server prior to 2016, you can achieve similar functionality using a view:</span></span>

      ```sql
      CREATE VIEW vw_MyTable
      AS
          RETURN SELECT * FROM MyTable
          WHERE UserName = SUSER_SNAME()
      GO
      ```

- <span data-ttu-id="f505a-118">Cree procedimientos almacenados para seleccionar, insertar, actualizar y eliminar datos.</span><span class="sxs-lookup"><span data-stu-id="f505a-118">Create stored procedures to select, insert, update, and delete data.</span></span> <span data-ttu-id="f505a-119">Si el filtrado está aplicado por una directiva de seguridad, los procedimientos almacenados deben llevar a cabo estas operaciones en la tabla base directamente; de lo contrario, si el filtrado está aplicado por una vista, los procedimientos almacenados deben funcionar en su lugar con la vista.</span><span class="sxs-lookup"><span data-stu-id="f505a-119">If the filtering is enacted by a security policy, the stored procedures should perform these operations on the base table directly; otherwise, if the filtering is enacted by a view, the stored procedures should instead operate against the view.</span></span> <span data-ttu-id="f505a-120">La directiva de seguridad o la vista filtrarán automáticamente las filas devueltas o modificadas por las consultas de usuario, y el procedimiento almacenado ofrecerá un mayor límite de seguridad para impedir que los usuarios con acceso directo a consultas ejecuten correctamente las consultas que pueden inferir la existencia de datos filtrados.</span><span class="sxs-lookup"><span data-stu-id="f505a-120">The security policy or view will automatically filter the rows returned or modified by user queries, and the stored procedure will provide a harder security boundary to prevent users with direct query access from successfully running queries that can infer the existence of filtered data.</span></span>

- <span data-ttu-id="f505a-121">Para los procedimientos almacenados que insertan datos, capture el nombre de usuario utilizando el mismo rol especificado en la vista o directiva de seguridad e inserte dicho valor en la columna UserName.</span><span class="sxs-lookup"><span data-stu-id="f505a-121">For stored procedures that insert data, capture the user name using the same function specified in the security policy or view, and insert that value into the UserName column.</span></span>

- <span data-ttu-id="f505a-122">Denegar todos los permisos en las tablas (y vistas, si es aplicable) al rol `public` .</span><span class="sxs-lookup"><span data-stu-id="f505a-122">Deny all permissions on the tables (and views, if applicable) to the `public` role.</span></span> <span data-ttu-id="f505a-123">Los usuarios no podrán heredar permisos de otros roles de base de datos porque el predicado de filtro se basa en nombres de inicio de sesión o usuarios, no en roles.</span><span class="sxs-lookup"><span data-stu-id="f505a-123">Users will not be able to inherit permissions from other database roles, because the filter predicate is based on user or login names, not on roles.</span></span>

- <span data-ttu-id="f505a-124">Conceder permisos EXECUTE en los procedimientos almacenados a roles de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="f505a-124">Grant EXECUTE on the stored procedures to database roles.</span></span> <span data-ttu-id="f505a-125">Los usuarios sólo pueden obtener acceso a datos a través de los procedimientos almacenados proporcionados</span><span class="sxs-lookup"><span data-stu-id="f505a-125">Users can only access data through the stored procedures provided.</span></span>

## <a name="see-also"></a><span data-ttu-id="f505a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f505a-126">See also</span></span>

- [<span data-ttu-id="f505a-127">Seguridad de nivel de fila</span><span class="sxs-lookup"><span data-stu-id="f505a-127">Row-Level Security</span></span>](/sql/relational-databases/security/row-level-security)
- [<span data-ttu-id="f505a-128">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f505a-128">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="f505a-129">Información general sobre la seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f505a-129">Overview of SQL Server Security</span></span>](overview-of-sql-server-security.md)
- [<span data-ttu-id="f505a-130">Escenarios de seguridad de aplicaciones en SQL Server</span><span class="sxs-lookup"><span data-stu-id="f505a-130">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="f505a-131">Administración de permisos con procedimientos almacenados en SQL Server</span><span class="sxs-lookup"><span data-stu-id="f505a-131">Managing Permissions with Stored Procedures in SQL Server</span></span>](managing-permissions-with-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="f505a-132">Escritura de código SQL dinámico y seguro en SQL Server</span><span class="sxs-lookup"><span data-stu-id="f505a-132">Writing Secure Dynamic SQL in SQL Server</span></span>](writing-secure-dynamic-sql-in-sql-server.md)
- [<span data-ttu-id="f505a-133">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f505a-133">ADO.NET Overview</span></span>](../ado-net-overview.md)

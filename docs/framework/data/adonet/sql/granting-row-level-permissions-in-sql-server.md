---
description: Más información acerca de cómo conceder permisos de Row-Level en SQL Server
title: Conceder permisos de nivel de fila en SQL Server
ms.date: 03/30/2017
ms.assetid: a55aaa12-34ab-41cd-9dec-fd255b29258c
ms.openlocfilehash: fe69a023b5befbdb53473881647fff8bdf0e9795
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663305"
---
# <a name="granting-row-level-permissions-in-sql-server"></a><span data-ttu-id="2c207-103">Conceder permisos de nivel de fila en SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c207-103">Granting Row-Level Permissions in SQL Server</span></span>

<span data-ttu-id="2c207-104">En algunos casos, existe un requisito para controlar el acceso a los datos a un nivel más detallado que el que se deriva simplemente de conceder, revocar o denegar permisos.</span><span class="sxs-lookup"><span data-stu-id="2c207-104">In some scenarios, there is a requirement to control access to data at a more granular level than what simply granting, revoking, or denying permissions provides.</span></span> <span data-ttu-id="2c207-105">Por ejemplo, una aplicación de bases de datos de hospital puede requerir que se restrinja el acceso a los médicos individuales solo a la información relacionada con sus pacientes.</span><span class="sxs-lookup"><span data-stu-id="2c207-105">For example, a hospital database application may require individual Doctors to be restricted to accessing information related to only their patients.</span></span> <span data-ttu-id="2c207-106">Requisitos similares se producen en muchos ámbitos, como en aplicaciones financieras, legales, gubernamentales y militares.</span><span class="sxs-lookup"><span data-stu-id="2c207-106">Similar requirements exist in many environments, including finance, law, government, and military applications.</span></span> <span data-ttu-id="2c207-107">Para ayudar a resolver estos escenarios, SQL Server 2016 ofrece una característica de [seguridad por filas](/sql/relational-databases/security/row-level-security) que simplifica y centraliza la lógica de acceso por filas en una directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2c207-107">To help address these scenarios, SQL Server 2016 provides a [Row-Level Security](/sql/relational-databases/security/row-level-security) feature that simplifies and centralizes row-level access logic in a security policy.</span></span> <span data-ttu-id="2c207-108">Para las versiones anteriores de SQL Server, se puede lograr una funcionalidad similar con vistas para aplicar el filtrado por filas.</span><span class="sxs-lookup"><span data-stu-id="2c207-108">For earlier versions of SQL Server, similar functionality can be achieved by using views to enact row-level filtering.</span></span>

## <a name="implementing-row-level-filtering"></a><span data-ttu-id="2c207-109">Implementación de filtros por filas</span><span class="sxs-lookup"><span data-stu-id="2c207-109">Implementing Row-level Filtering</span></span>

<span data-ttu-id="2c207-110">El filtrado por filas se usa para la información de almacenamiento de aplicaciones en una tabla única como en el ejemplo anterior del hospital.</span><span class="sxs-lookup"><span data-stu-id="2c207-110">Row-level filtering is used for applications storing information in a single table like in the hospital example above.</span></span> <span data-ttu-id="2c207-111">Para implementar el filtrado por filas, cada fila tiene una columna que define un parámetro diferenciador, como un nombre de usuario, una etiqueta u otro identificador.</span><span class="sxs-lookup"><span data-stu-id="2c207-111">To implement row-level filtering each row has a column that defines a differentiating parameter, such as a user name, label or other identifier.</span></span> <span data-ttu-id="2c207-112">Para crear una vista o una directiva de seguridad en la tabla, que filtre las filas a las que puede tener acceso el usuario.</span><span class="sxs-lookup"><span data-stu-id="2c207-112">You create either a security policy or a view on the table, which filters the rows that the user can access.</span></span> <span data-ttu-id="2c207-113">Después, cree procedimientos almacenados parametrizados, que controlan los tipos de consultas que el usuario puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="2c207-113">You then create parameterized stored procedures, which control the types of queries the user can execute.</span></span>

<span data-ttu-id="2c207-114">En el siguiente ejemplo se describe cómo configurar el filtrado por filas basándose en un usuario o nombre de inicio de sesión:</span><span class="sxs-lookup"><span data-stu-id="2c207-114">The following example describes how to configure row-level filtering based on a user or login name:</span></span>

- <span data-ttu-id="2c207-115">Crear la tabla agregando una columna para almacenar el nombre.</span><span class="sxs-lookup"><span data-stu-id="2c207-115">Create the table, adding a column to store the name.</span></span>

- <span data-ttu-id="2c207-116">Habilite el filtrado por filas:</span><span class="sxs-lookup"><span data-stu-id="2c207-116">Enable row-level filtering:</span></span>

  - <span data-ttu-id="2c207-117">Si usa SQL Server 2016 o posterior, o la [Base de datos SQL de Azure](/azure/sql-database/), cree una directiva de seguridad que agregue un predicado en la tabla restringiendo las filas devueltas a aquellas que coinciden con el usuario de base de datos actual (mediante la función integrada CURRENT_USER()) o el nombre de inicio de sesión actual (mediante la función integrada de SUSER_SNAME()):</span><span class="sxs-lookup"><span data-stu-id="2c207-117">If you are using SQL Server 2016 or higher, or [Azure SQL Database](/azure/sql-database/), create a security policy that adds a predicate on the table restricting the rows returned to those that match either the current database user (using the CURRENT_USER() built-in function) or the current login name (using the SUSER_SNAME() built-in function):</span></span>

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

  - <span data-ttu-id="2c207-118">Si usa una versión de SQL Server anterior a 2016, puede lograr una funcionalidad similar con una vista:</span><span class="sxs-lookup"><span data-stu-id="2c207-118">If you are using a version of SQL Server prior to 2016, you can achieve similar functionality using a view:</span></span>

      ```sql
      CREATE VIEW vw_MyTable
      AS
          RETURN SELECT * FROM MyTable
          WHERE UserName = SUSER_SNAME()
      GO
      ```

- <span data-ttu-id="2c207-119">Cree procedimientos almacenados para seleccionar, insertar, actualizar y eliminar datos.</span><span class="sxs-lookup"><span data-stu-id="2c207-119">Create stored procedures to select, insert, update, and delete data.</span></span> <span data-ttu-id="2c207-120">Si el filtrado está aplicado por una directiva de seguridad, los procedimientos almacenados deben llevar a cabo estas operaciones en la tabla base directamente; de lo contrario, si el filtrado está aplicado por una vista, los procedimientos almacenados deben funcionar en su lugar con la vista.</span><span class="sxs-lookup"><span data-stu-id="2c207-120">If the filtering is enacted by a security policy, the stored procedures should perform these operations on the base table directly; otherwise, if the filtering is enacted by a view, the stored procedures should instead operate against the view.</span></span> <span data-ttu-id="2c207-121">La directiva de seguridad o la vista filtrarán automáticamente las filas devueltas o modificadas por las consultas de usuario, y el procedimiento almacenado ofrecerá un mayor límite de seguridad para impedir que los usuarios con acceso directo a consultas ejecuten correctamente las consultas que pueden inferir la existencia de datos filtrados.</span><span class="sxs-lookup"><span data-stu-id="2c207-121">The security policy or view will automatically filter the rows returned or modified by user queries, and the stored procedure will provide a harder security boundary to prevent users with direct query access from successfully running queries that can infer the existence of filtered data.</span></span>

- <span data-ttu-id="2c207-122">Para los procedimientos almacenados que insertan datos, capture el nombre de usuario utilizando el mismo rol especificado en la vista o directiva de seguridad e inserte dicho valor en la columna UserName.</span><span class="sxs-lookup"><span data-stu-id="2c207-122">For stored procedures that insert data, capture the user name using the same function specified in the security policy or view, and insert that value into the UserName column.</span></span>

- <span data-ttu-id="2c207-123">Denegar todos los permisos en las tablas (y vistas, si es aplicable) al rol `public` .</span><span class="sxs-lookup"><span data-stu-id="2c207-123">Deny all permissions on the tables (and views, if applicable) to the `public` role.</span></span> <span data-ttu-id="2c207-124">Los usuarios no podrán heredar permisos de otros roles de base de datos porque el predicado de filtro se basa en nombres de inicio de sesión o usuarios, no en roles.</span><span class="sxs-lookup"><span data-stu-id="2c207-124">Users will not be able to inherit permissions from other database roles, because the filter predicate is based on user or login names, not on roles.</span></span>

- <span data-ttu-id="2c207-125">Conceder permisos EXECUTE en los procedimientos almacenados a roles de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="2c207-125">Grant EXECUTE on the stored procedures to database roles.</span></span> <span data-ttu-id="2c207-126">Los usuarios sólo pueden obtener acceso a datos a través de los procedimientos almacenados proporcionados</span><span class="sxs-lookup"><span data-stu-id="2c207-126">Users can only access data through the stored procedures provided.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c207-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c207-127">See also</span></span>

- [<span data-ttu-id="2c207-128">Seguridad de nivel de fila</span><span class="sxs-lookup"><span data-stu-id="2c207-128">Row-Level Security</span></span>](/sql/relational-databases/security/row-level-security)
- [<span data-ttu-id="2c207-129">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c207-129">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="2c207-130">Información general sobre la seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c207-130">Overview of SQL Server Security</span></span>](overview-of-sql-server-security.md)
- [<span data-ttu-id="2c207-131">Escenarios de seguridad de aplicaciones en SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c207-131">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="2c207-132">Administrar permisos con procedimientos almacenados en SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c207-132">Managing Permissions with Stored Procedures in SQL Server</span></span>](managing-permissions-with-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="2c207-133">Escribir SQL dinámico seguro en SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c207-133">Writing Secure Dynamic SQL in SQL Server</span></span>](writing-secure-dynamic-sql-in-sql-server.md)
- [<span data-ttu-id="2c207-134">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c207-134">ADO.NET Overview</span></span>](../ado-net-overview.md)

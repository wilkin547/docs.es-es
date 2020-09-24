---
title: Datos de fecha y hora
description: Obtenga información sobre los tipos de datos para controlar la información de fecha y hora en el proveedor de datos de .NET Framework para SQL Server.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6f5ff56a-a57e-49d7-8ae9-bbed697e42e3
ms.openlocfilehash: 6fe047fc672a2b42f886e81dcace91042a552932
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156321"
---
# <a name="date-and-time-data"></a><span data-ttu-id="a98c7-103">Datos de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="a98c7-103">Date and Time Data</span></span>

<span data-ttu-id="a98c7-104">SQL Server 2008 introduce nuevos tipos de datos para administrar la información de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="a98c7-104">SQL Server 2008 introduces new data types for handling date and time information.</span></span> <span data-ttu-id="a98c7-105">Los nuevos tipos de datos incluyen tipos independientes para la fecha y la hora y tipos de datos expandidos con mayor control sobre el intervalo, la precisión y la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="a98c7-105">The new data types include separate types for date and time, and expanded data types with greater range, precision, and time-zone awareness.</span></span> <span data-ttu-id="a98c7-106">A partir de .NET Framework versión 3.5 Service Pack (SP) 1, el proveedor de datos .NET Framework para SQL Server (<xref:System.Data.SqlClient>) proporciona compatibilidad total con todas las características nuevas del Motor de base de datos de SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="a98c7-106">Starting with the .NET Framework version 3.5 Service Pack (SP) 1, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides full support for all the new features of the SQL Server 2008 Database Engine.</span></span> <span data-ttu-id="a98c7-107">Debe instalar .NET Framework 3.5 SP1 (o posterior) para usar estas características nuevas con SqlClient.</span><span class="sxs-lookup"><span data-stu-id="a98c7-107">You must install the .NET Framework 3.5 SP1 (or later) to use these new features with SqlClient.</span></span>  
  
 <span data-ttu-id="a98c7-108">Las versiones de SQL Server anteriores a SQL Server 2008 solo tenían dos tipos de datos para trabajar con valores de fecha y hora: `datetime` y `smalldatetime`.</span><span class="sxs-lookup"><span data-stu-id="a98c7-108">Versions of SQL Server earlier than SQL Server 2008 only had two data types for working with date and time values: `datetime` and `smalldatetime`.</span></span> <span data-ttu-id="a98c7-109">Ambos tipos de datos contienen el valor de fecha y el valor de hora, lo que dificulta trabajar solo con valores de fecha o de hora.</span><span class="sxs-lookup"><span data-stu-id="a98c7-109">Both of these data types contain both the date value and a time value, which makes it difficult to work with only date or only time values.</span></span> <span data-ttu-id="a98c7-110">Además, estos tipos de datos solo admiten las fechas posteriores a la introducción del calendario gregoriano en Inglaterra en 1753.</span><span class="sxs-lookup"><span data-stu-id="a98c7-110">Also, these data types only support dates that occur after the introduction of the Gregorian calendar in England in 1753.</span></span> <span data-ttu-id="a98c7-111">Otra limitación es que estos tipos de datos más antiguos no reconocen la zona horaria, por lo que resulta difícil trabajar con datos que proceden de varias zonas horarias.</span><span class="sxs-lookup"><span data-stu-id="a98c7-111">Another limitation is that these older data types are not time-zone aware, which makes it difficult to work with data that originates from multiple time zones.</span></span>  
  
 <span data-ttu-id="a98c7-112">La documentación completa de los tipos de datos de SQL Server está disponible en Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a98c7-112">Complete documentation for SQL Server data types is available in SQL Server Books Online.</span></span> <span data-ttu-id="a98c7-113">En la tabla siguiente se enumeran los temas de nivel básico específicos de la versión correspondientes a los datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="a98c7-113">The following table lists the version-specific entry-level topics for date and time data.</span></span>  
  
 <span data-ttu-id="a98c7-114">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a98c7-114">**SQL Server documentation**</span></span>  
  
1. <span data-ttu-id="a98c7-115">[Uso de datos de fecha y hora](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="a98c7-115">[Using Date and Time Data](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span></span>  
  
## <a name="datetime-data-types-introduced-in-sql-server-2008"></a><span data-ttu-id="a98c7-116">Tipos de datos de fecha y hora introducidos en SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="a98c7-116">Date/Time Data Types Introduced in SQL Server 2008</span></span>  

 <span data-ttu-id="a98c7-117">En la tabla siguiente se describen los nuevos tipos de datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="a98c7-117">The following table describes the new date and time data types.</span></span>  
  
|<span data-ttu-id="a98c7-118">Tipos de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a98c7-118">SQL Server data type</span></span>|<span data-ttu-id="a98c7-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a98c7-119">Description</span></span>|  
|--------------------------|-----------------|  
|`date`|<span data-ttu-id="a98c7-120">El tipo de datos `date` tiene un intervalo del 1 de enero de 01 al 31 de diciembre de 9999, con una precisión de 1 día.</span><span class="sxs-lookup"><span data-stu-id="a98c7-120">The `date` data type has a range of January 1, 01 through December 31, 9999 with an accuracy of 1 day.</span></span> <span data-ttu-id="a98c7-121">El valor predeterminado es 1 de enero de 1900.</span><span class="sxs-lookup"><span data-stu-id="a98c7-121">The default value is January 1, 1900.</span></span> <span data-ttu-id="a98c7-122">El tamaño de almacenamiento es de 3 bytes.</span><span class="sxs-lookup"><span data-stu-id="a98c7-122">The storage size is 3 bytes.</span></span>|  
|`time`|<span data-ttu-id="a98c7-123">El tipo de datos `time` solo almacena valores de hora basados en un reloj de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="a98c7-123">The `time` data type stores time values only, based on a 24-hour clock.</span></span> <span data-ttu-id="a98c7-124">El tipo de datos `time` tiene un intervalo de 00:00:00,0000000 a 23:59:59,9999999 con una precisión de 100 nanosegundos.</span><span class="sxs-lookup"><span data-stu-id="a98c7-124">The `time` data type has a range of 00:00:00.0000000 through 23:59:59.9999999 with an accuracy of 100 nanoseconds.</span></span> <span data-ttu-id="a98c7-125">El valor predeterminado es 00:00:00,0000000 (medianoche).</span><span class="sxs-lookup"><span data-stu-id="a98c7-125">The default value is 00:00:00.0000000 (midnight).</span></span> <span data-ttu-id="a98c7-126">El tipo de datos `time` admite la precisión decimal de segundos definida por el usuario y su tamaño de almacenamiento varía entre 3 y 6 bytes en función de la precisión especificada.</span><span class="sxs-lookup"><span data-stu-id="a98c7-126">The `time` data type supports user-defined fractional second precision, and the storage size varies from 3 to 6 bytes, based on the precision specified.</span></span>|  
|`datetime2`|<span data-ttu-id="a98c7-127">El tipo de datos `datetime2` combina el intervalo y la precisión de los tipos de datos `date` y `time` en un solo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="a98c7-127">The `datetime2` data type combines the range and precision of the `date` and `time` data types into a single data type.</span></span><br /><br /> <span data-ttu-id="a98c7-128">Los valores predeterminados y los formatos de literales de cadena son los mismos que los definidos en los tipos de datos `date` y `time`.</span><span class="sxs-lookup"><span data-stu-id="a98c7-128">The default values and string literal formats are the same as those defined in the `date` and `time` data types.</span></span>|  
|`datetimeoffset`|<span data-ttu-id="a98c7-129">El tipo de datos `datetimeoffset` incluye todas las características de `datetime2` con un desfase de zona horaria adicional.</span><span class="sxs-lookup"><span data-stu-id="a98c7-129">The `datetimeoffset` data type has all the features of `datetime2` with an additional time zone offset.</span></span> <span data-ttu-id="a98c7-130">El desfase de zona horaria se representa como [+&#124;-] HH:MM.</span><span class="sxs-lookup"><span data-stu-id="a98c7-130">The time zone offset is represented as [+&#124;-] HH:MM.</span></span> <span data-ttu-id="a98c7-131">HH es una cifra de dos dígitos que va de 00 a 14 y que representa el número de horas del desfase de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="a98c7-131">HH is 2 digits ranging from 00 to 14 that represent the number of hours in the time zone offset.</span></span> <span data-ttu-id="a98c7-132">MM es una cifra de dos dígitos que va de 00 a 59 y que representa el número minutos adicionales del desfase de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="a98c7-132">MM is 2 digits ranging from 00 to 59 that represent the number of additional minutes in the time zone offset.</span></span> <span data-ttu-id="a98c7-133">Se admiten formatos de hora de hasta 100 nanosegundos.</span><span class="sxs-lookup"><span data-stu-id="a98c7-133">Time formats are supported to 100 nanoseconds.</span></span> <span data-ttu-id="a98c7-134">El signo + o- obligatorio indica si el ajuste de zona horaria se suma o se resta de la hora UTC (hora universal coordinada u hora del meridiano de Greenwich) para obtener la hora local.</span><span class="sxs-lookup"><span data-stu-id="a98c7-134">The mandatory + or - sign indicates whether the time zone offset is added or subtracted from UTC (Universal Time Coordinate or Greenwich Mean Time) to obtain the local time.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="a98c7-135">Para obtener más información sobre el empleo de la palabra clave `Type System Version`, vea <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="a98c7-135">For more information about using the `Type System Version` keyword, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
## <a name="date-format-and-date-order"></a><span data-ttu-id="a98c7-136">Formato de fecha y orden de la fecha</span><span class="sxs-lookup"><span data-stu-id="a98c7-136">Date Format and Date Order</span></span>  

 <span data-ttu-id="a98c7-137">La forma en que SQL Server analiza los valores de fecha y hora no solo depende de la versión del sistema de tipos y de la versión del servidor, sino también de la configuración de formato y idioma predeterminados del servidor.</span><span class="sxs-lookup"><span data-stu-id="a98c7-137">How SQL Server parses date and time values depends not only on the type system version and server version, but also on the server's default language and format settings.</span></span> <span data-ttu-id="a98c7-138">Una cadena de fecha que funcione para los formatos de fecha de un idioma podría ser irreconocible si la consulta se ejecuta por una conexión que utiliza una configuración de formato de fecha y idioma diferente.</span><span class="sxs-lookup"><span data-stu-id="a98c7-138">A date string that works for the date formats of one language might be unrecognizable if the query is executed by a connection that uses a different language and date format setting.</span></span>  
  
 <span data-ttu-id="a98c7-139">La instrucción SET LANGUAGE de Transact-SQL establece implícitamente DATEFORMAT, que determina el orden de las partes de la fecha.</span><span class="sxs-lookup"><span data-stu-id="a98c7-139">The Transact-SQL SET LANGUAGE statement implicitly sets the DATEFORMAT that determines the order of the date parts.</span></span> <span data-ttu-id="a98c7-140">Puede usar la instrucción SET DATEFORMAT de Transact-SQL en una conexión para eliminar la ambigüedad de los valores de fecha ordenando las partes de fecha según MDA, DMA, AMD, ADM, MAD o DAM.</span><span class="sxs-lookup"><span data-stu-id="a98c7-140">You can use the SET DATEFORMAT Transact-SQL statement on a connection to disambiguate date values by ordering the date parts in MDY, DMY, YMD, YDM, MYD, or DYM order.</span></span>  
  
 <span data-ttu-id="a98c7-141">Si no especifica ningún valor DATEFORMAT para la conexión, SQL Server utiliza el idioma predeterminado asociado a la conexión.</span><span class="sxs-lookup"><span data-stu-id="a98c7-141">If you do not specify any DATEFORMAT for the connection, SQL Server uses the default language associated with the connection.</span></span> <span data-ttu-id="a98c7-142">Por ejemplo, una cadena de fecha de "01/02/03" se interpretaría como MDA (2 de enero de 2003) en un servidor con una configuración de idioma de inglés de Estados Unidos y como DMA (1 de febrero de 2003) en un servidor con una configuración de idioma de inglés británico.</span><span class="sxs-lookup"><span data-stu-id="a98c7-142">For example, a date string of '01/02/03' would be interpreted as MDY (January 2, 2003) on a server with a language setting of United States English, and as DMY (February 1, 2003) on a server with a language setting of British English.</span></span> <span data-ttu-id="a98c7-143">El año se determina mediante el uso de la regla del año límite de SQL Server, que define la fecha límite para asignar el valor del siglo.</span><span class="sxs-lookup"><span data-stu-id="a98c7-143">The year is determined by using SQL Server's cutoff year rule, which defines the cutoff date for assigning the century value.</span></span> <span data-ttu-id="a98c7-144">Para obtener más información, consulte la [opción de fecha límite de año de dos dígitos](/sql/database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option).</span><span class="sxs-lookup"><span data-stu-id="a98c7-144">For more information, see [two digit year cutoff Option](/sql/database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a98c7-145">No se admite el formato de fecha ADM al convertir de un formato de cadena a `date`, `time`, `datetime2` o `datetimeoffset`.</span><span class="sxs-lookup"><span data-stu-id="a98c7-145">The YDM date format is not supported when converting from a string format to `date`, `time`, `datetime2`, or `datetimeoffset`.</span></span>  
  
 <span data-ttu-id="a98c7-146">Para obtener más información sobre cómo SQL Server interpreta los datos de fecha y hora, vea [usar datos de fecha y hora](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100)).</span><span class="sxs-lookup"><span data-stu-id="a98c7-146">For more information about how SQL Server interprets date and time data, see [Using Date and Time Data](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100)).</span></span>  
  
## <a name="datetime-data-types-and-parameters"></a><span data-ttu-id="a98c7-147">Tipos de datos de fecha y hora y parámetros</span><span class="sxs-lookup"><span data-stu-id="a98c7-147">Date/Time Data Types and Parameters</span></span>  

 <span data-ttu-id="a98c7-148">Se han agregado los siguientes valores de enumeración a <xref:System.Data.SqlDbType> para admitir los nuevos tipos de datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="a98c7-148">The following enumerations have been added to <xref:System.Data.SqlDbType> to support the new date and time data types.</span></span>  
  
- `SqlDbType.Date`  
  
- `SqlDbType.Time`  
  
- `SqlDbType.DateTime2`  
  
- `SqlDbType.DateTimeOffSet`  

<span data-ttu-id="a98c7-149">Puede especificar el tipo de datos de <xref:System.Data.SqlClient.SqlParameter> mediante una de las enumeraciones <xref:System.Data.SqlDbType> anteriores.</span><span class="sxs-lookup"><span data-stu-id="a98c7-149">You can specify the data type of a <xref:System.Data.SqlClient.SqlParameter> by using one of the preceding <xref:System.Data.SqlDbType> enumerations.</span></span>

> [!NOTE]
> <span data-ttu-id="a98c7-150">No puede establecer la propiedad `DbType` de un `SqlParameter` en `SqlDbType.Date`.</span><span class="sxs-lookup"><span data-stu-id="a98c7-150">You cannot set the `DbType` property of a `SqlParameter` to `SqlDbType.Date`.</span></span>

 <span data-ttu-id="a98c7-151">También puede especificar el tipo de <xref:System.Data.SqlClient.SqlParameter> de forma genérica si establece la propiedad <xref:System.Data.SqlClient.SqlParameter.DbType%2A> de un objeto `SqlParameter` en un determinado valor de enumeración <xref:System.Data.DbType>.</span><span class="sxs-lookup"><span data-stu-id="a98c7-151">You can also specify the type of a <xref:System.Data.SqlClient.SqlParameter> generically by setting the <xref:System.Data.SqlClient.SqlParameter.DbType%2A> property of a `SqlParameter` object to a particular <xref:System.Data.DbType> enumeration value.</span></span> <span data-ttu-id="a98c7-152">Se han agregado los siguientes valores de enumeración a <xref:System.Data.DbType> para admitir los tipos de datos `datetime2` y `datetimeoffset`:</span><span class="sxs-lookup"><span data-stu-id="a98c7-152">The following enumeration values have been added to <xref:System.Data.DbType> to support the `datetime2` and `datetimeoffset` data types:</span></span>  
  
- <span data-ttu-id="a98c7-153">DbType.DateTime2</span><span class="sxs-lookup"><span data-stu-id="a98c7-153">DbType.DateTime2</span></span>  
  
- <span data-ttu-id="a98c7-154">DbType.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a98c7-154">DbType.DateTimeOffset</span></span>  
  
 <span data-ttu-id="a98c7-155">Estas nuevas enumeraciones complementan las enumeraciones `Date`, `Time` y `DateTime`, que ya existían en versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a98c7-155">These new enumerations supplement the `Date`, `Time`, and `DateTime` enumerations, which existed in earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="a98c7-156">El tipo del proveedor de datos .NET Framework de un objeto de parámetro se deduce a partir del tipo de .NET Framework del valor del objeto de parámetro o a partir de la enumeración `DbType` del objeto de parámetro.</span><span class="sxs-lookup"><span data-stu-id="a98c7-156">The .NET Framework data provider type of a parameter object is inferred from the .NET Framework type of the value of the parameter object, or from the `DbType` of the parameter object.</span></span> <span data-ttu-id="a98c7-157">No se han introducido nuevos tipos de datos de <xref:System.Data.SqlTypes> para admitir los nuevos tipos de datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="a98c7-157">No new <xref:System.Data.SqlTypes> data types have been introduced to support the new date and time data types.</span></span> <span data-ttu-id="a98c7-158">En la tabla siguiente se describen las asignaciones entre los tipos de datos de fecha y hora de SQL Server 2008 y los tipos de datos de CLR.</span><span class="sxs-lookup"><span data-stu-id="a98c7-158">The following table describes the mappings between the SQL Server 2008 date and time data types and the CLR data types.</span></span>  
  
|<span data-ttu-id="a98c7-159">Tipos de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a98c7-159">SQL Server data type</span></span>|<span data-ttu-id="a98c7-160">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a98c7-160">.NET Framework type</span></span>|<span data-ttu-id="a98c7-161">System.Data.SqlDbType</span><span class="sxs-lookup"><span data-stu-id="a98c7-161">System.Data.SqlDbType</span></span>|<span data-ttu-id="a98c7-162">System.Data.DbType</span><span class="sxs-lookup"><span data-stu-id="a98c7-162">System.Data.DbType</span></span>|  
|--------------------------|-------------------------|---------------------------|------------------------|  
|<span data-ttu-id="a98c7-163">date</span><span class="sxs-lookup"><span data-stu-id="a98c7-163">date</span></span>|<span data-ttu-id="a98c7-164">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="a98c7-164">System.DateTime</span></span>|<span data-ttu-id="a98c7-165">Date</span><span class="sxs-lookup"><span data-stu-id="a98c7-165">Date</span></span>|<span data-ttu-id="a98c7-166">Date</span><span class="sxs-lookup"><span data-stu-id="a98c7-166">Date</span></span>|  
|<span data-ttu-id="a98c7-167">time</span><span class="sxs-lookup"><span data-stu-id="a98c7-167">time</span></span>|<span data-ttu-id="a98c7-168">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="a98c7-168">System.TimeSpan</span></span>|<span data-ttu-id="a98c7-169">Time</span><span class="sxs-lookup"><span data-stu-id="a98c7-169">Time</span></span>|<span data-ttu-id="a98c7-170">Time</span><span class="sxs-lookup"><span data-stu-id="a98c7-170">Time</span></span>|  
|<span data-ttu-id="a98c7-171">datetime2</span><span class="sxs-lookup"><span data-stu-id="a98c7-171">datetime2</span></span>|<span data-ttu-id="a98c7-172">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="a98c7-172">System.DateTime</span></span>|<span data-ttu-id="a98c7-173">DateTime2</span><span class="sxs-lookup"><span data-stu-id="a98c7-173">DateTime2</span></span>|<span data-ttu-id="a98c7-174">DateTime2</span><span class="sxs-lookup"><span data-stu-id="a98c7-174">DateTime2</span></span>|  
|<span data-ttu-id="a98c7-175">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="a98c7-175">datetimeoffset</span></span>|<span data-ttu-id="a98c7-176">System.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a98c7-176">System.DateTimeOffset</span></span>|<span data-ttu-id="a98c7-177">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a98c7-177">DateTimeOffset</span></span>|<span data-ttu-id="a98c7-178">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a98c7-178">DateTimeOffset</span></span>|  
|<span data-ttu-id="a98c7-179">datetime</span><span class="sxs-lookup"><span data-stu-id="a98c7-179">datetime</span></span>|<span data-ttu-id="a98c7-180">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="a98c7-180">System.DateTime</span></span>|<span data-ttu-id="a98c7-181">DateTime</span><span class="sxs-lookup"><span data-stu-id="a98c7-181">DateTime</span></span>|<span data-ttu-id="a98c7-182">DateTime</span><span class="sxs-lookup"><span data-stu-id="a98c7-182">DateTime</span></span>|  
|<span data-ttu-id="a98c7-183">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="a98c7-183">smalldatetime</span></span>|<span data-ttu-id="a98c7-184">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="a98c7-184">System.DateTime</span></span>|<span data-ttu-id="a98c7-185">DateTime</span><span class="sxs-lookup"><span data-stu-id="a98c7-185">DateTime</span></span>|<span data-ttu-id="a98c7-186">DateTime</span><span class="sxs-lookup"><span data-stu-id="a98c7-186">DateTime</span></span>|  
  
### <a name="sqlparameter-properties"></a><span data-ttu-id="a98c7-187">Propiedades de SqlParameter</span><span class="sxs-lookup"><span data-stu-id="a98c7-187">SqlParameter Properties</span></span>  

 <span data-ttu-id="a98c7-188">En la tabla siguiente se describen las propiedades `SqlParameter` que son pertinentes para los tipos de datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="a98c7-188">The following table describes `SqlParameter` properties that are relevant to date and time data types.</span></span>  
  
|<span data-ttu-id="a98c7-189">Propiedad</span><span class="sxs-lookup"><span data-stu-id="a98c7-189">Property</span></span>|<span data-ttu-id="a98c7-190">Descripción</span><span class="sxs-lookup"><span data-stu-id="a98c7-190">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.IsNullable%2A>|<span data-ttu-id="a98c7-191">Obtiene o establece si un valor admite valores NULL.</span><span class="sxs-lookup"><span data-stu-id="a98c7-191">Gets or sets whether a value is nullable.</span></span> <span data-ttu-id="a98c7-192">Cuando se envía un valor de parámetro nulo al servidor, se debe especificar <xref:System.DBNull>, en lugar de `null` (`Nothing` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="a98c7-192">When you send a null parameter value to the server, you must specify <xref:System.DBNull>, rather than `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="a98c7-193">Para obtener más información acerca de los valores NULL de base de datos, vea [administrar valores NULL](handling-null-values.md).</span><span class="sxs-lookup"><span data-stu-id="a98c7-193">For more information about database nulls, see [Handling Null Values](handling-null-values.md).</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Precision%2A>|<span data-ttu-id="a98c7-194">Obtiene o establece el número máximo de dígitos usado para representar el valor.</span><span class="sxs-lookup"><span data-stu-id="a98c7-194">Gets or sets the maximum number of digits used to represent the value.</span></span> <span data-ttu-id="a98c7-195">Este valor se omite para los tipos de datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="a98c7-195">This setting is ignored for date and time data types.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Scale%2A>|<span data-ttu-id="a98c7-196">Obtiene o establece el número de posiciones decimales determinado para la parte de hora del valor de `Time`, `DateTime2` y `DateTimeOffset`.</span><span class="sxs-lookup"><span data-stu-id="a98c7-196">Gets or sets the number of decimal places to which the time portion of the value is resolved for `Time`, `DateTime2`,and `DateTimeOffset`.</span></span> <span data-ttu-id="a98c7-197">El valor predeterminado es 0, lo que significa que la escala real se deduce del valor y se envía al servidor.</span><span class="sxs-lookup"><span data-stu-id="a98c7-197">The default value is 0, which means that the actual scale is inferred from the value and sent to the server.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="a98c7-198">Se ignora para los tipos de datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="a98c7-198">Ignored for date and time data types.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="a98c7-199">Obtiene o establece el valor de parámetro.</span><span class="sxs-lookup"><span data-stu-id="a98c7-199">Gets or sets the parameter value.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="a98c7-200">Obtiene o establece el valor de parámetro.</span><span class="sxs-lookup"><span data-stu-id="a98c7-200">Gets or sets the parameter value.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="a98c7-201">Los valores de hora que son menores que cero o mayores o iguales que 24 horas producirán una excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="a98c7-201">Time values that are less than zero or greater than or equal to 24 hours will throw an <xref:System.ArgumentException>.</span></span>  
  
### <a name="creating-parameters"></a><span data-ttu-id="a98c7-202">Crear parámetros</span><span class="sxs-lookup"><span data-stu-id="a98c7-202">Creating Parameters</span></span>  

 <span data-ttu-id="a98c7-203">Para crear un objeto <xref:System.Data.SqlClient.SqlParameter>, se puede usar su constructor o bien se puede agregar a una colección <xref:System.Data.SqlClient.SqlCommand><xref:System.Data.SqlClient.SqlCommand.Parameters%2A> mediante una llamada al método `Add` de la colección <xref:System.Data.SqlClient.SqlParameterCollection>.</span><span class="sxs-lookup"><span data-stu-id="a98c7-203">You can create a <xref:System.Data.SqlClient.SqlParameter> object by using its constructor, or by adding it to a <xref:System.Data.SqlClient.SqlCommand><xref:System.Data.SqlClient.SqlCommand.Parameters%2A> collection by calling the `Add` method of the <xref:System.Data.SqlClient.SqlParameterCollection>.</span></span> <span data-ttu-id="a98c7-204">El método `Add` tomará como entrada los argumentos del constructor o un objeto de parámetro existente.</span><span class="sxs-lookup"><span data-stu-id="a98c7-204">The `Add` method will take as input either constructor arguments or an existing parameter object.</span></span>  
  
 <span data-ttu-id="a98c7-205">En las secciones siguientes de este tema se proporcionan ejemplos de cómo especificar parámetros de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="a98c7-205">The next sections in this topic provide examples of how to specify date and time parameters.</span></span> <span data-ttu-id="a98c7-206">Para obtener más ejemplos de cómo trabajar con parámetros, vea [Configurar parámetros y tipos de datos](../configuring-parameters-and-parameter-data-types.md) de parámetros y [parámetros DataAdapter](../dataadapter-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="a98c7-206">For additional examples of working with parameters, see [Configuring Parameters and Parameter Data Types](../configuring-parameters-and-parameter-data-types.md) and [DataAdapter Parameters](../dataadapter-parameters.md).</span></span>  
  
### <a name="date-example"></a><span data-ttu-id="a98c7-207">Ejemplo de date</span><span class="sxs-lookup"><span data-stu-id="a98c7-207">Date Example</span></span>  

 <span data-ttu-id="a98c7-208">El fragmento de código siguiente muestra cómo se especifica un parámetro `date`.</span><span class="sxs-lookup"><span data-stu-id="a98c7-208">The following code fragment demonstrates how to specify a `date` parameter.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Date";  
parameter.SqlDbType = SqlDbType.Date;  
parameter.Value = "2007/12/1";  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Date"  
parameter.SqlDbType = SqlDbType.Date  
parameter.Value = "2007/12/1"  
```  
  
### <a name="time-example"></a><span data-ttu-id="a98c7-209">Ejemplo de time</span><span class="sxs-lookup"><span data-stu-id="a98c7-209">Time Example</span></span>  

 <span data-ttu-id="a98c7-210">El fragmento de código siguiente muestra cómo se especifica un parámetro `time`.</span><span class="sxs-lookup"><span data-stu-id="a98c7-210">The following code fragment demonstrates how to specify a `time` parameter.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@time";  
parameter.SqlDbType = SqlDbType.Time;  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Time"  
parameter.SqlDbType = SqlDbType.Time  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
### <a name="datetime2-example"></a><span data-ttu-id="a98c7-211">Ejemplo de datetime2</span><span class="sxs-lookup"><span data-stu-id="a98c7-211">Datetime2 Example</span></span>  

 <span data-ttu-id="a98c7-212">En el fragmento de código siguiente se muestra cómo especificar un parámetro `datetime2` con las partes de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="a98c7-212">The following code fragment demonstrates how to specify a `datetime2` parameter with both the date and time parts.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Datetime2";  
parameter.SqlDbType = SqlDbType.DateTime2;  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Datetime2"  
parameter.SqlDbType = SqlDbType.DateTime2  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
### <a name="datetimeoffset-example"></a><span data-ttu-id="a98c7-213">Ejemplo de DateTimeOffSet</span><span class="sxs-lookup"><span data-stu-id="a98c7-213">DateTimeOffSet Example</span></span>  

 <span data-ttu-id="a98c7-214">En el fragmento de código siguiente se muestra cómo especificar un parámetro `DateTimeOffSet` con una fecha, una hora y un ajuste de zona horaria de 0.</span><span class="sxs-lookup"><span data-stu-id="a98c7-214">The following code fragment demonstrates how to specify a `DateTimeOffSet` parameter with a date, a time, and a time zone offset of 0.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@DateTimeOffSet";  
parameter.SqlDbType = SqlDbType.DateTimeOffSet;  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@DateTimeOffSet"  
parameter.SqlDbType = SqlDbType.DateTimeOffSet  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
### <a name="addwithvalue"></a><span data-ttu-id="a98c7-215">AddWithValue</span><span class="sxs-lookup"><span data-stu-id="a98c7-215">AddWithValue</span></span>  

 <span data-ttu-id="a98c7-216">También puede proporcionar parámetros mediante el método `AddWithValue` de un <xref:System.Data.SqlClient.SqlCommand>, como se muestra en el fragmento de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a98c7-216">You can also supply parameters by using the `AddWithValue` method of a <xref:System.Data.SqlClient.SqlCommand>, as shown in the following code fragment.</span></span> <span data-ttu-id="a98c7-217">Sin embargo, el método `AddWithValue` no permite especificar el valor <xref:System.Data.SqlClient.SqlParameter.DbType%2A> o <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="a98c7-217">However, the `AddWithValue` method does not allow you to specify the <xref:System.Data.SqlClient.SqlParameter.DbType%2A> or <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> for the parameter.</span></span>  
  
```csharp  
command.Parameters.AddWithValue(
    "@date", DateTimeOffset.Parse("16660902"));  
```  
  
```vb  
command.Parameters.AddWithValue( _  
    "@date", DateTimeOffset.Parse("16660902"))  
```  
  
 <span data-ttu-id="a98c7-218">El parámetro `@date` podría asignarse a un tipo de datos `date`, `datetime` o `datetime2` en el servidor.</span><span class="sxs-lookup"><span data-stu-id="a98c7-218">The `@date` parameter could map to a `date`, `datetime`, or `datetime2` data type on the server.</span></span> <span data-ttu-id="a98c7-219">Al trabajar con los nuevos tipos de datos de `datetime`, debe establecer explícitamente la propiedad <xref:System.Data.SqlDbType> del parámetro en el tipo de datos de la instancia.</span><span class="sxs-lookup"><span data-stu-id="a98c7-219">When working with the new `datetime` data types, you must explicitly set the parameter's <xref:System.Data.SqlDbType> property to the data type of the instance.</span></span> <span data-ttu-id="a98c7-220">El uso de <xref:System.Data.SqlDbType.Variant> o el suministro implícito de valores de parámetros puede causar problemas de compatibilidad con versiones anteriores de los tipos de datos `datetime` y `smalldatetime`.</span><span class="sxs-lookup"><span data-stu-id="a98c7-220">Using <xref:System.Data.SqlDbType.Variant> or implicitly supplying parameter values can cause problems with backward compatibility with the `datetime` and `smalldatetime` data types.</span></span>  
  
 <span data-ttu-id="a98c7-221">En la tabla siguiente se muestra qué valores `SqlDbTypes` se deducen a partir de los tipos de CLR:</span><span class="sxs-lookup"><span data-stu-id="a98c7-221">The following table shows which `SqlDbTypes` are inferred from which CLR types:</span></span>  
  
|<span data-ttu-id="a98c7-222">Tipo CLR</span><span class="sxs-lookup"><span data-stu-id="a98c7-222">CLR type</span></span>|<span data-ttu-id="a98c7-223">SqlDbType deducido</span><span class="sxs-lookup"><span data-stu-id="a98c7-223">Inferred SqlDbType</span></span>|  
|--------------|------------------------|  
|<span data-ttu-id="a98c7-224">DateTime</span><span class="sxs-lookup"><span data-stu-id="a98c7-224">DateTime</span></span>|<span data-ttu-id="a98c7-225">SqlDbType.DateTime</span><span class="sxs-lookup"><span data-stu-id="a98c7-225">SqlDbType.DateTime</span></span>|  
|<span data-ttu-id="a98c7-226">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="a98c7-226">TimeSpan</span></span>|<span data-ttu-id="a98c7-227">SqlDbType.Time</span><span class="sxs-lookup"><span data-stu-id="a98c7-227">SqlDbType.Time</span></span>|  
|<span data-ttu-id="a98c7-228">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a98c7-228">DateTimeOffset</span></span>|<span data-ttu-id="a98c7-229">SqlDbType.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a98c7-229">SqlDbType.DateTimeOffset</span></span>|  
  
## <a name="retrieving-date-and-time-data"></a><span data-ttu-id="a98c7-230">Recuperar datos de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="a98c7-230">Retrieving Date and Time Data</span></span>  

 <span data-ttu-id="a98c7-231">En la tabla siguiente se describen los métodos que se usan para recuperar valores de fecha y hora de SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="a98c7-231">The following table describes methods that are used to retrieve SQL Server 2008 date and time values.</span></span>  
  
|<span data-ttu-id="a98c7-232">Método SqlClient</span><span class="sxs-lookup"><span data-stu-id="a98c7-232">SqlClient method</span></span>|<span data-ttu-id="a98c7-233">Descripción</span><span class="sxs-lookup"><span data-stu-id="a98c7-233">Description</span></span>|  
|----------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|<span data-ttu-id="a98c7-234">Recupera el valor de columna especificado como una estructura <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="a98c7-234">Retrieves the specified column value as a <xref:System.DateTime> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTimeOffset%2A>|<span data-ttu-id="a98c7-235">Recupera el valor de columna especificado como una estructura <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="a98c7-235">Retrieves the specified column value as a <xref:System.DateTimeOffset> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>|<span data-ttu-id="a98c7-236">Devuelve el tipo específico del proveedor subyacente para el campo.</span><span class="sxs-lookup"><span data-stu-id="a98c7-236">Returns the type that is the underlying provider-specific type for the field.</span></span> <span data-ttu-id="a98c7-237">Devuelve los mismos tipos que `GetFieldType` para los nuevos tipos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="a98c7-237">Returns the same types as `GetFieldType` for new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>|<span data-ttu-id="a98c7-238">Recupera el valor de la columna especificada.</span><span class="sxs-lookup"><span data-stu-id="a98c7-238">Retrieves the value of the specified column.</span></span> <span data-ttu-id="a98c7-239">Devuelve los mismos tipos que `GetValue` para los nuevos tipos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="a98c7-239">Returns the same types as `GetValue` for the new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>|<span data-ttu-id="a98c7-240">Recupera los valores de la matriz especificada.</span><span class="sxs-lookup"><span data-stu-id="a98c7-240">Retrieves the values in the specified array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<span data-ttu-id="a98c7-241">Recupera el valor de la columna como <xref:System.Data.SqlTypes.SqlString>.</span><span class="sxs-lookup"><span data-stu-id="a98c7-241">Retrieves the column value as a <xref:System.Data.SqlTypes.SqlString>.</span></span> <span data-ttu-id="a98c7-242">Se produce <xref:System.InvalidCastException> si los datos no se pueden expresar como `SqlString`.</span><span class="sxs-lookup"><span data-stu-id="a98c7-242">An <xref:System.InvalidCastException> occurs if the data cannot be expressed as a `SqlString`.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>|<span data-ttu-id="a98c7-243">Recupera los datos de la columna como su `SqlDbType` predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a98c7-243">Retrieves column data as its default `SqlDbType`.</span></span> <span data-ttu-id="a98c7-244">Devuelve los mismos tipos que `GetValue` para los nuevos tipos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="a98c7-244">Returns the same types as `GetValue` for the new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>|<span data-ttu-id="a98c7-245">Recupera los valores de la matriz especificada.</span><span class="sxs-lookup"><span data-stu-id="a98c7-245">Retrieves the values in the specified array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A>|<span data-ttu-id="a98c7-246">Recupera el valor de columna como una cadena si Type System Version se ha establecido en SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a98c7-246">Retrieves the column value as a string if the Type System Version is set to SQL Server 2005.</span></span> <span data-ttu-id="a98c7-247">Se produce <xref:System.InvalidCastException> si los datos no se pueden expresar como una cadena.</span><span class="sxs-lookup"><span data-stu-id="a98c7-247">An <xref:System.InvalidCastException> occurs if the data cannot be expressed as a string.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetTimeSpan%2A>|<span data-ttu-id="a98c7-248">Recupera el valor de columna especificado como una estructura <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="a98c7-248">Retrieves the specified column value as a <xref:System.TimeSpan> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>|<span data-ttu-id="a98c7-249">Recupera el valor de columna especificado como su tipo CLR subyacente.</span><span class="sxs-lookup"><span data-stu-id="a98c7-249">Retrieves the specified column value as its underlying CLR type.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>|<span data-ttu-id="a98c7-250">Recupera los valores de columna de una matriz.</span><span class="sxs-lookup"><span data-stu-id="a98c7-250">Retrieves column values in an array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>|<span data-ttu-id="a98c7-251">Devuelve un valor <xref:System.Data.DataTable> que describe los metadatos del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="a98c7-251">Returns a <xref:System.Data.DataTable> that describes the metadata of the result set.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="a98c7-252">Los nuevos `SqlDbTypes` de fecha y hora no se admiten para el código que se ejecuta en proceso en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a98c7-252">The new date and time `SqlDbTypes` are not supported for code that is executing in-process in SQL Server.</span></span> <span data-ttu-id="a98c7-253">Se producirá una excepción si se pasa uno de estos tipos al servidor.</span><span class="sxs-lookup"><span data-stu-id="a98c7-253">An exception will be raised if one of these types is passed to the server.</span></span>  
  
## <a name="specifying-date-and-time-values-as-literals"></a><span data-ttu-id="a98c7-254">Especificar valores de fecha y hora como literales</span><span class="sxs-lookup"><span data-stu-id="a98c7-254">Specifying Date and Time Values as Literals</span></span>  

 <span data-ttu-id="a98c7-255">Puede especificar tipos de datos de fecha y hora mediante una variedad de diferentes formatos de cadena literales, que SQL Server evalúa luego en el entorno de ejecución, convirtiéndolos en estructuras de fecha y hora internas.</span><span class="sxs-lookup"><span data-stu-id="a98c7-255">You can specify date and time data types by using a variety of different literal string formats, which SQL Server then evaluates at run time, converting them to internal date/time structures.</span></span> <span data-ttu-id="a98c7-256">SQL Server reconoce los datos de fecha y hora que se incluyen entre comillas simples (').</span><span class="sxs-lookup"><span data-stu-id="a98c7-256">SQL Server recognizes date and time data that is enclosed in single quotation marks (').</span></span> <span data-ttu-id="a98c7-257">Los ejemplos siguientes demuestran algunos formatos:</span><span class="sxs-lookup"><span data-stu-id="a98c7-257">The following examples demonstrate some formats:</span></span>  
  
- <span data-ttu-id="a98c7-258">Formatos de fecha alfabéticos, como `'October 15, 2006'`.</span><span class="sxs-lookup"><span data-stu-id="a98c7-258">Alphabetic date formats, such as `'October 15, 2006'`.</span></span>  
  
- <span data-ttu-id="a98c7-259">Formatos de fecha numéricos, como `'10/15/2006'`.</span><span class="sxs-lookup"><span data-stu-id="a98c7-259">Numeric date formats, such as `'10/15/2006'`.</span></span>  
  
- <span data-ttu-id="a98c7-260">Formatos de cadena no separados, como `'20061015'`, que se interpretarán como 15 de octubre de 2006 si usa el formato de fecha estándar ISO.</span><span class="sxs-lookup"><span data-stu-id="a98c7-260">Unseparated string formats, such as `'20061015'`, which would be interpreted as October 15, 2006 if you are using the ISO standard date format.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a98c7-261">Puede encontrar documentación completa de todos los formatos de cadena literales y otras características de los tipos de datos de fecha y hora en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a98c7-261">You can find complete documentation for all of the literal string formats and other features of the date and time data types in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="a98c7-262">Los valores de hora que son menores que cero o mayores o iguales que 24 horas producirán una excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="a98c7-262">Time values that are less than zero or greater than or equal to 24 hours will throw an <xref:System.ArgumentException>.</span></span>  
  
## <a name="resources-in-sql-server-books-online"></a><span data-ttu-id="a98c7-263">Recursos en los Libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a98c7-263">Resources in SQL Server Books Online</span></span>  

 <span data-ttu-id="a98c7-264">Para obtener más información sobre cómo trabajar con valores de fecha y hora en SQL Server, vea los siguientes recursos en Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a98c7-264">For more information about working with date and time values in SQL Server, see the following resources in SQL Server Books Online.</span></span>  
  
|<span data-ttu-id="a98c7-265">Tema</span><span class="sxs-lookup"><span data-stu-id="a98c7-265">Topic</span></span>|<span data-ttu-id="a98c7-266">Descripción</span><span class="sxs-lookup"><span data-stu-id="a98c7-266">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a98c7-267">Tipos de datos y funciones de fecha y hora (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a98c7-267">Date and Time Data Types and Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)|<span data-ttu-id="a98c7-268">Proporciona información general sobre todos los tipos de datos y funciones de fecha y hora de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="a98c7-268">Provides an overview of all Transact-SQL date and time data types and functions.</span></span>|  
|<span data-ttu-id="a98c7-269">[Uso de datos de fecha y hora](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="a98c7-269">[Using Date and Time Data](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span></span>|<span data-ttu-id="a98c7-270">Proporciona información sobre las funciones y los tipos de datos de fecha y hora, además de ejemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="a98c7-270">Provides information about the date and time data types and functions, and examples of using them.</span></span>|  
|[<span data-ttu-id="a98c7-271">Tipos de datos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a98c7-271">Data Types (Transact-SQL)</span></span>](/sql/t-sql/data-types/data-types-transact-sql)|<span data-ttu-id="a98c7-272">Describe los tipos de datos del sistema en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a98c7-272">Describes system data types in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a98c7-273">Vea también</span><span class="sxs-lookup"><span data-stu-id="a98c7-273">See also</span></span>

- [<span data-ttu-id="a98c7-274">Asignaciones de tipos de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a98c7-274">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="a98c7-275">Configurar parámetros y tipos de datos de parámetros</span><span class="sxs-lookup"><span data-stu-id="a98c7-275">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="a98c7-276">Tipos de datos de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a98c7-276">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="a98c7-277">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a98c7-277">ADO.NET Overview</span></span>](../ado-net-overview.md)

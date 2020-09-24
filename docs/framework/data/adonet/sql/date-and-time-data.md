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
# <a name="date-and-time-data"></a>Datos de fecha y hora

SQL Server 2008 introduce nuevos tipos de datos para administrar la información de fecha y hora. Los nuevos tipos de datos incluyen tipos independientes para la fecha y la hora y tipos de datos expandidos con mayor control sobre el intervalo, la precisión y la zona horaria. A partir de .NET Framework versión 3.5 Service Pack (SP) 1, el proveedor de datos .NET Framework para SQL Server (<xref:System.Data.SqlClient>) proporciona compatibilidad total con todas las características nuevas del Motor de base de datos de SQL Server 2008. Debe instalar .NET Framework 3.5 SP1 (o posterior) para usar estas características nuevas con SqlClient.  
  
 Las versiones de SQL Server anteriores a SQL Server 2008 solo tenían dos tipos de datos para trabajar con valores de fecha y hora: `datetime` y `smalldatetime`. Ambos tipos de datos contienen el valor de fecha y el valor de hora, lo que dificulta trabajar solo con valores de fecha o de hora. Además, estos tipos de datos solo admiten las fechas posteriores a la introducción del calendario gregoriano en Inglaterra en 1753. Otra limitación es que estos tipos de datos más antiguos no reconocen la zona horaria, por lo que resulta difícil trabajar con datos que proceden de varias zonas horarias.  
  
 La documentación completa de los tipos de datos de SQL Server está disponible en Libros en pantalla de SQL Server. En la tabla siguiente se enumeran los temas de nivel básico específicos de la versión correspondientes a los datos de fecha y hora.  
  
 **Documentación de SQL Server**  
  
1. [Uso de datos de fecha y hora](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))  
  
## <a name="datetime-data-types-introduced-in-sql-server-2008"></a>Tipos de datos de fecha y hora introducidos en SQL Server 2008  

 En la tabla siguiente se describen los nuevos tipos de datos de fecha y hora.  
  
|Tipos de datos de SQL Server|Descripción|  
|--------------------------|-----------------|  
|`date`|El tipo de datos `date` tiene un intervalo del 1 de enero de 01 al 31 de diciembre de 9999, con una precisión de 1 día. El valor predeterminado es 1 de enero de 1900. El tamaño de almacenamiento es de 3 bytes.|  
|`time`|El tipo de datos `time` solo almacena valores de hora basados en un reloj de 24 horas. El tipo de datos `time` tiene un intervalo de 00:00:00,0000000 a 23:59:59,9999999 con una precisión de 100 nanosegundos. El valor predeterminado es 00:00:00,0000000 (medianoche). El tipo de datos `time` admite la precisión decimal de segundos definida por el usuario y su tamaño de almacenamiento varía entre 3 y 6 bytes en función de la precisión especificada.|  
|`datetime2`|El tipo de datos `datetime2` combina el intervalo y la precisión de los tipos de datos `date` y `time` en un solo tipo de datos.<br /><br /> Los valores predeterminados y los formatos de literales de cadena son los mismos que los definidos en los tipos de datos `date` y `time`.|  
|`datetimeoffset`|El tipo de datos `datetimeoffset` incluye todas las características de `datetime2` con un desfase de zona horaria adicional. El desfase de zona horaria se representa como [+&#124;-] HH:MM. HH es una cifra de dos dígitos que va de 00 a 14 y que representa el número de horas del desfase de zona horaria. MM es una cifra de dos dígitos que va de 00 a 59 y que representa el número minutos adicionales del desfase de zona horaria. Se admiten formatos de hora de hasta 100 nanosegundos. El signo + o- obligatorio indica si el ajuste de zona horaria se suma o se resta de la hora UTC (hora universal coordinada u hora del meridiano de Greenwich) para obtener la hora local.|  
  
> [!NOTE]
> Para obtener más información sobre el empleo de la palabra clave `Type System Version`, vea <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
## <a name="date-format-and-date-order"></a>Formato de fecha y orden de la fecha  

 La forma en que SQL Server analiza los valores de fecha y hora no solo depende de la versión del sistema de tipos y de la versión del servidor, sino también de la configuración de formato y idioma predeterminados del servidor. Una cadena de fecha que funcione para los formatos de fecha de un idioma podría ser irreconocible si la consulta se ejecuta por una conexión que utiliza una configuración de formato de fecha y idioma diferente.  
  
 La instrucción SET LANGUAGE de Transact-SQL establece implícitamente DATEFORMAT, que determina el orden de las partes de la fecha. Puede usar la instrucción SET DATEFORMAT de Transact-SQL en una conexión para eliminar la ambigüedad de los valores de fecha ordenando las partes de fecha según MDA, DMA, AMD, ADM, MAD o DAM.  
  
 Si no especifica ningún valor DATEFORMAT para la conexión, SQL Server utiliza el idioma predeterminado asociado a la conexión. Por ejemplo, una cadena de fecha de "01/02/03" se interpretaría como MDA (2 de enero de 2003) en un servidor con una configuración de idioma de inglés de Estados Unidos y como DMA (1 de febrero de 2003) en un servidor con una configuración de idioma de inglés británico. El año se determina mediante el uso de la regla del año límite de SQL Server, que define la fecha límite para asignar el valor del siglo. Para obtener más información, consulte la [opción de fecha límite de año de dos dígitos](/sql/database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option).  
  
> [!NOTE]
> No se admite el formato de fecha ADM al convertir de un formato de cadena a `date`, `time`, `datetime2` o `datetimeoffset`.  
  
 Para obtener más información sobre cómo SQL Server interpreta los datos de fecha y hora, vea [usar datos de fecha y hora](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100)).  
  
## <a name="datetime-data-types-and-parameters"></a>Tipos de datos de fecha y hora y parámetros  

 Se han agregado los siguientes valores de enumeración a <xref:System.Data.SqlDbType> para admitir los nuevos tipos de datos de fecha y hora.  
  
- `SqlDbType.Date`  
  
- `SqlDbType.Time`  
  
- `SqlDbType.DateTime2`  
  
- `SqlDbType.DateTimeOffSet`  

Puede especificar el tipo de datos de <xref:System.Data.SqlClient.SqlParameter> mediante una de las enumeraciones <xref:System.Data.SqlDbType> anteriores.

> [!NOTE]
> No puede establecer la propiedad `DbType` de un `SqlParameter` en `SqlDbType.Date`.

 También puede especificar el tipo de <xref:System.Data.SqlClient.SqlParameter> de forma genérica si establece la propiedad <xref:System.Data.SqlClient.SqlParameter.DbType%2A> de un objeto `SqlParameter` en un determinado valor de enumeración <xref:System.Data.DbType>. Se han agregado los siguientes valores de enumeración a <xref:System.Data.DbType> para admitir los tipos de datos `datetime2` y `datetimeoffset`:  
  
- DbType.DateTime2  
  
- DbType.DateTimeOffset  
  
 Estas nuevas enumeraciones complementan las enumeraciones `Date`, `Time` y `DateTime`, que ya existían en versiones anteriores de .NET Framework.  
  
 El tipo del proveedor de datos .NET Framework de un objeto de parámetro se deduce a partir del tipo de .NET Framework del valor del objeto de parámetro o a partir de la enumeración `DbType` del objeto de parámetro. No se han introducido nuevos tipos de datos de <xref:System.Data.SqlTypes> para admitir los nuevos tipos de datos de fecha y hora. En la tabla siguiente se describen las asignaciones entre los tipos de datos de fecha y hora de SQL Server 2008 y los tipos de datos de CLR.  
  
|Tipos de datos de SQL Server|Tipo de .NET Framework|System.Data.SqlDbType|System.Data.DbType|  
|--------------------------|-------------------------|---------------------------|------------------------|  
|date|System.DateTime|Date|Date|  
|time|System.TimeSpan|Time|Time|  
|datetime2|System.DateTime|DateTime2|DateTime2|  
|datetimeoffset|System.DateTimeOffset|DateTimeOffset|DateTimeOffset|  
|datetime|System.DateTime|DateTime|DateTime|  
|smalldatetime|System.DateTime|DateTime|DateTime|  
  
### <a name="sqlparameter-properties"></a>Propiedades de SqlParameter  

 En la tabla siguiente se describen las propiedades `SqlParameter` que son pertinentes para los tipos de datos de fecha y hora.  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.IsNullable%2A>|Obtiene o establece si un valor admite valores NULL. Cuando se envía un valor de parámetro nulo al servidor, se debe especificar <xref:System.DBNull>, en lugar de `null` (`Nothing` en Visual Basic). Para obtener más información acerca de los valores NULL de base de datos, vea [administrar valores NULL](handling-null-values.md).|  
|<xref:System.Data.SqlClient.SqlParameter.Precision%2A>|Obtiene o establece el número máximo de dígitos usado para representar el valor. Este valor se omite para los tipos de datos de fecha y hora.|  
|<xref:System.Data.SqlClient.SqlParameter.Scale%2A>|Obtiene o establece el número de posiciones decimales determinado para la parte de hora del valor de `Time`, `DateTime2` y `DateTimeOffset`. El valor predeterminado es 0, lo que significa que la escala real se deduce del valor y se envía al servidor.|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|Se ignora para los tipos de datos de fecha y hora.|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|Obtiene o establece el valor de parámetro.|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|Obtiene o establece el valor de parámetro.|  
  
> [!NOTE]
> Los valores de hora que son menores que cero o mayores o iguales que 24 horas producirán una excepción <xref:System.ArgumentException>.  
  
### <a name="creating-parameters"></a>Crear parámetros  

 Para crear un objeto <xref:System.Data.SqlClient.SqlParameter>, se puede usar su constructor o bien se puede agregar a una colección <xref:System.Data.SqlClient.SqlCommand><xref:System.Data.SqlClient.SqlCommand.Parameters%2A> mediante una llamada al método `Add` de la colección <xref:System.Data.SqlClient.SqlParameterCollection>. El método `Add` tomará como entrada los argumentos del constructor o un objeto de parámetro existente.  
  
 En las secciones siguientes de este tema se proporcionan ejemplos de cómo especificar parámetros de fecha y hora. Para obtener más ejemplos de cómo trabajar con parámetros, vea [Configurar parámetros y tipos de datos](../configuring-parameters-and-parameter-data-types.md) de parámetros y [parámetros DataAdapter](../dataadapter-parameters.md).  
  
### <a name="date-example"></a>Ejemplo de date  

 El fragmento de código siguiente muestra cómo se especifica un parámetro `date`.  
  
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
  
### <a name="time-example"></a>Ejemplo de time  

 El fragmento de código siguiente muestra cómo se especifica un parámetro `time`.  
  
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
  
### <a name="datetime2-example"></a>Ejemplo de datetime2  

 En el fragmento de código siguiente se muestra cómo especificar un parámetro `datetime2` con las partes de fecha y hora.  
  
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
  
### <a name="datetimeoffset-example"></a>Ejemplo de DateTimeOffSet  

 En el fragmento de código siguiente se muestra cómo especificar un parámetro `DateTimeOffSet` con una fecha, una hora y un ajuste de zona horaria de 0.  
  
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
  
### <a name="addwithvalue"></a>AddWithValue  

 También puede proporcionar parámetros mediante el método `AddWithValue` de un <xref:System.Data.SqlClient.SqlCommand>, como se muestra en el fragmento de código siguiente. Sin embargo, el método `AddWithValue` no permite especificar el valor <xref:System.Data.SqlClient.SqlParameter.DbType%2A> o <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> para el parámetro.  
  
```csharp  
command.Parameters.AddWithValue(
    "@date", DateTimeOffset.Parse("16660902"));  
```  
  
```vb  
command.Parameters.AddWithValue( _  
    "@date", DateTimeOffset.Parse("16660902"))  
```  
  
 El parámetro `@date` podría asignarse a un tipo de datos `date`, `datetime` o `datetime2` en el servidor. Al trabajar con los nuevos tipos de datos de `datetime`, debe establecer explícitamente la propiedad <xref:System.Data.SqlDbType> del parámetro en el tipo de datos de la instancia. El uso de <xref:System.Data.SqlDbType.Variant> o el suministro implícito de valores de parámetros puede causar problemas de compatibilidad con versiones anteriores de los tipos de datos `datetime` y `smalldatetime`.  
  
 En la tabla siguiente se muestra qué valores `SqlDbTypes` se deducen a partir de los tipos de CLR:  
  
|Tipo CLR|SqlDbType deducido|  
|--------------|------------------------|  
|DateTime|SqlDbType.DateTime|  
|TimeSpan|SqlDbType.Time|  
|DateTimeOffset|SqlDbType.DateTimeOffset|  
  
## <a name="retrieving-date-and-time-data"></a>Recuperar datos de fecha y hora  

 En la tabla siguiente se describen los métodos que se usan para recuperar valores de fecha y hora de SQL Server 2008.  
  
|Método SqlClient|Descripción|  
|----------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|Recupera el valor de columna especificado como una estructura <xref:System.DateTime>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTimeOffset%2A>|Recupera el valor de columna especificado como una estructura <xref:System.DateTimeOffset>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>|Devuelve el tipo específico del proveedor subyacente para el campo. Devuelve los mismos tipos que `GetFieldType` para los nuevos tipos de fecha y hora.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>|Recupera el valor de la columna especificada. Devuelve los mismos tipos que `GetValue` para los nuevos tipos de fecha y hora.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>|Recupera los valores de la matriz especificada.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|Recupera el valor de la columna como <xref:System.Data.SqlTypes.SqlString>. Se produce <xref:System.InvalidCastException> si los datos no se pueden expresar como `SqlString`.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>|Recupera los datos de la columna como su `SqlDbType` predeterminada. Devuelve los mismos tipos que `GetValue` para los nuevos tipos de fecha y hora.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>|Recupera los valores de la matriz especificada.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A>|Recupera el valor de columna como una cadena si Type System Version se ha establecido en SQL Server 2005. Se produce <xref:System.InvalidCastException> si los datos no se pueden expresar como una cadena.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetTimeSpan%2A>|Recupera el valor de columna especificado como una estructura <xref:System.TimeSpan>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>|Recupera el valor de columna especificado como su tipo CLR subyacente.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>|Recupera los valores de columna de una matriz.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>|Devuelve un valor <xref:System.Data.DataTable> que describe los metadatos del conjunto de resultados.|  
  
> [!NOTE]
> Los nuevos `SqlDbTypes` de fecha y hora no se admiten para el código que se ejecuta en proceso en SQL Server. Se producirá una excepción si se pasa uno de estos tipos al servidor.  
  
## <a name="specifying-date-and-time-values-as-literals"></a>Especificar valores de fecha y hora como literales  

 Puede especificar tipos de datos de fecha y hora mediante una variedad de diferentes formatos de cadena literales, que SQL Server evalúa luego en el entorno de ejecución, convirtiéndolos en estructuras de fecha y hora internas. SQL Server reconoce los datos de fecha y hora que se incluyen entre comillas simples ('). Los ejemplos siguientes demuestran algunos formatos:  
  
- Formatos de fecha alfabéticos, como `'October 15, 2006'`.  
  
- Formatos de fecha numéricos, como `'10/15/2006'`.  
  
- Formatos de cadena no separados, como `'20061015'`, que se interpretarán como 15 de octubre de 2006 si usa el formato de fecha estándar ISO.  
  
> [!NOTE]
> Puede encontrar documentación completa de todos los formatos de cadena literales y otras características de los tipos de datos de fecha y hora en los Libros en pantalla de SQL Server.  
  
 Los valores de hora que son menores que cero o mayores o iguales que 24 horas producirán una excepción <xref:System.ArgumentException>.  
  
## <a name="resources-in-sql-server-books-online"></a>Recursos en los Libros en pantalla de SQL Server  

 Para obtener más información sobre cómo trabajar con valores de fecha y hora en SQL Server, vea los siguientes recursos en Libros en pantalla de SQL Server.  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Tipos de datos y funciones de fecha y hora (Transact-SQL)](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)|Proporciona información general sobre todos los tipos de datos y funciones de fecha y hora de Transact-SQL.|  
|[Uso de datos de fecha y hora](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))|Proporciona información sobre las funciones y los tipos de datos de fecha y hora, además de ejemplos de uso.|  
|[Tipos de datos (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql)|Describe los tipos de datos del sistema en SQL Server.|  
  
## <a name="see-also"></a>Vea también

- [Asignaciones de tipos de datos de SQL Server](../sql-server-data-type-mappings.md)
- [Configurar parámetros y tipos de datos de parámetros](../configuring-parameters-and-parameter-data-types.md)
- [Tipos de datos de SQL Server y ADO.NET](sql-server-data-types.md)
- [Información general de ADO.NET](../ado-net-overview.md)

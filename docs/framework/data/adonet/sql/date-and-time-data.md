---
title: Datos de fecha y hora
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6f5ff56a-a57e-49d7-8ae9-bbed697e42e3
ms.openlocfilehash: bdcbaffe1be4933b89c7bf0d3a11e1bb871bc2bd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450303"
---
# <a name="date-and-time-data"></a>Datos de fecha y hora
SQL Server 2008 incluye nuevos tipos de datos para administrar la información de fecha y hora. Los nuevos tipos de datos incluyen tipos individuales de fecha y hora y tipos de datos expandidos con mayor intervalo, precisión y conocimiento de la zona horaria. A partir de .NET Framework versión 3.5 Service Pack (SP) 1, el proveedor de datos .NET Framework para SQL Server (<xref:System.Data.SqlClient>) proporciona compatibilidad total con todas las características nuevas del Motor de base de datos de SQL Server 2008. Debe instalar .NET Framework 3.5 SP1 (o posterior) para usar estas características nuevas con SqlClient.  
  
 Las versiones de SQL Server anteriores a SQL Server 2008 solo tenían dos tipos de datos para trabajar con valores de fecha y hora: `datetime` y `smalldatetime`. Ambos tipos de datos contienen el valor de fecha y el valor de hora, lo que dificulta trabajar solo con valores de fecha o de hora. Por otra parte, solo se admiten las fechas posteriores a la introducción del calendario gregoriano en Inglaterra en 1753. Otra limitación es que estos tipos de datos anteriores no reconocen la zona horaria, por lo que resulta difícil trabajar con datos que proceden de varias zonas horarias.  
  
 La documentación completa de los tipos de datos de SQL Server está disponible en los Libros en pantalla de SQL Server. En la tabla siguiente se enumeran los temas de nivel básico específicos de la versión correspondientes a los datos de fecha y hora.  
  
 **Documentación de SQL Server**  
  
1. [Uso de datos de fecha y hora](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))  
  
## <a name="datetime-data-types-introduced-in-sql-server-2008"></a>Tipos de datos de fecha y hora introducidos en SQL Server 2008  
 En la tabla siguiente se describen los tipos de datos de fecha y hora nuevos.  
  
|Tipos de datos de SQL Server|Descripción|  
|--------------------------|-----------------|  
|`date`|El tipo de datos `date` tiene un intervalo del 1 de enero de 01 al 31 de diciembre de 9999, con una precisión de 1 día. El valor predeterminado es el 1 de enero de 1900. El tamaño de almacenamiento es de 3 bytes.|  
|`time`|El tipo de datos `time` solo almacena valores de hora basados en un reloj de 24 horas. El tipo de datos `time` admite un intervalo de 00:00:00.0000000 a 23:59:59.9999999 con una precisión de 100 nanosegundos. El valor predeterminado es 00:00:00.0000000 (medianoche). El tipo de datos `time` admite la precisión decimal de segundos definida por el usuario y su tamaño de almacenamiento varía entre 3 y 6 bytes en función de la precisión especificada.|  
|`datetime2`|El tipo de datos `datetime2` combina el intervalo y la precisión de los tipos de datos `date` y `time` en un único tipo de datos.<br /><br /> Los valores predeterminados y los formatos de literal de cadena son los mismos que los definidos en los tipos de datos `date` y `time`.|  
|`datetimeoffset`|El tipo de datos `datetimeoffset` incluye todas las características de `datetime2` con un desfase de zona horaria adicional. El desfase de zona horaria se representa como [+&#124;-] HH:MM. HH es una cifra de dos dígitos que va de 00 a 14 y que representa el número de horas del desfase de zona horaria. MM es una cifra de dos dígitos que va de 00 a 59 y que representa el número minutos adicionales del desfase de zona horaria. Se admiten formatos de hora de hasta 100 nanosegundos. El signo + o - obligatorio indica si el desfase de zona horaria se suma o resta de la hora UTC (hora universal coordinada u hora del meridiano de Greenwich) para obtener la hora local.|  
  
> [!NOTE]
> Para obtener más información sobre el empleo de la palabra clave `Type System Version`, vea <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
## <a name="date-format-and-date-order"></a>Formato de fecha y orden de la fecha  
 El modo en que SQL Server analiza los valores de fecha y hora depende no solo de la versión del sistema de tipos y de la versión del servidor, sino también de los valores de idioma y formato predeterminados del servidor. Una cadena de fecha que funcione para los formatos de fecha de un idioma puede resultar irreconocible si la consulta se ejecuta mediante una conexión que utiliza un valor diferente de idioma y formato de fechas.  
  
 La instrucción SET LANGUAGE de Transact-SQL establece implícitamente el DATEFORMAT que determina el orden de los componentes de la fecha. Puede utilizar la instrucción SET DATEFORMAT de Transact-SQL en una conexión para eliminar la ambigüedad de los valores de fecha ordenando los componentes de la fecha en el orden de MDA, DMA, AMD, ADM, MAD o DAM.  
  
 Si no especifica ningún DATEFORMAT para la conexión, SQL Server utiliza el idioma predeterminado asociado a la conexión. Por ejemplo, una cadena de fecha de '01/02/03' se interpretaría como MDA (2 de enero de 2003) en un servidor con un valor de idioma de inglés de Estados Unidos y como DMA (1 de febrero de 2003) en un servidor con un valor de fecha de inglés británico. El año se determina mediante la regla de año límite de SQL Server, que define la fecha límite para asignar el valor de siglo. Para obtener más información, consulte la [opción de fecha límite de año de dos dígitos](/sql/database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option).  
  
> [!NOTE]
> El formato de fecha ADM no se admite al convertir de un formato de cadena en `date`, `time`, `datetime2` o `datetimeoffset`.  
  
 Para obtener más información sobre cómo SQL Server interpreta los datos de fecha y hora, vea [usar datos de fecha y hora](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms180878(v=sql.100)).  
  
## <a name="datetime-data-types-and-parameters"></a>Tipos de datos de fecha y hora y parámetros  
 En <xref:System.Data.SqlDbType> se han agregado las siguientes enumeraciones para admitir los nuevos tipos de datos de fecha y hora.  
  
- `SqlDbType.Date`  
  
- `SqlDbType.Time`  
  
- `SqlDbType.DateTime2`  
  
- `SqlDbType.DateTimeOffSet`  

Puede especificar el tipo de datos de <xref:System.Data.SqlClient.SqlParameter> mediante una de las enumeraciones <xref:System.Data.SqlDbType> anteriores. 

> [!NOTE]
> No se puede establecer la propiedad `DbType` de una `SqlParameter` en `SqlDbType.Date`.

 También puede especificar el tipo de <xref:System.Data.SqlClient.SqlParameter> de forma genérica si establece la propiedad <xref:System.Data.SqlClient.SqlParameter.DbType%2A> de un objeto `SqlParameter` en un determinado valor de enumeración <xref:System.Data.DbType>. Se han agregado los siguientes valores de enumeración a <xref:System.Data.DbType> para admitir los tipos de datos `datetime2` y `datetimeoffset`:  
  
- DbType.DateTime2  
  
- DbType.DateTimeOffset  
  
 Estas nuevas enumeraciones complementan las enumeraciones `Date`, `Time` y `DateTime`, que ya existían en versiones anteriores de .NET Framework.  
  
 El tipo del proveedor de datos .NET Framework de un objeto de parámetro se deduce a partir del tipo de .NET Framework del valor del objeto de parámetro o a partir de la enumeración `DbType` del objeto de parámetro. No se han agregado nuevos tipos de datos <xref:System.Data.SqlTypes> para admitir los nuevos tipos de datos de fecha y hora. En la siguiente tabla se describen las asignaciones entre los tipos de datos de fecha y hora de SQL Server 2008 y los tipos de datos CLR.  
  
|Tipos de datos de SQL Server|Tipo de .NET Framework|System.Data.SqlDbType|System.Data.DbType|  
|--------------------------|-------------------------|---------------------------|------------------------|  
|date|System.DateTime|Date|Date|  
|time|System.TimeSpan|Time|Time|  
|datetime2|System.DateTime|DateTime2|DateTime2|  
|datetimeoffset|System.DateTimeOffset|DateTimeOffset|DateTimeOffset|  
|datetime|System.DateTime|DateTime|DateTime|  
|smalldatetime|System.DateTime|DateTime|DateTime|  
  
### <a name="sqlparameter-properties"></a>Propiedades de SqlParameter  
 En la tabla siguiente se describen las propiedades de `SqlParameter` pertinentes de los tipos de datos de fecha y hora.  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.IsNullable%2A>|Obtiene o establece si un valor acepta valores NULL. Cuando envía un valor de parámetro nulo al servidor, debe especificar <xref:System.DBNull> en lugar de `null` (`Nothing` en Visual Basic). Para obtener más información sobre valores nulos de base de datos, consulte [Handling Null Values](handling-null-values.md).|  
|<xref:System.Data.SqlClient.SqlParameter.Precision%2A>|Obtiene o establece el número máximo de dígitos usado para representar el valor. Este valor se omite para los tipos de datos de fecha y hora.|  
|<xref:System.Data.SqlClient.SqlParameter.Scale%2A>|Obtiene o establece el número de posiciones decimales determinado para la parte de hora del valor de `Time`, `DateTime2` y `DateTimeOffset`. El valor predeterminado es 0, que significa que la escala real se deduce del valor y se envía al servidor.|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|Se omite para los tipos de datos de fecha y hora.|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|Obtiene o establece el valor de parámetro.|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|Obtiene o establece el valor de parámetro.|  
  
> [!NOTE]
> Los valores de hora que son menores que cero o mayores o iguales que 24 horas producirán una excepción <xref:System.ArgumentException>.  
  
### <a name="creating-parameters"></a>Crear parámetros  
 Para crear un objeto <xref:System.Data.SqlClient.SqlParameter>, se puede usar su constructor o bien se puede agregar a una colección <xref:System.Data.SqlClient.SqlCommand><xref:System.Data.SqlClient.SqlCommand.Parameters%2A> mediante una llamada al método `Add` de la colección <xref:System.Data.SqlClient.SqlParameterCollection>. El método `Add` acepta como entrada argumentos del constructor o cualquier objeto de parámetro ya existente.  
  
 En las secciones siguientes de este tema se proporcionan ejemplos de cómo especificar los parámetros de fecha y hora. Para obtener más ejemplos de cómo trabajar con parámetros, vea [Configurar parámetros y tipos de datos](../configuring-parameters-and-parameter-data-types.md) de parámetros y [parámetros DataAdapter](../dataadapter-parameters.md).  
  
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
 El fragmento de código siguiente muestra cómo se especifica un parámetro `datetime2` con los componentes de fecha y hora.  
  
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
 El fragmento de código siguiente muestra cómo se especifica un parámetro `DateTimeOffSet` con una fecha, una hora y un desplazamiento de zona horaria de 0.  
  
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
 También puede proporcionar parámetros mediante el método `AddWithValue` de <xref:System.Data.SqlClient.SqlCommand>, como se muestra en el fragmento de código siguiente. No obstante, el método `AddWithValue` no permite especificar la propiedad <xref:System.Data.SqlClient.SqlParameter.DbType%2A> o <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> del parámetro.  
  
```csharp  
command.Parameters.AddWithValue(   
    "@date", DateTimeOffset.Parse("16660902"));  
```  
  
```vb  
command.Parameters.AddWithValue( _  
    "@date", DateTimeOffset.Parse("16660902"))  
```  
  
 El parámetro `@date` podría asignarse a un tipo de datos `date`, `datetime` o `datetime2` en el servidor. Al trabajar con los nuevos tipos de datos `datetime`, debe establecer explícitamente la propiedad <xref:System.Data.SqlDbType> del parámetro en el tipo de datos de la instancia. El uso de <xref:System.Data.SqlDbType.Variant> o la provisión implícita de valores de parámetro puede ocasionar problemas de compatibilidad con versiones anteriores con los tipos de datos `datetime` y `smalldatetime`.  
  
 En la tabla siguiente se muestra qué `SqlDbTypes` se deducen de los tipos CLR:  
  
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
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>|Devuelve el tipo subyacente del tipo específico de proveedor del campo. Devuelve los mismos tipos que `GetFieldType` en los nuevos tipos de fecha y hora.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>|Recupera el valor de la columna especificada. Devuelve los mismos tipos que `GetValue` en los nuevos tipos de fecha y hora.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>|Recupera los valores de la matriz especificada.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|Recupera el valor de columna como una estructura <xref:System.Data.SqlTypes.SqlString>. Si los datos no se pueden expresar como una estructura <xref:System.InvalidCastException>, se produce una clase `SqlString`.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>|Recupera datos de columna como su enumeración `SqlDbType` predeterminada. Devuelve los mismos tipos que `GetValue` en los nuevos tipos de fecha y hora.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>|Recupera los valores de la matriz especificada.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A>|Recupera el valor de columna como una cadena si Type System Version se ha establecido en SQL Server 2005. Si los datos no se pueden expresar como una cadena, se produce una clase <xref:System.InvalidCastException>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetTimeSpan%2A>|Recupera el valor de columna especificado como una estructura <xref:System.TimeSpan>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>|Recupera el valor de columna especificado como su tipo CLR subyacente.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>|Recupera los valores de columna de una matriz.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>|Devuelve una clase <xref:System.Data.DataTable> que describe los metadatos del conjunto de resultados.|  
  
> [!NOTE]
> Los nuevos `SqlDbTypes` de fecha y hora no se admiten en el código que se ejecuta en proceso en SQL Server. Se producirá una excepción si se pasa uno de estos tipos al servidor.  
  
## <a name="specifying-date-and-time-values-as-literals"></a>Especificar valores de fecha y hora como literales  
 Puede especificar los tipos de datos de fecha y hora mediante una variedad de formatos de cadena de literales distintos, que SQL Server evalúa después en tiempo de ejecución, y los convierte en estructuras de fecha y hora internas. SQL Server reconoce los datos de fecha y hora escritos entre comillas simples ('). Los ejemplos siguientes explican algunos formatos:  
  
- Formatos alfabéticos de fecha, como `'October 15, 2006'`.  
  
- Formatos numéricos de fecha, como `'10/15/2006'`.  
  
- Formatos de cadena sin separación, como `'20061015'`, que se interpretarían como 15 de octubre de 2006 si utiliza el formato de fecha estándar ISO.  
  
> [!NOTE]
> Puede encontrar documentación completa de todos los formatos de cadena de literales y otras características de los tipos de datos de fecha y hora en los Libros en pantalla de SQL Server.  
  
 Los valores de hora que son menores que cero o mayores o iguales que 24 horas producirán una excepción <xref:System.ArgumentException>.  
  
## <a name="resources-in-sql-server-books-online"></a>Recursos en los Libros en pantalla de SQL Server  
 Para obtener más información sobre cómo trabajar con valores de fecha y hora en SQL Server, vea los siguientes recursos en Libros en pantalla de SQL Server.  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Tipos de datos y funciones de fecha y hora (Transact-SQL)](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)|Proporciona información general sobre todos los tipos de datos y funciones de fecha y hora de Transact-SQL.|  
|[Uso de datos de fecha y hora](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))|Proporciona información sobre las funciones y los tipos de datos de fecha y hora, además de ejemplos de uso.|  
|[Tipos de datos (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql)|Describe los tipos de datos del sistema en SQL Server.|  
  
## <a name="see-also"></a>Consulte también

- [Asignaciones de tipos de datos de SQL Server](../sql-server-data-type-mappings.md)
- [Configuración de parámetros y tipos de datos de parámetros](../configuring-parameters-and-parameter-data-types.md)
- [Tipos de datos de SQL Server y ADO.NET](sql-server-data-types.md)
- [Información general sobre ADO.NET](../ado-net-overview.md)

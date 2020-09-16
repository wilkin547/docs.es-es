---
title: Asignación de tipos entre CLR y SQL
ms.date: 07/23/2018
ms.assetid: 4ed76327-54a7-414b-82a9-7579bfcec04b
ms.openlocfilehash: 6d0a1bca5baade1bab6042bb7b7ab8e2d1353360
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555606"
---
# <a name="sql-clr-type-mapping"></a>Asignación de tipos entre CLR y SQL
En LINQ to SQL, el modelo de datos de una base de datos relacional se asigna a un modelo de objetos expresado en el lenguaje de programación que prefiera. Cuando la aplicación se ejecuta, LINQ to SQL convierte las consultas integradas del lenguaje del modelo de objetos a SQL y las envía a la base de datos para su ejecución. Cuando la base de datos devuelve los resultados, LINQ to SQL los vuelve a convertir en objetos con los que pueda trabajar en su propio lenguaje de programación.  
  
 Para traducir los datos entre el modelo de objetos y la base de datos, se debe definir una *asignación de tipos* . LINQ to SQL utiliza una asignación de tipos para que cada tipo de Common Language Runtime (CLR) se corresponda con un tipo de SQL Server concreto. Las asignaciones de tipos y otra información de asignación, como las relaciones de tablas y estructuras de bases de datos, se pueden definir en el modelo de objetos con una asignación basada en atributos. Opcionalmente, la información de asignación se puede especificar fuera del modelo de objetos con un archivo de asignación externo. Para obtener más información, consulte [asignación basada en atributos](attribute-based-mapping.md) y [asignación externa](external-mapping.md).  
  
 En este tema se tratan los puntos siguientes:  
  
- [Asignación de tipos predeterminados](#DefaultTypeMapping)  
  
- [Matriz de comportamiento de la asignación de tipos en tiempo de ejecución](#BehaviorMatrix)  
  
- [Diferencias de comportamiento entre la ejecución de CLR y SQL](#BehaviorDiffs)  
  
- [Asignación de enumeración](#EnumMapping)  
  
- [Asignación numérica](#NumericMapping)  
  
- [Asignación de texto y XML](#TextMapping)  
  
- [Asignación de fecha y hora](#DateMapping)  
  
- [Asignación binaria](#BinaryMapping)  
  
- [Asignaciones varias](#MiscMapping)  
  
<a name="DefaultTypeMapping"></a>
## <a name="default-type-mapping"></a>Asignación de tipos predeterminados  
 Puede crear automáticamente el modelo de objetos o el archivo de asignación con Object Relational Designer o la herramienta de línea de comandos SQLMetal. Las asignaciones de tipos predeterminadas de estas herramientas definen qué tipos de CLR se deben elegir para asignarlos a columnas en la base de datos SQL Server. Para obtener más información sobre el uso de estas herramientas, vea [crear el modelo de objetos](creating-the-object-model.md).  
  
 También puede utilizar el método <xref:System.Data.Linq.DataContext.CreateDatabase%2A> para crear una base de datos de SQL Server según la información de asignación del modelo de objetos o del archivo de asignación externo. Las asignaciones de tipos predeterminadas del método <xref:System.Data.Linq.DataContext.CreateDatabase%2A> definen qué tipo de columnas de SQL Server se deben crear para asignarlas a los tipos de CLR en el modelo de objetos. Para obtener más información, consulte [Cómo: crear dinámicamente una base de datos](how-to-dynamically-create-a-database.md).  
  
<a name="BehaviorMatrix"></a>
## <a name="type-mapping-run-time-behavior-matrix"></a>Matriz de comportamiento de la asignación de tipos en tiempo de ejecución  
 En el diagrama siguiente se muestra el comportamiento de las asignaciones de tipos específicos que se espera en tiempo de ejecución, cuando los datos se recuperan de la base de datos o se guardan en ella. Con la excepción de la serialización, LINQ to SQL no admite la asignación entre los tipos de datos de CLR o SQL Server no especificados en esta matriz. Para obtener más información sobre la compatibilidad con la serialización, vea [serialización binaria](#BinarySerialization).  

![SQL Server a la tabla de asignación de tipos de datos CLR de SQL](./media/sql-clr-type-mapping.png)

> [!NOTE]
> Algunas asignaciones de tipos pueden tener como resultado excepciones de desbordamiento o de pérdida de datos mientras se convierten a la base de datos o desde ella.  
  
### <a name="custom-type-mapping"></a>Asignación de tipos personalizados  
 Con LINQ to SQL, no está limitado a usar las asignaciones de tipos predeterminadas de Object Relational Designer, SQLMetal y el método <xref:System.Data.Linq.DataContext.CreateDatabase%2A>. Puede crear asignaciones de tipos personalizadas especificándolas explícitamente en un archivo DBML. Después, puede usar ese archivo para crear el código del modelo de objetos y el archivo de asignación. Para obtener más información, vea [asignaciones de tipos personalizados de SQL-CLR](sql-clr-custom-type-mappings.md).  
  
<a name="BehaviorDiffs"></a>
## <a name="behavior-differences-between-clr-and-sql-execution"></a>Diferencias de comportamiento entre la ejecución de CLR y SQL  
 Debido a las diferencias entre CLR y SQL Server en cuanto a la precisión y la ejecución, puede recibir diferentes resultados o experimentar un comportamiento distinto en función de dónde se realicen los cálculos. Los cálculos realizados en las consultas LINQ to SQL se traducen, de hecho, a Transact-SQL y después se ejecutan en la base de datos de SQL Server. Los cálculos realizados fuera de las consultas LINQ to SQL se ejecutan en el contexto de CLR.  
  
 Por ejemplo, a continuación se indican algunas diferencias de comportamiento entre CLR y SQL Server:  
  
- SQL Server ordena ciertos tipos de datos de forma diferente a los datos del tipo equivalente en CLR. Por ejemplo, los datos de SQL Server del tipo `UNIQUEIDENTIFIER` se ordenan de forma diferente a los datos de CLR del tipo <xref:System.Guid?displayProperty=nameWithType>.  
  
- SQL Server trata ciertas operaciones de comparación de cadenas de forma diferente a CLR. En SQL Server, el comportamiento de comparación de cadenas depende de la configuración de intercalación del servidor. Para obtener más información, vea [trabajar con intercalaciones](/previous-versions/sql/sql-server-2008-r2/ms187582(v=sql.105)) en el libros en pantalla de Microsoft SQL Server.  
  
- SQL Server puede devolver valores diferentes a los que devuelve CLR para algunas funciones asignadas. Por ejemplo, las funciones de igualdad tendrán resultados distintos porque SQL Server considera que dos cadenas son iguales si solo se diferencian en el espacio en blanco final, mientras que CLR considera que no son iguales.  
  
<a name="EnumMapping"></a>
## <a name="enum-mapping"></a>Asignación de enumeración  
 LINQ to SQL admite la asignación del tipo <xref:System.Enum?displayProperty=nameWithType> de CLR a tipos de SQL Server de dos maneras:  
  
- Asignación a tipos SQL numéricos (`TINYINT`, `SMALLINT`, `INT`, `BIGINT`)  
  
     Al asignar un tipo <xref:System.Enum?displayProperty=nameWithType> de CLR a un tipo numérico de SQL, el valor entero subyacente del tipo <xref:System.Enum?displayProperty=nameWithType> de CLR se asigna al valor de la columna de base de datos de SQL Server. Por ejemplo, si un elemento <xref:System.Enum?displayProperty=nameWithType> denominado `DaysOfWeek` contiene un miembro denominado `Tue` con un valor entero subyacente de 3, ese miembro se asigna a un valor de base de datos de 3.  
  
- Asignación a tipos SQL de texto (`CHAR`, `NCHAR`, `VARCHAR`, `NVARCHAR`)  
  
     Al asignar un tipo <xref:System.Enum?displayProperty=nameWithType> de CLR a un tipo de texto de SQL, el valor de la base de datos SQL se asigna a los nombres de los miembros <xref:System.Enum?displayProperty=nameWithType> de CLR. Por ejemplo, si un tipo <xref:System.Enum?displayProperty=nameWithType> denominado `DaysOfWeek` contiene un miembro denominado `Tue` con un valor entero subyacente de 3, ese miembro se asigna a un valor de base de datos de `Tue`.  
  
> [!NOTE]
> Cuando los tipos de texto de SQL se asignan a <xref:System.Enum?displayProperty=nameWithType> de CLR, solo se incluyen los nombres de los miembros <xref:System.Enum> en la columna de SQL asignada. No se admiten otros valores en la columna de SQL asignada a <xref:System.Enum>.  
  
 Object Relational Designer y la herramienta de línea de comandos SQLMetal no pueden asignar automáticamente un tipo SQL a una clase <xref:System.Enum> de CLR. Debe configurar explícitamente esta asignación personalizando un archivo DBML para que lo usen Object Relational Designer y SQLMetal. Para obtener más información sobre la asignación de tipos personalizados, vea [asignaciones de tipos personalizados de SQL-CLR](sql-clr-custom-type-mappings.md).  
  
 Dado que una columna SQL diseñada para la enumeración será del mismo tipo que otras columnas numéricas y de texto; Estas herramientas no reconocerán su intención y, de forma predeterminada, se asignarán tal y como se describe en las siguientes secciones de asignación [numérica](#NumericMapping) y de [asignación de texto y XML](#TextMapping) . Para obtener más información sobre cómo generar código con el archivo DBML, vea [generación de código en LINQ to SQL](code-generation-in-linq-to-sql.md).  
  
 El método <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> crea una columna de SQL de tipo numérico para asignar un tipo <xref:System.Enum?displayProperty=nameWithType> de CLR.  
  
<a name="NumericMapping"></a>
## <a name="numeric-mapping"></a>Asignación numérica  
 LINQ to SQL permite asignar muchos tipos numéricos de CLR y SQL Server. En la tabla siguiente se muestran los tipos de CLR que Object Relational Designer y SQLMetal seleccionan al crear un modelo de objetos o un archivo de asignación externo de acuerdo con la base de datos.  
  
|Tipo de datos de SQL Server|Asignación de tipos de CLR predeterminada usada por Object Relational Designer y SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`BIT`|<xref:System.Boolean?displayProperty=nameWithType>|  
|`TINYINT`|<xref:System.Int16?displayProperty=nameWithType>|  
|`INT`|<xref:System.Int32?displayProperty=nameWithType>|  
|`BIGINT`|<xref:System.Int64?displayProperty=nameWithType>|  
|`SMALLMONEY`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`MONEY`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`DECIMAL`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`NUMERIC`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`REAL/FLOAT(24)`|<xref:System.Single?displayProperty=nameWithType>|  
|`FLOAT/FLOAT(53)`|<xref:System.Double?displayProperty=nameWithType>|  
  
 En la tabla siguiente se muestran las asignaciones de tipos predeterminadas que el método <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> utiliza para definir qué tipo de columnas de SQL se deben crear para asignarlas a los tipos de CLR definidos en el modelo de objetos o en el archivo de asignación externo.  
  
|Tipo CLR|Tipo predeterminado de SQL Server utilizado por <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Boolean?displayProperty=nameWithType>|`BIT`|  
|<xref:System.Byte?displayProperty=nameWithType>|`TINYINT`|  
|<xref:System.Int16?displayProperty=nameWithType>|`SMALLINT`|  
|<xref:System.Int32?displayProperty=nameWithType>|`INT`|  
|<xref:System.Int64?displayProperty=nameWithType>|`BIGINT`|  
|<xref:System.SByte?displayProperty=nameWithType>|`SMALLINT`|  
|<xref:System.UInt16?displayProperty=nameWithType>|`INT`|  
|<xref:System.UInt32?displayProperty=nameWithType>|`BIGINT`|  
|<xref:System.UInt64?displayProperty=nameWithType>|`DECIMAL(20)`|  
|<xref:System.Decimal?displayProperty=nameWithType>|`DECIMAL(29,4)`|  
|<xref:System.Single?displayProperty=nameWithType>|`REAL`|  
|<xref:System.Double?displayProperty=nameWithType>|`FLOAT`|  
  
 Hay muchas otras asignaciones de tipos numéricos entre las que puede elegir, pero algunas pueden tener como resultado excepciones de desbordamiento o de pérdida de datos mientras se trasladan a la base de datos o desde ella. Para obtener más información, vea la matriz de comportamiento de la [asignación de tipos en tiempo de ejecución](#BehaviorMatrix).  
  
### <a name="decimal-and-money-types"></a>Tipos Decimal y Money  
 La precisión predeterminada de SQL Server `DECIMAL` tipo (18 dígitos decimales a la izquierda y a la derecha del separador decimal) es mucho menor que la precisión del <xref:System.Decimal?displayProperty=nameWithType> tipo CLR con el que se empareja de forma predeterminada. Esto puede producir una pérdida de precisión cuando los datos se guardan en la base de datos. Sin embargo, puede ocurrir exactamente lo contrario si el tipo `DECIMAL` de SQL Server se configura con más de 29 dígitos de precisión. Cuando se ha configurado un tipo `DECIMAL` de SQL Server con mayor precisión que el tipo <xref:System.Decimal?displayProperty=nameWithType> de CLR, la pérdida de precisión se produce al recuperar los datos de la base de datos.  
  
 Los tipos `MONEY` y `SMALLMONEY` de SQL Server, que también están emparejados con el tipo <xref:System.Decimal?displayProperty=nameWithType> de CLR de forma predeterminada, tienen mucha menos precisión, por lo que pueden producirse excepciones de desbordamiento o de pérdida de datos al guardar los datos en la base de datos.  
  
<a name="TextMapping"></a>
## <a name="text-and-xml-mapping"></a>Asignación de texto y XML  
 También hay muchos tipos XML y basados en texto que se pueden asignar con LINQ to SQL. En la tabla siguiente se muestran los tipos de CLR que Object Relational Designer y SQLMetal seleccionan al crear un modelo de objetos o un archivo de asignación externo de acuerdo con la base de datos.  
  
|Tipo de datos de SQL Server|Asignación de tipos de CLR predeterminada usada por Object Relational Designer y SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`CHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`NCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`VARCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`NVARCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`TEXT`|<xref:System.String?displayProperty=nameWithType>|  
|`NTEXT`|<xref:System.String?displayProperty=nameWithType>|  
|`XML`|<xref:System.Xml.Linq.XElement?displayProperty=nameWithType>|  
  
 En la tabla siguiente se muestran las asignaciones de tipos predeterminadas que el método <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> utiliza para definir qué tipo de columnas de SQL se deben crear para asignarlas a los tipos de CLR definidos en el modelo de objetos o en el archivo de asignación externo.  
  
|Tipo CLR|Tipo predeterminado de SQL Server utilizado por <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Char?displayProperty=nameWithType>|`NCHAR(1)`|  
|<xref:System.String?displayProperty=nameWithType>|`NVARCHAR(4000)`|  
|<xref:System.Char?displayProperty=nameWithType>[]|`NVARCHAR(4000)`|  
|Tipo personalizado que implementa `Parse()` y `ToString()`|`NVARCHAR(MAX)`|  
  
 Hay muchas otras asignaciones de XML y basadas en texto entre las que puede elegir, pero algunas pueden tener como resultado excepciones de desbordamiento o de pérdida de datos mientras se trasladan a o desde la base de datos. Para obtener más información, vea la matriz de comportamiento de la [asignación de tipos en tiempo de ejecución](#BehaviorMatrix).  
  
### <a name="xml-types"></a>Tipos XML  
 El tipo de datos `XML` de SQL Server está disponible a partir de Microsoft SQL Server 2005. Puede asignar el tipo de datos `XML` de SQL Server a <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument> o <xref:System.String>. Si la columna almacena fragmentos XML que no se pueden leer en <xref:System.Xml.Linq.XElement>, dicha columna debe asignarse a <xref:System.String> para evitar errores en tiempo de ejecución. Entre los fragmentos XML que se deben asignar a <xref:System.String> se incluyen los siguientes:  
  
- Una secuencia de elementos XML  
  
- Atributos  
  
- Identificadores públicos (PI)  
  
- Comentarios  
  
 Aunque puede asignar <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XDocument> SQL Server tal y como se muestra en la matriz de comportamiento de la [asignación de tipos en tiempo de ejecución](#BehaviorMatrix), el <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> método no tiene ninguna asignación de tipo SQL Server predeterminada para estos tipos.  
  
### <a name="custom-types"></a>Tipos personalizados  
 Si una clase implementa `Parse()` y `ToString()` , puede asignar el objeto a cualquier tipo de texto de SQL ( `CHAR` , `NCHAR` , `VARCHAR` , `NVARCHAR` , `TEXT` , `NTEXT` , `XML` ). El objeto se almacena en la base de datos enviando el valor devuelto por `ToString()` a la columna de base de datos asignada. El objeto se reconstruye invocando a `Parse()` en la cadena devuelta por la base de datos.  
  
> [!NOTE]
> LINQ to SQL no admite la serialización mediante <xref:System.Xml.Serialization.IXmlSerializable?displayProperty=nameWithType>.  
  
<a name="DateMapping"></a>
## <a name="date-and-time-mapping"></a>Asignación de fecha y hora  
 Con LINQ to SQL, se pueden asignar muchos tipos de fecha y hora de SQL Server. En la tabla siguiente se muestran los tipos de CLR que Object Relational Designer y SQLMetal seleccionan al crear un modelo de objetos o un archivo de asignación externo de acuerdo con la base de datos.  
  
|Tipo de datos de SQL Server|Asignación de tipos de CLR predeterminada usada por Object Relational Designer y SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`SMALLDATETIME`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIME`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIME2`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIMEOFFSET`|<xref:System.DateTimeOffset?displayProperty=nameWithType>|  
|`DATE`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`TIME`|<xref:System.TimeSpan?displayProperty=nameWithType>|  
  
 En la tabla siguiente se muestran las asignaciones de tipos predeterminadas que el método <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> utiliza para definir qué tipo de columnas de SQL se deben crear para asignarlas a los tipos de CLR definidos en el modelo de objetos o en el archivo de asignación externo.  
  
|Tipo CLR|Tipo predeterminado de SQL Server utilizado por <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.DateTime?displayProperty=nameWithType>|`DATETIME`|  
|<xref:System.DateTimeOffset?displayProperty=nameWithType>|`DATETIMEOFFSET`|  
|<xref:System.TimeSpan?displayProperty=nameWithType>|`TIME`|  
  
 Hay muchas otras asignaciones de fecha y hora entre las que puede elegir, pero algunas pueden tener como resultado excepciones de desbordamiento o de pérdida de datos mientras se trasladan a o desde la base de datos. Para obtener más información, vea la matriz de comportamiento de la [asignación de tipos en tiempo de ejecución](#BehaviorMatrix).  
  
> [!NOTE]
> Los tipos de SQL Server `DATETIME2`, `DATETIMEOFFSET`, `DATE` y `TIME` están disponibles a partir de Microsoft SQL Server 2008. LINQ to SQL admite la asignación a estos tipos nuevos a partir del Service Pack 1 de .NET Framework 3.5.  
  
### <a name="systemdatetime"></a>System.Datetime  
 El intervalo y la precisión del tipo <xref:System.DateTime?displayProperty=nameWithType> de CLR son mayores que el intervalo y la precisión del tipo `DATETIME` de SQL Server, que es la asignación de tipos predeterminada para el método <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>. Para evitar las excepciones relacionadas con los datos que están fuera del intervalo de `DATETIME`, utilice `DATETIME2`, que está disponible a partir de Microsoft SQL Server 2008. `DATETIME2` puede coincidir con el intervalo y la precisión de CLR <xref:System.DateTime?displayProperty=nameWithType> .  
  
 Las fechas de SQL Server no disponen del concepto de <xref:System.TimeZone>, que es una característica totalmente admitida en CLR. Los valores de <xref:System.TimeZone> se guardan tal como están en la base de datos sin conversión de <xref:System.TimeZone>, independientemente de la información de  <xref:System.DateTimeKind> original. Cuando los valores <xref:System.DateTime> se recuperan de la base de datos, su valor se carga tal cual en <xref:System.DateTime>, con un valor <xref:System.DateTimeKind> de <xref:System.DateTimeKind.Unspecified>. Para obtener más información sobre <xref:System.DateTime?displayProperty=nameWithType> los métodos admitidos, consulte [métodos System. DateTime](system-datetime-methods.md).  
  
### <a name="systemtimespan"></a>System.TimeSpan  
 Microsoft SQL Server 2008 y .NET Framework 3.5 SP1 permiten asignar el tipo <xref:System.TimeSpan?displayProperty=nameWithType> de CLR al tipo `TIME` de SQL Server. Sin embargo, existe una gran diferencia entre el intervalo que admite el tipo <xref:System.TimeSpan?displayProperty=nameWithType> de CLR y el que admite el tipo `TIME` de SQL Server. La asignación de valores menores que 0 horas o mayores que 23:59:59.9999999 horas al tipo `TIME` de SQL producirá excepciones de desbordamiento. Para obtener más información, vea [métodos System. TimeSpan](system-timespan-methods.md).  
  
 En Microsoft SQL Server 2000 y SQL Server 2005, no se pueden asignar campos de base de datos a <xref:System.TimeSpan>. Sin embargo, se admiten las operaciones en <xref:System.TimeSpan> porque se pueden devolver valores <xref:System.TimeSpan> a partir de la sustracción de <xref:System.DateTime> o se pueden incluir en una expresión como una variable literal o una variable enlazada.  
  
<a name="BinaryMapping"></a>
## <a name="binary-mapping"></a>Asignación binaria  
 Hay muchos tipos de SQL Server que se pueden asignar al tipo <xref:System.Data.Linq.Binary?displayProperty=nameWithType> de CLR. En la tabla siguiente se muestran los tipos de SQL Server que provocan que Object Relational Designer y SQLMetal definan un tipo <xref:System.Data.Linq.Binary?displayProperty=nameWithType> de CLR al crear un modelo de objetos o un archivo de asignación externo de acuerdo con la base de datos.  
  
|Tipo de datos de SQL Server|Asignación de tipos de CLR predeterminada usada por Object Relational Designer y SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`BINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(MAX)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(MAX)` con el `FILESTREAM` atributo|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`IMAGE`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`TIMESTAMP`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
  
 En la tabla siguiente se muestran las asignaciones de tipos predeterminadas que el método <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> utiliza para definir qué tipo de columnas de SQL se deben crear para asignarlas a los tipos de CLR definidos en el modelo de objetos o en el archivo de asignación externo.  
  
|Tipo CLR|Tipo predeterminado de SQL Server utilizado por <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
|<xref:System.Byte?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
|<xref:System.Runtime.Serialization.ISerializable?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
  
 Hay muchas otras asignaciones binarias entre las que puede elegir, pero algunas pueden tener como resultado excepciones de desbordamiento o de pérdida de datos mientras se trasladan a o desde la base de datos. Para obtener más información, vea la matriz de comportamiento de la [asignación de tipos en tiempo de ejecución](#BehaviorMatrix).  
  
### <a name="sql-server-filestream"></a>SQL Server FILESTREAM  
 El atributo `FILESTREAM` para las columnas `VARBINARY(MAX)` está disponible a partir de Microsoft SQL Server 2008; se le pueden asignar elementos con LINQ to SQL a partir del Service Pack 1 de .NET Framework 3.5.  
  
 Aunque puede asignar columnas `VARBINARY(MAX)` con el atributo `FILESTREAM` a objetos <xref:System.Data.Linq.Binary>, el método <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> no puede crear columnas automáticamente con el atributo `FILESTREAM`. Para obtener más información sobre `FILESTREAM` , vea [información general de FileStream](/previous-versions/sql/sql-server-2008-r2/bb933993(v=sql.105)).  
  
<a name="BinarySerialization"></a>
### <a name="binary-serialization"></a>Serialización binaria  
 Si una clase implementa la interfaz <xref:System.Runtime.Serialization.ISerializable>, se puede serializar un objeto en cualquier campo binario de SQL (`BINARY`, `VARBINARY`, `IMAGE`). El objeto se serializa o deserializa de acuerdo con la forma en que se haya implementado la interfaz <xref:System.Runtime.Serialization.ISerializable>. Para obtener más información, vea [serialización binaria](../../../../../standard/serialization/binary-serialization.md).
  
<a name="MiscMapping"></a>
## <a name="miscellaneous-mapping"></a>Asignaciones varias  
 En la tabla siguiente se muestran las asignaciones de tipos predeterminadas para varios tipos que aún no se han mencionado. En la tabla siguiente se muestran los tipos de CLR que Object Relational Designer y SQLMetal seleccionan al crear un modelo de objetos o un archivo de asignación externo de acuerdo con la base de datos.  
  
|Tipo de datos de SQL Server|Asignación de tipos de CLR predeterminada usada por Object Relational Designer y SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`UNIQUEIDENTIFIER`|<xref:System.Guid?displayProperty=nameWithType>|  
|`SQL_VARIANT`|<xref:System.Object?displayProperty=nameWithType>|  
  
 En la tabla siguiente se muestran las asignaciones de tipos predeterminadas que el método <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> utiliza para definir qué tipo de columnas de SQL se deben crear para asignarlas a los tipos de CLR definidos en el modelo de objetos o en el archivo de asignación externo.  
  
|Tipo CLR|Tipo predeterminado de SQL Server utilizado por <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Guid?displayProperty=nameWithType>|`UNIQUEIDENTIFIER`|  
|<xref:System.Object?displayProperty=nameWithType>|`SQL_VARIANT`|  
  
 LINQ to SQL no admite ninguna otra asignación de tipos para estos tipos varios.  Para obtener más información, vea la matriz de comportamiento de la [asignación de tipos en tiempo de ejecución](#BehaviorMatrix).  
  
## <a name="see-also"></a>Vea también

- [Asignación basada en atributos](attribute-based-mapping.md)
- [Asignación externa](external-mapping.md)
- [Tipos de datos y funciones](data-types-and-functions.md)
- [Desajustes de tipos entre SQL y CLR](sql-clr-type-mismatches.md)

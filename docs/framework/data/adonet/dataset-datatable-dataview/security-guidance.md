---
title: Guía de seguridad de DataSet y DataTable
ms.date: 07/14/2020
dev_langs:
- csharp
ms.openlocfilehash: c6b32afeadccc3fd22d6611d282840233280440f
ms.sourcegitcommit: e7748001b1cee80ced691d8a76ca814c0b02dd9b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86382472"
---
# <a name="dataset-and-datatable-security-guidance"></a>Guía de seguridad de DataSet y DataTable

Este artículo se aplica a:

* .NET Framework (todas las versiones)
* .NET Core y versiones posteriores
* .NET 5,0 y versiones posteriores

Los tipos [DataSet](/dotnet/api/system.data.dataset) y [DataTable](/dotnet/api/system.data.datatable) son componentes de .net heredados que permiten representar conjuntos de datos como objetos administrados. Estos componentes se introdujeron en .NET 1,0 como parte de la [infraestructura de ADO.net](/dotnet/framework/data/adonet/dataset-datatable-dataview/)original. Su objetivo era proporcionar una vista administrada a través de un conjunto de datos relacional, extraabstraendo si el origen subyacente de los datos era XML, SQL u otra tecnología.

Para obtener más información sobre ADO.NET, incluidos los paradigmas más modernos de la vista de datos, vea [la documentación de ADO.net](/dotnet/framework/data/adonet/).

## <a name="default-restrictions-when-deserializing-a-dataset-or-datatable-from-xml"></a>Restricciones predeterminadas al deserializar un DataSet o DataTable desde XML

En todas las versiones compatibles de .NET Framework, .NET Core y .NET, `DataSet` y `DataTable` se aplican las restricciones siguientes a los tipos de objetos que pueden estar presentes en los datos deserializados. De forma predeterminada, esta lista está restringida a:

* Tipos primitivos y equivalentes primitivos:,,,,,,,,,,,,,,,,,,, `bool` `char` `sbyte` `byte` `short` `ushort` `int` `uint` `long` `ulong` `float` `double` `decimal` `DateTime` `DateTimeOffset` `TimeSpan` `string` `Guid` `SqlBinary` `SqlBoolean` , `SqlByte` , `SqlBytes` ,,,, `SqlChars` , `SqlDateTime` `SqlDecimal` `SqlDouble` `SqlGuid` `SqlInt16` `SqlInt32` `SqlInt64` `SqlMoney` `SqlSingle` `SqlString` ,,,,, y.
* No primitivos usados comúnmente: `Type` , `Uri` y `BigInteger` .
* Tipos _System. Drawing_ usados comúnmente: `Color` , `Point` , `PointF` , `Rectangle` , `RectangleF` , `Size` y `SizeF` .
* `Enum`distintos.
* Matrices y listas de los tipos anteriores.

Si los datos XML entrantes contienen un objeto cuyo tipo no está en esta lista:

* Se inicia una excepción.
* Se produce un error en la operación de deserialización.

Al cargar XML en una `DataSet` instancia de o existente `DataTable` , también se tienen en cuenta las definiciones de columna existentes. Si la tabla ya contiene una definición de columna de un tipo personalizado, ese tipo se agrega temporalmente a la lista de permitidos mientras dure la operación de deserialización de XML.

```cs
XmlReader xmlReader = GetXmlReader();

// Assume the XML blob contains data for type MyCustomClass.
// The following call to ReadXml fails because MyCustomClass isn't in the allowed types list.

DataTable table = new DataTable("MyDataTable");
table.ReadXml(xmlReader);

// However, the following call to ReadXml succeeds, since the DataTable instance
// already defines a column of type MyCustomClass.

DataTable table = new DataTable("MyDataTable");
table.Columns.Add("MyColumn", typeof(MyCustomClass));
table.ReadXml(xmlReader); // this call will succeed
```

Las restricciones de tipo de objeto también se aplican cuando `XmlSerializer` se usa para deserializar una instancia de `DataSet` o `DataTable` . Sin embargo, es posible que no se apliquen al utilizar `BinaryFormatter` para deserializar una instancia de `DataSet` o `DataTable` .

Las restricciones de tipo de objeto no se aplican cuando `DataAdapter.Fill` se usa, como cuando una `DataTable` instancia se rellena directamente desde una base de datos sin usar las API de deserialización XML.

### <a name="extend-the-list-of-allowed-types"></a>Ampliar la lista de tipos permitidos

Una aplicación puede extender la lista de tipos permitidos para incluir tipos personalizados además de los tipos integrados enumerados anteriormente. Si se extiende la lista de tipos permitidos, el cambio afecta a _todas_ las `DataSet` instancias de y dentro de `DataTable` la aplicación. Los tipos no se pueden quitar de la lista de tipos permitidos integrados.

#### <a name="extend-through-configuration-net-framework-40---48"></a>Extender a través de la configuración (.NET Framework 4,0-4,8)

_App.config_ se puede usar para ampliar la lista de tipos permitidos. Para ampliar la lista de tipos permitidos:

* Use el `<configSections>` elemento para agregar una referencia a la sección de configuración _System. Data_ .
* `<system.data.dataset.serialization>` / `<allowedTypes>` Se usa para especificar tipos adicionales.

Cada `<add>` elemento debe especificar un solo tipo usando su nombre de tipo calificado con el ensamblado. Para agregar tipos adicionales a la lista de tipos permitidos, use varios `<add>` elementos.

En el ejemplo siguiente se muestra cómo extender la lista de tipos permitidos agregando el tipo personalizado `Fabrikam.CustomType` .

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add type="assembly qualified type name" /> -->
      <add type="Fabrikam.CustomType, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
      <!-- additional <add /> elements as needed -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

Para recuperar el nombre calificado del ensamblado de un tipo, use la propiedad [Type. AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) , como se muestra en el código siguiente.

```cs
string assemblyQualifiedName = typeof(Fabrikam.CustomType).AssemblyQualifiedName;
```

<a name="etc"></a>

#### <a name="extend-through-configuration-net-framework-20---35"></a>Extender a través de la configuración (.NET Framework 2,0-3,5)

Si su aplicación tiene como destino .NET Framework 2,0 o 3,5, todavía puede usar el mecanismo de _App.config_ anterior para ampliar la lista de tipos permitidos. Sin embargo, el `<configSections>` elemento tendrá un aspecto ligeramente diferente, tal como se muestra en el código siguiente:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- The below <sectionGroup> and <section> are specific to .NET Framework 2.0 and 3.5. -->
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add /> elements, as demonstrated in the .NET Framework 4.0 - 4.8 sample code above. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

#### <a name="extend-programmatically-net-framework-net-core-net-50"></a>Extender mediante programación (.NET Framework, .NET Core, .NET 5.0 +)

La lista de tipos permitidos también puede ampliarse mediante programación usando [AppDomain. SetData](/dotnet/api/system.appdomain.setdata) con el sistema de claves conocido _System. Data. DataSetDefaultAllowedTypes_, como se muestra en el código siguiente.

```cs
Type[] extraAllowedTypes = new Type[]
{
    typeof(Fabrikam.CustomType),
    typeof(Contoso.AdditionalCustomType)
};

AppDomain.CurrentDomain.SetData("System.Data.DataSetDefaultAllowedTypes", extraAllowedTypes);
```

Si se usa el mecanismo de extensión, el valor asociado a la clave _System. Data. DataSetDefaultAllowedTypes_ debe ser de tipo `Type[]` .

En .NET Framework, la lista de tipos permitidos se puede extender con _App.config_ y `AppDomain.SetData` . En este caso, `DataSet` y `DataTable` permitirá que un objeto se deserialice como parte de los datos si su tipo está presente en cualquiera de las listas.

### <a name="run-an-app-in-audit-mode-net-framework"></a>Ejecutar una aplicación en modo auditoría (.NET Framework)

En .NET Framework, `DataSet` y `DataTable` proporcionan una capacidad de modo de auditoría. Cuando está habilitado el modo `DataSet` de auditoría y `DataTable` compara los tipos de objetos entrantes con la lista de tipos permitidos. Sin embargo, si se muestra un objeto cuyo tipo no está permitido, **no** se produce una excepción. En su lugar, `DataSet` y `DataTable` notifican a las instancias adjuntas `TraceListener` que un tipo sospechoso está presente, lo que permite `TraceListener` que registre esta información. No se produce ninguna excepción y continúa la operación de deserialización.

> [!WARNING]
> La ejecución de una aplicación en "modo de auditoría" solo debe ser una medida temporal utilizada para las pruebas. Cuando el modo de auditoría está habilitado `DataSet` y `DataTable` no impone restricciones de tipo, lo que puede incluir un hueco de seguridad dentro de la aplicación. Para obtener más información, vea las secciones titulada [quitar todas las restricciones de tipo](#ratr) y [seguridad con respecto a la entrada que](#swr)no es de confianza.

El modo auditoría se puede habilitar a través de _App.config_:

* Vea la sección [extender a través](#etc) de la configuración de este documento para obtener información sobre el valor apropiado que se debe colocar para el `<configSections>` elemento.
* Use `<allowedTypes auditOnly="true">` para habilitar el modo de auditoría, tal como se muestra en el marcado siguiente.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- See the section of this document titled "Extending through configuration" for the appropriate
         <sectionGroup> and <section> elements to put here, depending on whether you're running .NET
         Framework 2.0 - 3.5 or 4.0 - 4.8. -->
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes auditOnly="true"> <!-- setting auditOnly="true" enables audit mode -->
      <!-- Optional <add /> elements as needed. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

Una vez habilitado el modo de auditoría, puede usar _App.config_ para conectar su preferido `TraceListener` al `DataSet` nombre integrado del `TraceSource.` origen de seguimiento integrado es _System. Data. DataSet_. En el ejemplo siguiente se muestra cómo escribir eventos de seguimiento en la consola _y_ en un archivo de registro en disco.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.diagnostics>
    <sources>
      <source name="System.Data.DataSet"
              switchType="System.Diagnostics.SourceSwitch"
              switchValue="Warning">
        <listeners>
          <!-- write to the console -->
          <add name="console"
               type="System.Diagnostics.ConsoleTraceListener" />
          <!-- *and* write to a log file on disk -->
          <add name="filelog"
               type="System.Diagnostics.TextWriterTraceListener"
               initializeData="c:\logs\mylog.txt" />
        </listeners>
      </source>
    </sources>
  </system.diagnostics>
</configuration>
```

Para obtener más información sobre `TraceSource` y `TraceListener` , vea el documento [Cómo: utilizar TraceSource y filtros con agentes de escucha de seguimiento](/dotnet/framework/debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners).

**Nota**: la ejecución de una aplicación en modo auditoría no está disponible en .net Core o en .net 5,0 y versiones posteriores.

<a name="ratr"></a>

### <a name="remove-all-type-restrictions"></a>Quitar todas las restricciones de tipo

Si una aplicación debe quitar todas las restricciones de limitación de tipos de `DataSet` y `DataTable` :

* Hay varias opciones para suprimir las restricciones de limitación de tipos.
* Las opciones disponibles dependen del marco de trabajo de destino de la aplicación.

> [!WARNING]
> Al quitar todas las restricciones de tipo, se puede introducir un agujero de seguridad dentro de la aplicación. Al utilizar este mecanismo, asegúrese de que la **not** aplicación no usa `DataSet` o `DataTable` para leer la entrada que no es de confianza. Para obtener más información, vea [CVE-2020-1147](https://portal.msrc.microsoft.com/security-guidance/advisory/CVE-2020-1147) y la sección siguiente titulada [seguridad con respecto a la entrada que no es de confianza](#swr).

#### <a name="through-appcontext-configuration-net-framework-46---48-net-core-21-and-later-net-50-and-later"></a>A través de la configuración de AppContext (.NET Framework 4,6-4,8, .NET Core 2,1 y versiones posteriores, .NET 5,0 y versiones posteriores)

El `AppContext` modificador, `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` , cuando se establece en, `true` quita todas las restricciones de limitación de tipos de `DataSet` y `DataTable` .

En .NET Framework, este modificador se puede habilitar a través de _App.config_, tal y como se muestra en la configuración siguiente:

```xml
<configuration>
   <runtime>
      <!-- Warning: setting the following switch can introduce a security problem. -->
      <AppContextSwitchOverrides value="Switch.System.Data.AllowArbitraryDataSetTypeInstantiation=true" />
   </runtime>
</configuration>
```

En ASP.NET, el `<AppContextSwitchOverrides>` elemento no está disponible. En su lugar, el conmutador se puede habilitar a través de _Web.config_, como se muestra en la configuración siguiente:

```xml
<configuration>
    <appSettings>
        <!-- Warning: setting the following switch can introduce a security problem. -->
        <add key="AppContext.SetSwitch:Switch.System.Data.AllowArbitraryDataSetTypeInstantiation" value="true" />
    </appSettings>
</configuration>
```

Para obtener más información, vea el [\<AppContextSwitchOverrides>](/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) elemento.

En .NET Core, .NET 5 y ASP.NET Core, este valor se controla mediante _runtimeconfig.jsen_, tal y como se muestra en el siguiente JSON:

```json
{
  "runtimeOptions": {
    "configProperties": {
      "Switch.System.Data.AllowArbitraryDataSetTypeInstantiation": true
    }
  }
}
```

Para obtener más información, vea ["opciones de configuración en tiempo de ejecución de .net Core"](/dotnet/core/run-time-config/).

`AllowArbitraryDataSetTypeInstantiation`también se puede establecer mediante programación a través de [AppContext. SetSwitch](/dotnet/api/system.appcontext.setswitch) en lugar de usar un archivo de configuración, como se muestra en el código siguiente:

```cs
// Warning: setting the following switch can introduce a security problem.
AppContext.SetSwitch("Switch.System.Data.AllowArbitraryDataSetTypeInstantiation", true);
```

 Si elige el enfoque de programación anterior, la llamada a `AppContext.SetSwitch` debe realizarse al principio de la aplicación.

#### <a name="through-the-machine-wide-registry-net-framework-20---48"></a>A través del registro en todo el equipo (.NET Framework 2,0-4,8)

Si `AppContext` no está disponible, las comprobaciones de limitación de tipos se pueden deshabilitar con el registro de Windows:

* Un administrador debe configurar el registro.
* El uso del registro es un cambio en todo el equipo y afectará a _todas las_ aplicaciones que se ejecutan en la máquina.

| Tipo  |  Value |
|---|---|
| **Clave del Registro** | `HKLM\SOFTWARE\Microsoft\.NETFramework\AppContext` |
| **Nombre del valor** | `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` |
| **Tipo de valor** | `REG_SZ` |
| **Datos de valor** | `true` |

En un sistema operativo de 64 bits, es necesario agregar este valor para la clave de 64 bits (mostrada anteriormente) y la clave de 32 bits. La clave de 32 bits se encuentra en `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext` .

Para obtener más información sobre el uso del registro para configurar `AppContext` , vea ["AppContext for Library Consumers"](/dotnet/api/system.appcontext#appcontext-for-library-consumers).

<a name="swr"></a>

## <a name="safety-with-regard-to-untrusted-input"></a>Seguridad con respecto a la entrada que no es de confianza

While `DataSet` y `DataTable` imponen limitaciones predeterminadas en los tipos que se pueden encontrar durante la deserialización de cargas XML __ `DataSet` y `DataTable` no suelen ser seguras cuando se rellenan con una entrada que no es de confianza.__ A continuación se muestra una lista no exhaustiva de formas en que `DataSet` una `DataTable` instancia de o podría leer una entrada que no es de confianza.

* Un `DataAdapter` hace referencia a una base de datos de y el `DataAdapter.Fill` método se utiliza para rellenar `DataSet` con el contenido de una consulta de base de datos.
* El `DataSet.ReadXml` `DataTable.ReadXml` método o se utiliza para leer un archivo XML que contiene información de columnas y filas.
* Una `DataSet` instancia de o `DataTable` se serializa como parte de un punto de conexión de WCF o servicios Web ASP.net (SOAP).
* Un serializador como `XmlSerializer` se utiliza para deserializar una `DataSet` `DataTable` instancia de o de una secuencia XML.
* Un serializador como `JsonConvert` se usa para deserializar una `DataSet` `DataTable` instancia de o de un flujo JSON. `JsonConvert`es un método de la conocida [Newtonsoft.Jsde terceros en](https://www.newtonsoft.com/json) la biblioteca.
* Un serializador como `BinaryFormatter` se usa para deserializar una `DataSet` `DataTable` instancia de o a partir de una secuencia de bytes sin formato.

En este documento se describen las consideraciones de seguridad para los escenarios anteriores.

## <a name="use-dataadapterfill-to-populate-a-dataset-from-an-untrusted-data-source"></a>Usar `DataAdapter.Fill` para rellenar a `DataSet` partir de un origen de datos que no es de confianza

`DataSet`Se puede rellenar una instancia de `DataAdapter` mediante [el `DataAdapter.Fill` método](/dotnet/api/system.data.common.dataadapter.fill), tal y como se muestra en el ejemplo siguiente.

```cs
// Assumes that connection is a valid SqlConnection object.  
string queryString =
  "SELECT CustomerID, CompanyName FROM dbo.Customers";  
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");
```

(El ejemplo de código anterior forma parte de un ejemplo más grande que se encuentra en [rellenar un conjunto de elementos a partir de un DataAdapter](/dotnet/framework/data/adonet/populating-a-dataset-from-a-dataadapter)).

> La mayoría de las aplicaciones pueden simplificar y suponer que su nivel de base de datos es de confianza. Sin embargo, si es el hábito del [modelado de amenazas](https://www.microsoft.com/securityengineering/sdl/threatmodeling) de las aplicaciones, puede considerar que el modelo de amenazas es un límite de confianza entre la aplicación (cliente) y el nivel de base de datos (servidor). El uso de la [autenticación mutua](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) o la [autenticación de AAD](/azure/azure-sql/database/authentication-aad-overview) entre el cliente y el servidor es una manera de ayudar a abordar los riesgos asociados a este. En el resto de esta sección se describe el posible resultado de que un cliente se conecte a un servidor que no es de confianza.

Las consecuencias de señalar un `DataAdapter` en un origen de datos que no es de confianza dependen de la implementación del `DataAdapter` propio.

### <a name="sqldataadapter"></a>SqlDataAdapter

En el caso del tipo integrado [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter), la referencia a un origen de datos que no es de confianza podría producir un ataque de denegación de servicio (dos). El ataque de DoS puede dar lugar a que la aplicación deje de responder o se bloquee. Si un atacante puede plantar un archivo DLL junto con la aplicación, es posible que también pueda lograr la ejecución de código local.

### <a name="other-dataadapter-types"></a>Otros tipos DataAdapter

`DataAdapter`Las implementaciones de terceros deben realizar sus propias evaluaciones sobre qué garantías de seguridad proporcionan en caso de que se produzcan entradas que no son de confianza. .NET no puede garantizar ninguna garantía de seguridad con respecto a estas implementaciones.

<a name="dsrdtr"></a>

## <a name="datasetreadxml-and-datatablereadxml"></a>DataSet. ReadXml y DataTable. ReadXml

Los `DataSet.ReadXml` `DataTable.ReadXml` métodos y no son seguros cuando se usan con una entrada que no es de confianza. Se recomienda encarecidamente que los consumidores consideren el uso de una de las alternativas que se describen más adelante en este documento.

Las implementaciones de `DataSet.ReadXml` y `DataTable.ReadXml` se crearon originalmente antes de que las vulnerabilidades de serialización fueran una categoría de amenazas bien entendida. Como resultado, el código no sigue los procedimientos recomendados de seguridad actuales. Estas API se pueden usar como vectores para que los atacantes realicen ataques de DoS en aplicaciones Web. Estos ataques pueden provocar que el servicio Web deje de responder o que se produzca una terminación inesperada del proceso. El marco de trabajo no proporciona mitigaciones para estas categorías de ataque y .NET considera este comportamiento "por diseño".

.NET ha publicado actualizaciones de seguridad para mitigar algunos problemas, como la divulgación de información o la ejecución remota de código en `DataSet.ReadXml` y `DataTable.ReadXml` . Es posible que las actualizaciones de seguridad de .NET no proporcionen protección completa contra estas categorías de amenaza. Los consumidores deben evaluar sus escenarios individuales y considerar su posible exposición a estos riesgos.

Los consumidores deben tener en cuenta que las actualizaciones de seguridad de estas API pueden afectar a la compatibilidad de aplicaciones en algunas situaciones. Además, existe la posibilidad de que se detecte una vulnerabilidad novedosa en estas API para la que .NET no puede publicar prácticamente una actualización de seguridad.

Se recomienda que los consumidores de estas API:

* Considere la posibilidad de usar una de las alternativas que se describen más adelante en este documento.
* Realizar evaluaciones de riesgos individuales en sus aplicaciones.

Es responsabilidad exclusiva del consumidor determinar si se deben utilizar estas API. Los consumidores deben evaluar los riesgos de seguridad, técnicos y legales, incluidos los requisitos normativos, que pueden acompañar al uso de estas API.

## <a name="dataset-and-datatable-via-aspnet-web-services-or-wcf"></a>DataSet y DataTable a través de los servicios Web de ASP.NET o WCF

Es posible aceptar una `DataSet` `DataTable` instancia de o en un servicio Web ASP.net (SOAP), como se muestra en el código siguiente:

```cs
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(DataTable dataTable)
    {
        /* Web method implementation. */
    }
}
```

Una variación de esto no es aceptar `DataSet` o `DataTable` directamente como parámetro, sino que se puede aceptar como parte del gráfico de objetos serializado SOAP general, tal y como se muestra en el código siguiente:

```cs
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(MyClass data)
    {
        /* Web method implementation. */
    }
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

O bien, mediante WCF en lugar de los servicios Web de ASP.NET:

```cs
using System.Data;
using System.ServiceModel;

[ServiceContract(Namespace = "http://contoso.com/")]
public interface IMyContract
{
    [OperationContract]
    string MyMethod(DataTable dataTable);
    [OperationContract]
    string MyOtherMethod(MyClass data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

En todos estos casos, el modelo de amenazas y las garantías de seguridad son los mismos que los de la [sección DataSet. ReadXml y DataTable. ReadXml](#dsrdtr).

## <a name="deserialize-a-dataset-or-datatable-via-xmlserializer"></a>Deserialización de un conjunto de DataSet o DataTable a través de XmlSerializer

Los desarrolladores pueden usar `XmlSerializer` para deserializar `DataSet` `DataTable` las instancias de y, tal y como se muestra en el código siguiente:

```cs
using System.Data;
using System.IO;
using System.Xml.Serialization;

public DataSet PerformDeserialization1(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(DataSet));
    return (DataSet)serializer.Deserialize(stream);
}

public MyClass PerformDeserialization2(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(MyClass));
    return (MyClass)serializer.Deserialize(stream);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

En estos casos, el modelo de amenazas y las garantías de seguridad son los mismos que los de la [sección DataSet. ReadXml y DataTable. ReadXml.](#dsrdtr)

## <a name="deserialize-a-dataset-or-datatable-via-jsonconvert"></a>Deserialización de un conjunto de DataSet o DataTable a través de JsonConvert

La popular biblioteca de Newtonsoft de terceros [JSON.net](https://www.newtonsoft.com/json) se puede usar para deserializar `DataSet` `DataTable` las instancias de y, tal y como se muestra en el código siguiente:

```cs
using System.Data;
using Newtonsoft.Json;

public DataSet PerformDeserialization1(string json) {
    return JsonConvert.DeserializeObect<DataSet>(data);
}

public MyClass PerformDeserialization2(string json) {
    return JsonConvert.DeserializeObect<MyClass>(data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

La deserialización de un `DataSet` `DataTable` objeto o de este modo desde un BLOB JSON que no es de confianza no es segura. Este patrón es vulnerable a ataques de denegación de servicio. Este tipo de ataque podría bloquear la aplicación o representar que no responde.

**Nota**: Microsoft no garantiza ni admite la implementación de bibliotecas de terceros como _Newtonsoft.Jsen_. Esta información se proporciona para la integridad y es precisa en el momento de redactar este documento.

## <a name="deserialize-a-dataset-or-datatable-via-binaryformatter"></a>Deserializar un conjunto de DataSet o DataTable a través de BinaryFormatter

Los desarrolladores nunca deben usar `BinaryFormatter` , `NetDataContractSerializer` , `SoapFormatter` o formateadores ***no seguros*** relacionados para deserializar una `DataSet` `DataTable` instancia de o de una carga que no sea de confianza:

* Esto es susceptible a un ataque de ejecución de código remoto completo.
* El uso de un personalizado `SerializationBinder` no es suficiente para evitar este tipo de ataque.

## <a name="safe-replacements"></a>Reemplazos seguros

En el caso de las aplicaciones que:

* Acepte `DataSet` o `DataTable` a través de un punto de conexión SOAP de. asmx o un extremo de WCF.
* Deserializa los datos que no son de confianza en una instancia de `DataSet` o `DataTable` .

Considere la posibilidad de reemplazar el modelo de objetos para utilizar [Entity Framework](/ef). Entity Framework:

* Es un marco de trabajo rico y moderno orientado a objetos que puede representar datos relacionales.
* Aporta [un amplio ecosistema](/ef/core/providers/) de proveedores de bases de datos para facilitar la creación de proyectos de consultas de base de datos a través de los modelos de objetos de Entity Framework.
* Ofrece protecciones integradas al deserializar datos de orígenes que no son de confianza.

En el caso de las aplicaciones que usan `.aspx` extremos SOAP, considere la posibilidad de cambiar esos puntos de conexión para usar [WCF](/dotnet/framework/wcf/). WCF es un sustituto más completo de `.asmx` servicios Web. Los extremos de WCF [se pueden exponer a través de SOAP](/dotnet/framework/wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients) para la compatibilidad con los autores de llamadas existentes.

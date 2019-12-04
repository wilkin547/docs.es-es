---
title: Actividades de acceso a bases de datos
ms.date: 03/30/2017
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
ms.openlocfilehash: eec368803eeacb2bab729bcd6d57cc7fc6107256
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74710858"
---
# <a name="database-access-activities"></a>Actividades de acceso a bases de datos

Las actividades de acceso a bases de datos permiten tener acceso a una base de datos dentro de un flujo de trabajo. Estas actividades permiten tener acceso a las bases de datos para recuperar o modificar información y usar [ADO.net](https://go.microsoft.com/fwlink/?LinkId=166081) para tener acceso a la base de datos.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a (página de descarga) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`

## <a name="database-activities"></a>Actividades de base de datos

En las siguientes secciones se detalla la lista de actividades incluidas en este ejemplo.

## <a name="dbupdate"></a>DbUpdate

Ejecuta una consulta SQL que genera una modificación en la base de datos (inserción, actualización, eliminación y otras modificaciones).

Esta clase realiza su trabajo de forma asincrónica (deriva de <xref:System.Activities.AsyncCodeActivity> y usa sus capacidades asincrónicas).

La información de conexión se puede configurar estableciendo un nombre invariable de proveedor (`ProviderName`) y la cadena de conexión (`ConnectionString`) o simplemente utilizando un nombre de configuración de cadena de conexión (`ConfigFileSectionName`) del archivo de configuración de la aplicación.

La consulta que se va a ejecutar se configura en su propiedad `Sql` y los parámetros se pasan a través de la colección `Parameters`.

Una vez ejecutado `DbUpdate`, el número de registros afectado se devuelve en la propiedad `AffectedRecords`.

```csharp
Public class DbUpdate: AsyncCodeActivity
{
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [DependsOn("Parameters")]
    public OutArgument<int> AffectedRecords { get; set; }
}
```

|Argument|Descripción|
|-|-|
|ProviderName|Nombre invariable de proveedor de ADO.NET. Si se establece este argumento, también se debe establecer `ConnectionString`.|
|ConnectionString|Cadena de conexión para conectar a la base de datos. Si se establece este argumento, también se debe establecer `ProviderName`.|
|ConfigName|Nombre de la sección de archivo de configuración donde se almacena la información de conexión. Cuando se establece este argumento no se requieren `ProviderName` ni `ConnectionString`.|
|CommandType|Tipo de <xref:System.Data.Common.DbCommand> que se va a ejecutar.|
|Sql|El comando SQL que se va a ejecutar.|
|Parameters|Colección de los parámetros de la consulta SQL.|
|AffectedRecords|Número de registros afectado por la última operación.|

## <a name="dbqueryscalar"></a>DbQueryScalar

Ejecuta una consulta que recupera un único valor de la base de datos.

Esta clase realiza su trabajo de forma asincrónica (deriva de <xref:System.Activities.AsyncCodeActivity%601> y usa sus capacidades asincrónicas).

La información de conexión se puede configurar estableciendo un nombre invariable de proveedor (`ProviderName`) y la cadena de conexión (`ConnectionString`) o simplemente utilizando un nombre de configuración de cadena de conexión (`ConfigFileSectionName`) del archivo de configuración de la aplicación.

La consulta que se va a ejecutar se configura en su propiedad `Sql` y los parámetros se pasan a través de la colección `Parameters`.

Una vez ejecutada la `DbQueryScalar`, el valor escalar se devuelve en el `Result out` argumento (de tipo `TResult`, que se define en la clase base <xref:System.Activities.AsyncCodeActivity%601>).

```csharp
public class DbQueryScalar<TResult> : AsyncCodeActivity<TResult>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|Argument|Descripción|
|-|-|
|ProviderName|Nombre invariable de proveedor de ADO.NET. Si se establece este argumento, también se debe establecer `ConnectionString`.|
|ConnectionString|Cadena de conexión para conectar a la base de datos. Si se establece este argumento, también se debe establecer `ProviderName`.|
|ConfigName|Nombre de la sección de archivo de configuración donde se almacena la información de conexión. Cuando se establece este argumento no se requieren `ProviderName` ni `ConnectionString`.|
|CommandType|Tipo de <xref:System.Data.Common.DbCommand> que se va a ejecutar.|
|Sql|El comando SQL que se va a ejecutar.|
|Parameters|Colección de los parámetros de la consulta SQL.|
|Resultado|Valor escalar que se obtiene una vez ejecutada la consulta. Este argumento es de tipo `TResult`.|

## <a name="dbquery"></a>DbQuery

Ejecuta una consulta que recupera una lista de objetos. Una vez ejecutada la consulta, se ejecuta una función de asignación (puede ser <xref:System.Func%601><`DbDataReader`, `TResult`> o <xref:System.Activities.ActivityFunc%601><`DbDataReader``TResult`>). Esta función de asignación obtiene un registro de `DbDataReader` y lo asigna al objeto que se va a devolver.

La información de conexión se puede configurar estableciendo un nombre invariable de proveedor (`ProviderName`) y la cadena de conexión (`ConnectionString`) o simplemente utilizando un nombre de configuración de cadena de conexión (`ConfigFileSectionName`) del archivo de configuración de la aplicación.

La consulta que se va a ejecutar se configura en su propiedad `Sql` y los parámetros se pasan a través de la colección `Parameters`.

Los resultados de la consulta SQL se recuperan utilizando `DbDataReader`. La actividad recorre en iteración `DbDataReader` y asigna las filas de `DbDataReader` a una instancia de `TResult`. El usuario de `DbQuery` tiene que proporcionar el código de asignación y esto puede realizarse de dos maneras: mediante un <xref:System.Func%601><`DbDataReader`, `TResult`> o un <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>. En el primer caso, la asignación se realiza en un pulso único de ejecución. Por tanto, es más rápida, pero esto no se puede serializar en XAML. En el último caso, la asignación se realiza en varios pulsos. Por tanto, puede ser más lenta pero se serializar en XAML y crear mediante declaración (cualquier actividad existente puede participar en la asignación).

```csharp
public class DbQuery<TResult> : AsyncCodeActivity<IList<TResult>> where TResult : class
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [OverloadGroup("DirectMapping")]
    [DefaultValue(null)]
    public Func<DbDataReader, TResult> Mapper { get; set; }

    [OverloadGroup("MultiplePulseMapping")]
    [DefaultValue(null)]
    public ActivityFunc<DbDataReader, TResult> MapperFunc { get; set; }
}
```

|Argument|Descripción|
|-|-|
|ProviderName|Nombre invariable de proveedor de ADO.NET. Si se establece este argumento, también se debe establecer `ConnectionString`.|
|ConnectionString|Cadena de conexión para conectar a la base de datos. Si se establece este argumento, también se debe establecer `ProviderName`.|
|ConfigName|Nombre de la sección de archivo de configuración donde se almacena la información de conexión. Cuando se establece este argumento no se requieren `ProviderName` ni `ConnectionString`.|
|CommandType|Tipo de <xref:System.Data.Common.DbCommand> que se va a ejecutar.|
|Sql|El comando SQL que se va a ejecutar.|
|Parameters|Colección de los parámetros de la consulta SQL.|
|Mapper|Función de asignación (<xref:System.Func%601><`DbDataReader`, `TResult`>) que toma un registro en el `DataReader` obtenido como resultado de la ejecución de la consulta y devuelve una instancia de un objeto de tipo `TResult` que se va a agregar a la colección de `Result`.<br /><br /> En este caso, la asignación se realiza mediante un único pulso de ejecución, pero no se puede crear mediante declaración utilizando el diseñador.|
|MapperFunc|Función de asignación (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) que toma un registro en el `DataReader` obtenido como resultado de la ejecución de la consulta y devuelve una instancia de un objeto de tipo `TResult` que se va a agregar a la colección de `Result`.<br /><br /> En este caso, la asignación se realiza en varios pulsos de ejecución. Esta función se puede serializar en XAML y crear mediante declaración (cualquier actividad existente puede participar en la asignación).|
|Resultado|Lista de objetos obtenidos como resultado de ejecutar la consulta y ejecutar la función de asignación para cada registro de `DataReader`.|

## <a name="dbquerydataset"></a>DbQueryDataSet

Ejecuta una consulta que devuelve una clase <xref:System.Data.DataSet>. Esta clase realiza su trabajo de forma asincrónica. Deriva de <xref:System.Activities.AsyncCodeActivity><`TResult`> y utiliza sus capacidades asincrónicas.

La información de conexión se puede configurar estableciendo un nombre invariable de proveedor (`ProviderName`) y la cadena de conexión (`ConnectionString`) o simplemente utilizando un nombre de configuración de cadena de conexión (`ConfigFileSectionName`) del archivo de configuración de la aplicación.

La consulta que se va a ejecutar se configura en su propiedad `Sql` y los parámetros se pasan a través de la colección `Parameters`.

Una vez ejecutada la `DbQueryDataSet`, se devuelve `DataSet` en el argumento `Result out` (de tipo `TResult`, que se define en la <xref:System.Activities.AsyncCodeActivity%601>de la clase base).

```csharp
public class DbQueryDataSet : AsyncCodeActivity<DataSet>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|Argument|Descripción|
|-|-|
|ProviderName|Nombre invariable de proveedor de ADO.NET. Si se establece este argumento, también se debe establecer `ConnectionString`.|
|ConnectionString|Cadena de conexión para conectar a la base de datos. Si se establece este argumento, también se debe establecer `ProviderName`.|
|ConfigName|Nombre de la sección de archivo de configuración donde se almacena la información de conexión. Cuando se establece este argumento no se requieren `ProviderName` ni `ConnectionString`.|
|CommandType|Tipo de <xref:System.Data.Common.DbCommand> que se va a ejecutar.|
|Sql|El comando SQL que se va a ejecutar.|
|Parameters|Colección de los parámetros de la consulta SQL.|
|Resultado|<xref:System.Data.DataSet> que se obtiene una vez ejecutada la consulta.|

## <a name="configuring-connection-information"></a>Configurar información de conexión

Todas las actividades de base de datos comparten los mismos parámetros de configuración. Se pueden configurar de dos maneras:

- `ConnectionString + InvariantName`: establezca el nombre invariable de proveedor de ADO.NET y la cadena de conexión.

  ```csharp
  Activity dbSelectCount = new DbQueryScalar<DateTime>()
  {
      ProviderName = "System.Data.SqlClient",
      ConnectionString = @"Data Source=.\SQLExpress;
                            Initial Catalog=DbActivitiesSample;
                            Integrated Security=True",
      Sql = "SELECT GetDate()"
  };
  ```

- `ConfigName`: establezca el nombre de la sección de configuración que contiene la información de conexión.

  ```xml
  <connectionStrings>
      <add name="DbActivitiesSample"
            providerName="System.Data.SqlClient"
            connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>
    </connectionStrings>
  ```

- En la actividad:

  ```csharp
  Activity dbSelectCount = new DbQueryScalar<int>()
  {
      ConfigName = "DbActivitiesSample",
      Sql = "SELECT COUNT(*) FROM Roles"
  };
  ```

## <a name="running-this-sample"></a>Ejecutar este ejemplo

### <a name="setup-instructions"></a>Instrucciones de instalación

En este ejemplo se utiliza una base de datos. Con el ejemplo se proporciona un script de instalación y carga (Setup.cmd). Debe ejecutar ese archivo mediante el símbolo del sistema.

El script Setup.cmd invoca el archivo de script CreateDb.sql, que contiene comandos SQL con los que realiza lo siguiente:

- Crea una base de datos llamada DbActivitiesSample.

- Crea la tabla Roles.

- Crea la tabla Employees.

- Inserta tres registros en la tabla Roles.

- Inserta doce registros en la tabla Employees.

##### <a name="to-run-setupcmd"></a>Para ejecutar Setup.cmd

1. Abra un símbolo del sistema.

2. Vaya a la carpeta de ejemplo DbActivities.

3. Escriba "Setup. cmd" y presione Entrar.

    > [!NOTE]
    > Setup.cmd intenta instalar el ejemplo en la instancia de SqlExpress del equipo local. Si desea instalarlo en otra instancia de SQL Server, modifique Setup.cmd con el nombre de la nueva instancia.

##### <a name="to-uninstall-the-sample-database"></a>Para desinstalar la base de datos de ejemplo

1. Ejecute Cleanup.cmd desde la carpeta de ejemplo en un símbolo del sistema.

##### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo

1. Abra la solución en Visual Studio 2010

2. Para compilar la solución, presione Ctrl+MAYÚS+B.

3. Para ejecutar el ejemplo sin depurar, presione CTRL+F5.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`

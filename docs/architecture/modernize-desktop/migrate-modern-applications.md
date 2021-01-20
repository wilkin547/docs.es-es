---
title: Migración de aplicaciones de escritorio modernas
description: Todo lo que necesita saber sobre el proceso de migración de aplicaciones de escritorio modernas.
ms.date: 01/19/2021
ms.openlocfilehash: b5bea6e601dc040adfd8ed410320a3416cb3372e
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615768"
---
# <a name="migrating-modern-desktop-applications"></a>Migración de aplicaciones de escritorio modernas

En este capítulo, estamos explorando los problemas y desafíos más comunes a los que puede enfrentarse al migrar una aplicación existente de .NET Framework a .NET.

Una aplicación de escritorio compleja no funciona de forma aislada y necesita algún tipo de interacción con subsistemas que pueden residir en el equipo local o en un servidor remoto. Probablemente necesitará algún tipo de base de datos para conectarse como almacenamiento de persistencia, ya sea de forma local o remota. Con el aumento de las arquitecturas orientadas a Internet y a los servicios, es habitual que la aplicación esté conectada a algún tipo de servicio que resida en un servidor remoto o en la nube. Es posible que necesite tener acceso al sistema de archivos de la máquina para implementar alguna funcionalidad. Como alternativa, quizás esté usando una parte de la funcionalidad que reside dentro de un objeto COM fuera de la aplicación, que es un escenario común si, por ejemplo, está integrando ensamblados de Office en la aplicación.

Además, hay diferencias en la superficie de API expuesta por .NET Framework y .NET, y algunas de las características que están disponibles en .NET Framework no están disponibles en .NET. Por lo tanto, es importante conocer y tener en cuenta al planear una migración.

## <a name="configuration-files"></a>Archivos de configuración

Los archivos de configuración ofrecen la posibilidad de almacenar conjuntos de propiedades que se leen en tiempo de ejecución y que afectan al comportamiento de nuestras aplicaciones, como dónde buscar una base de datos o cuántas veces ejecutar un bucle. La belleza de esta técnica es que puede modificar algunos aspectos de la aplicación sin necesidad de recodificar y volver a compilar. Esto resulta útil cuando, por ejemplo, el mismo código de la aplicación se ejecuta en un entorno de desarrollo con un determinado conjunto de valores de configuración y en producción con uno diferente.

### <a name="configuration-on-net-framework"></a>Configuración en .NET Framework

Si tiene una aplicación de escritorio .NET Framework en funcionamiento, lo más probable es que tenga un archivo *app.config* al que se tiene acceso a través de la <xref:System.Configuration.AppSettingsSection> clase del `System.Configuration` espacio de nombres.

Dentro de la infraestructura de .NET Framework, existe una jerarquía de archivos de configuración que heredan propiedades de sus elementos primarios. Puede encontrar un archivo *machine.config* que defina muchas propiedades y secciones de configuración que se pueden usar o reemplazar en cualquier archivo de configuración descendiente.

### <a name="configuration-on-net"></a>Configuración en .NET

En el mundo de .NET, no hay ningún archivo de *machine.config* . Además, aunque puede seguir usando el antiguo <xref:System.Configuration> espacio de nombres con el uso de, puede considerar la posibilidad de cambiar al moderno <xref:Microsoft.Extensions.Configuration> , que ofrece un buen número de mejoras.

La API de configuración de admite el concepto de proveedor de configuración, que define el origen de datos que se va a usar para cargar la configuración. Hay diferentes tipos de proveedores integrados, como:

- Objetos de .NET en memoria
- Archivos INI
- Archivos JSON
- Archivos XML
- Argumentos de la línea de comandos
- Variables de entorno
- Almacén de usuario cifrado

 También puede crear el suyo propio.

La nueva configuración permite una lista de pares nombre-valor que se pueden agrupar en una jerarquía de varios niveles. Cualquier valor almacenado se asigna a una cadena y existe compatibilidad de enlace integrada que permite deserializar la configuración en un objeto de objeto CLR antiguo sin formato (POCO).

El <xref:Microsoft.Extensions.Configuration.ConfigurationBuilder> objeto permite agregar tantos proveedores de configuración como sea necesario para la aplicación, con una regla de prioridad para resolver las preferencias. Por lo tanto, el último proveedor que agregue en el código invalidará los demás. Esta es una excelente característica para administrar distintos entornos de ejecución, ya que puede definir diferentes configuraciones para entornos de desarrollo, pruebas y producción, y administrarlos en una sola función dentro del código.

### <a name="migrating-configuration-files"></a>Migrar archivos de configuración

Puede seguir usando el archivo XML de app.config existente. Sin embargo, podría tomar esta oportunidad de migrar la configuración para beneficiarse de las distintas mejoras realizadas en .NET.

Para migrar desde un *app.config* de estilo antiguo a un nuevo archivo de configuración, debe elegir entre un formato XML y un formato JSON.

Si elige XML, la conversión es sencilla. Dado que el contenido es el mismo, solo tiene que guardar el archivo de *app.config* con XML como tipo. A continuación, cambie el código que hace referencia a AppSettings para usar la `ConfigurationBuilder` clase. Este cambio debe ser sencillo.

Si desea usar un formato JSON y no desea migrar a mano, hay una herramienta denominada [dotnet-config2json](https://www.nuget.org/packages/dotnet-config2json/) disponible en .net que puede convertir un archivo *app.config* en un archivo de configuración JSON.

También puede que surjan algunos problemas al usar las secciones de configuración que se definieron en el archivo de *machine.config* . Por ejemplo, considere la siguiente configuración:

```xml
<configuration>
    <system.diagnostics>
        <switches>
            <add name="General" value="4" />
        </switches>
        <trace autoflush="true" indentsize="2">
            <listeners>
                <add name="myListener"
                     type="System.Diagnostics.TextWriterTraceListener,
                           System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
                     initializeData="MyListener.log"
                     traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />
            </listeners>
        </trace>
    </system.diagnostics>
</configuration>
```

Si toma esta configuración en un .NET, obtendrá una excepción:

> Sección de configuración no reconocida System. Diagnostics

Esta excepción se produce porque esa sección y el ensamblado responsable de administrar esa sección se definieron en el archivo de *machine.config* , que ahora no existe.

Para solucionar el problema fácilmente, puede copiar la definición de la sección del *machine.config* anterior en el nuevo archivo de configuración:

```xml
<configSections>
    <section name="system.diagnostics"
             type="System.Diagnostics.SystemDiagnosticsSection,
                   System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
</configSections>
```

## <a name="accessing-databases"></a>Obtener acceso a bases de datos

Casi todas las aplicaciones de escritorio necesitan algún tipo de base de datos. En el caso de Desktop, es habitual encontrar arquitecturas cliente-servidor con una conexión directa entre la aplicación de escritorio y el motor de base de datos. Estas bases de datos pueden ser locales o remotas en función de la necesidad de compartir información entre distintos usuarios.

Desde la perspectiva del código, ha habido muchas tecnologías y marcos para ofrecer al desarrollador la posibilidad de conectar, consultar y actualizar una base de datos.

Los ejemplos más comunes de base de datos que puede encontrar al hablar sobre la aplicación de escritorio de Windows son Microsoft Access y Microsoft SQL Server. Si tiene más de 20 años de experiencia en programación para el escritorio, los nombres como ODBC, OLEDB, RDO, ADO, ADO.NET, LINQ y Entity Framework resultarán familiares.

### <a name="odbc"></a>ODBC

Puede seguir usando ODBC en .NET, ya que Microsoft proporciona la `System.Data.Odbc` biblioteca compatible con .NET Standard 2,0.

### <a name="ole-db"></a>OLE DB

[OLE DB](/previous-versions/windows/desktop/ms722784(v=vs.85)) ha sido una excelente manera de tener acceso a varios orígenes de datos de una manera uniforme. Pero se basaba en COM, que es una tecnología solo de Windows y, como tal, no era la mejor opción para una tecnología multiplataforma como .NET. Tampoco se admite en las versiones 2014 y posteriores de SQL Server. Por estos motivos, no admitirá OLE DB .NET.

### <a name="adonet"></a>ADO.NET

Todavía puede usar ADO.NET desde el código de escritorio existente en .NET. Solo tiene que actualizar algunos paquetes de NuGet.

### <a name="ef-core-vs-ef6"></a>EF Core frente a EF6

Hay dos versiones admitidas actualmente de Entity Framework (EF), Entity Framework 6 (EF6) y EF Core.

La última tecnología publicada como parte del mundo .NET Framework es Entity Framework, con 6,4 como última versión. Con el lanzamiento de .NET Core, Microsoft también lanzó una nueva pila de acceso a datos basada en Entity Framework y llamada Entity Framework Core.

Puede usar EF 6,4 y EF Core de .NET Framework y .NET. Por lo tanto, ¿cuáles son los controladores de decisión que le ayudarán a decidir entre los dos?

EF 6,3 es la primera versión de EF6 que se puede ejecutar en .NET y trabajar entre plataformas. De hecho, el objetivo principal de esta versión era facilitar la migración de las aplicaciones existentes que usan EF6 a .NET.

EF Core se diseñó para proporcionar una experiencia de desarrollo similar a EF6. La mayoría de las API de nivel superior siguen igual, por lo que EF Core resultará familiar para los desarrolladores que hayan usado EF6.

Aunque es compatible, hay diferencias en la implementación que debe comprobar antes de tomar una decisión.
Para obtener más información, vea [Compare EF Core & EF6](/ef/efcore-and-ef6/).

La recomendación es usar EF Core si:

* La aplicación necesita las capacidades de .NET.
* EF Core es compatible con todas las características que necesita la aplicación.

Considere el uso de EF6 si se cumplen las dos condiciones siguientes:

* La aplicación se ejecutará en Windows y .NET Framework 4,0 o posterior.
* EF6 es compatible con todas las características que necesita la aplicación.

### <a name="relational-databases"></a>Bases de datos relacionales

#### <a name="sql-server"></a>SQL Server

SQL Server ha sido una de las bases de datos que se han elegido si el desarrollo está en el escritorio hace algunos años. Con el uso de <xref:System.Data.SqlClient> en .NET Framework, puede tener acceso a las versiones de SQL Server, que encapsula los protocolos específicos de la base de datos.

En .NET, puede encontrar una nueva `SqlClient` clase, totalmente compatible con la existente en el .NET Framework, pero que se encuentra en la <xref:Microsoft.Data.SqlClient> biblioteca. Solo tiene que agregar una referencia al paquete de NuGet [Microsoft. Data. SqlClient](https://www.nuget.org/packages/Microsoft.Data.SqlClient/) y cambiar el nombre de los espacios de nombres y todo debería funcionar según lo esperado.

#### <a name="microsoft-access"></a>Microsoft Access

Microsoft Access se ha usado durante años cuando no era necesario el SQL Server sofisticado y más escalable. Todavía puede conectarse a Microsoft Access mediante la <xref:System.Data.Odbc> biblioteca.

## <a name="consuming-services"></a>Consumo de servicios

Con el aumento de las arquitecturas orientadas a servicios, las aplicaciones de escritorio empezaron a evolucionar desde un modelo cliente-servidor al enfoque de tres niveles. En el enfoque cliente-servidor, se establece una conexión de base de datos directa desde el cliente que contiene la lógica de negocios normalmente dentro de un solo archivo EXE. Por otro lado, el enfoque de tres niveles establece una capa de servicio intermedia que implementa la lógica de negocios y el acceso a bases de datos, lo que permite una mejor seguridad, escalabilidad y reutilización. En lugar de trabajar directamente con conjuntos de datos, el enfoque de capas se basa en un conjunto de servicios que implementan los contratos y los objetos de tipos como una manera de implementar la transferencia de datos.

Si tiene una aplicación de escritorio que usa un servicio WCF y desea migrarla a .NET, debe tener en cuenta algunos aspectos.

Lo primero es cómo resolver la configuración para tener acceso al servicio. Dado que la configuración es diferente en .NET, deberá hacer algunas actualizaciones en el archivo de configuración.

En segundo lugar, tendrá que volver a generar el cliente del servicio con las nuevas herramientas presentes en Visual Studio 2019. En este paso, debe considerar la posibilidad de activar la generación de las operaciones sincrónicas para hacer que el cliente sea compatible con el código existente.

Después de la migración, si observa que hay bibliotecas que necesita que no están presentes en .NET, puede Agregar una referencia al paquete de NuGet [Microsoft. Windows. Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) y ver si las funciones que faltan están allí.

Si utiliza la <xref:System.Net.WebRequest> clase para realizar llamadas de servicio Web, puede encontrar algunas diferencias en .net. En su lugar, se recomienda usar System .net. http. HttpClient.

## <a name="consuming-a-com-object"></a>Consumir un objeto COM

Actualmente, no hay ninguna manera de agregar una referencia a un objeto COM de Visual Studio 2019 para usarlo con .NET. Por lo tanto, debe modificar manualmente el archivo del proyecto.

Inserte una `COMReference` estructura dentro del archivo de proyecto como en el ejemplo siguiente:

```xml
<ItemGroup>
    <COMReference Include="MSHTML">
        <Guid>{3050F1C5-98B5-11CF-BB82-00AA00BDCE0B}\</Guid>
        <VersionMajor>4</VersionMajor>
        <VersionMinor>0</VersionMinor>
        <Lcid>0</Lcid>
        <WrapperTool>primary</WrapperTool>
        <Isolated>false</Isolated>
    </COMReference>
</ItemGroup>
```

## <a name="more-things-to-consider"></a>Más cosas que debe tener en cuenta

Varias tecnologías disponibles para las bibliotecas de .NET Framework no están disponibles para .NET Core o .NET 5. Si el código se basa en algunas de estas tecnologías, tenga en cuenta los enfoques alternativos descritos en esta sección.

El [paquete de compatibilidad de Windows](../../core/porting/windows-compat-pack.md) proporciona acceso a las API que anteriormente solo estaban disponibles para .NET Framework. Se puede usar en proyectos de .NET Core y .NET Standard.

Para obtener más información sobre la compatibilidad de la API, puede encontrar documentación sobre cambios importantes y API desusadas o heredadas en <https://docs.microsoft.com/dotnet/core/compatibility/fx-core> .

### <a name="appdomains"></a>Dominios de aplicaciones

Los dominios de aplicación aíslan las aplicaciones entre sí. Los AppDomains requieren compatibilidad en tiempo de ejecución y son caros. No se admite la creación de dominios de aplicación adicionales. En el caso del aislamiento del código, se recomiendan procesos independientes o usar contenedores como alternativa. Para la carga dinámica de ensamblados, se recomienda la nueva clase <xref:System.Runtime.Loader.AssemblyLoadContext>.

Para facilitar la migración de código de .NET Framework, .NET expone parte de la `AppDomain` superficie de la API. Algunas de las API funcionan con normalidad (por ejemplo, <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType>), algunos miembros no hacen nada (por ejemplo, <xref:System.AppDomain.SetCachePath%2A>) y algunos de ellos generan <xref:System.PlatformNotSupportedException> (por ejemplo, <xref:System.AppDomain.CreateDomain%2A>).

### <a name="remoting"></a>Comunicación remota

.NET Remoting se utilizó para la comunicación entre AppDomain, que ya no se admite. Además, la comunicación remota requiere la compatibilidad con el runtime, cuyo mantenimiento resulta caro. Por estos motivos, .NET Remoting no es compatible con .NET.

Para la comunicación entre procesos, debe considerar los mecanismos de comunicación entre procesos (IPC) como una alternativa a la comunicación remota, como la <xref:System.IO.Pipes?displayProperty=nameWithType> <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> clase o.

En los equipos, utilice una solución basada en red como una alternativa. Preferiblemente, use un protocolo de texto sin formato de baja sobrecarga, como HTTP. El servidor web Kestrel, el servidor web que usa ASP.NET Core, se puede usar como opción aquí.

### <a name="code-access-security-cas"></a>Seguridad de acceso del código (CAS)

El espacio aislado, que se basa en el tiempo de ejecución o en el marco de trabajo para restringir los recursos que una aplicación o biblioteca administrada usa o ejecuta, no es compatible con .NET.

Use los límites de seguridad proporcionados por el sistema operativo, como la virtualización, los contenedores o las cuentas de usuario para ejecutar procesos con el conjunto mínimo de privilegios.

### <a name="security-transparency"></a>Transparencia de seguridad

De forma similar a lo que ocurre con la seguridad de acceso al código, la transparencia de seguridad separa el código de espacios aislados del código crítico de seguridad de manera declarativa, pero ya no se admite como un límite de seguridad.

Use los límites de seguridad proporcionados por el sistema operativo, como la virtualización, los contenedores o las cuentas de usuario para ejecutar procesos con el menor conjunto de privilegios.

>[!div class="step-by-step"]
>[Anterior](whats-new-dotnet.md )
>[Siguiente](windows-migration.md)

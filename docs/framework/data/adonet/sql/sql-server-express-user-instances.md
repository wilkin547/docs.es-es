---
title: Instancias de usuario de SQL Server Express
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 00c12376-cb26-4317-86ad-e6e9c089be57
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f963aba983379d1474c3eedc348860751306a1bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-express-user-instances"></a>Instancias de usuario de SQL Server Express
Microsoft SQL Server Express Edition (SQL Server Express) incorpora una nueva característica de instancia de usuario, que solo está disponible cuando se usa el proveedor de datos .NET Framework para SQL Server (`SqlClient`). Una instancia de usuario es una instancia independiente del motor de base de datos de SQL Server Express que se genera mediante una instancia primaria. Las instancias de usuario permiten a los usuarios que no son administradores en sus equipos locales adjuntar y conectarse a bases de datos de SQL Server Express. Cada instancia se ejecuta en el contexto de seguridad del usuario individual, ya que solo se puede ejecutar una instancia por usuario.  
  
## <a name="user-instance-capabilities"></a>Funcionalidades de las instancias de usuario  
 Las instancias de usuario resultan muy útiles para los usuarios que ejecutan Windows desde una cuenta de usuario con privilegios mínimos, ya que cada usuario tiene privilegios de administrador del sistema (`sysadmin`) de SQL Server para la instancia que se ejecuta en su equipo sin necesidad de ser también administrador de Windows. El software que se ejecuta en una instancia de usuario con permisos limitados no puede realizar cambios en todo el sistema, puesto que la instancia de SQL Server Express se ejecuta en la cuenta del usuario de Windows que no es administrador, no como un servicio. Cada instancia de usuario se aísla de su instancia principal y de cualquier otra instancia de usuario que se ejecute en el mismo equipo. Las bases de datos que se ejecutan en una instancia de usuario se abren solo en modo usuario único y no es posible que varios usuarios se conecten a las bases de datos que se ejecutan en una instancia de usuario. La replicación y las consultas distribuidas también están deshabilitadas para las instancias de usuario.  
  
 Para obtener más información, vea "Instancias de usuario" en los Libros en línea de SQL Server.  
  
> [!NOTE]
>  Las instancias de usuario no son necesarias para los usuarios que ya son administradores en sus propios equipos o en casos en los que están implicados varios usuarios de bases de datos.  
  
## <a name="enabling-user-instances"></a>Habilitar instancias de usuario  
 Para generar instancias de usuario, debe estar ejecutándose una instancia primaria de SQL Server Express. Instancias de usuario están habilitadas de forma predeterminada cuando se instala SQL Server Express, y puede ser habilitados o deshabilitados por un administrador del sistema ejecutar explícitamente la **sp_configure** procedimiento almacenado del sistema en la instancia primaria.  
  
```  
-- Enable user instances.  
sp_configure 'user instances enabled','1'   
  
-- Disable user instances.  
sp_configure 'user instances enabled','0'  
```  
  
 El protocolo de red para las instancias de usuario debe ser el de Canalizaciones con nombre locales. No se puede iniciar una instancia de usuario en una instancia remota de SQL Server y los inicios de sesión de SQL Server no están permitidos.  
  
## <a name="connecting-to-a-user-instance"></a>Conectarse a una instancia de usuario  
 El `User Instance` y `AttachDBFilename` <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> palabras clave permiten un <xref:System.Data.SqlClient.SqlConnection> para conectarse a una instancia de usuario. Las instancias de usuario también funcionan con las propiedades <xref:System.Data.SqlClient.SqlConnectionStringBuilder>`UserInstance` y `AttachDBFilename`.  
  
 Tenga en cuenta lo siguiente sobre la cadena de conexión de ejemplo que se muestra a continuación:  
  
-   La palabra clave `Data Source` hace referencia a la instancia primaria de SQL Server Express que está generando la instancia de usuario. La instancia predeterminada es .\sqlexpress.  
  
-   El valor de `Integrated Security` está establecido en `true`. Para conectarse a una instancia de usuario, se requiere la autenticación de Windows; los inicios de sesión de SQL no están permitidos.  
  
-   La `User Instance` está establecida en `true`, por lo que invoca una instancia de usuario. (El valor predeterminado es `false`.)  
  
-   La palabra clave de cadena de conexión `AttachDbFileName` se utiliza para adjuntar el archivo de base de datos primario (.mdf), que debe incluir el nombre de ruta de acceso completo. `AttachDbFileName` se corresponde también con las claves "extended properties" e "initial file name" dentro de una cadena de conexión <xref:System.Data.SqlClient.SqlConnection>.  
  
-   La cadena de sustitución `|DataDirectory|`, que va entre barras verticales, hace referencia al directorio de datos de la aplicación que abre la conexión y proporciona una ruta de acceso relativa que muestra la ubicación de los archivos de la base de datos y de registro .mdf y .ldf. Si quiere ubicar estos archivos en cualquier otro lugar, debe indicar la ruta de acceso completa.  
  
```  
Data Source=.\\SQLExpress;Integrated Security=true;  
User Instance=true;AttachDBFilename=|DataDirectory|\InstanceDB.mdf;  
Initial Catalog=InstanceDB;  
```  
  
> [!NOTE]
>  También puede usar las propiedades <xref:System.Data.SqlClient.SqlConnectionStringBuilder><xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserInstance%2A> y <xref:System.Data.SqlClient.SqlConnectionStringBuilder.AttachDBFilename%2A> para compilar una cadena de conexión en tiempo de ejecución.  
  
### <a name="using-the-124datadirectory124-substitution-string"></a>Usar la &#124; DataDirectory &#124; Cadena de sustitución  
 `AttachDbFileName` se amplió en ADO.NET 2.0 con la incorporación de la cadena de sustitución `|DataDirectory|` (entre barras verticales). `DataDirectory` se usa junto con `AttachDbFileName` para indicar una ruta de acceso relativa a un archivo de datos, lo que permite a los desarrolladores crear cadenas de conexión basadas en una ruta relativa al origen de datos en lugar de tener que especificar la ruta completa.  
  
 La ubicación física que indica `DataDirectory` depende del tipo de aplicación. En este ejemplo, el archivo Northwind.mdf que se va a adjuntar se encuentra en la carpeta \app_data de la aplicación.  
  
```  
Data Source=.\\SQLExpress;Integrated Security=true;  
User Instance=true;  
AttachDBFilename=|DataDirectory|\app_data\Northwind.mdf;  
Initial Catalog=Northwind;  
```  
  
 Si se usa `DataDirectory`, la ruta del archivo resultante no puede estar más alta en la estructura de directorios que el directorio que señala la cadena de sustitución. Por ejemplo, si el `DataDirectory` totalmente expandido es C:\AppDirectory\app_data, la cadena de conexión de ejemplo que se muestra arriba funcionará porque está por debajo de c:\AppDirectory. Sin embargo, si se intenta especificar `DataDirectory` como `|DataDirectory|\..\data`, se producirá un error porque \data no es un subdirectorio de \AppDirectory.  
  
 Si la cadena de conexión tiene una cadena de sustitución con formato incorrecto, se producirá una <xref:System.ArgumentException>.  
  
> [!NOTE]
>  <xref:System.Data.SqlClient> resuelve las cadenas de sustitución en rutas de acceso completas del sistema de archivos del equipo local. Por eso, no se admiten rutas de acceso a servidores remotos, HTTP ni UNC. Si el servidor no se encuentra en el equipo local, se produce una excepción.  
  
 Cuando se abre <xref:System.Data.SqlClient.SqlConnection>, se redirige desde la instancia de SQL Server Express predeterminada a una instancia iniciada en tiempo de ejecución que se ejecuta en la cuenta del llamador.  
  
> [!NOTE]
>  Puede ser necesario aumentar el valor de <xref:System.Data.SqlClient.SqlConnection.ConnectionTimeout%2A> porque las instancias de usuario pueden tardar más en cargar que las instancias normales.  
  
 El siguiente fragmento de código abre una nueva `SqlConnection`, muestra la cadena de conexión en la ventana de la consola y después cierra la conexión cuando sale del bloque de código `using`.  
  
```vb  
Private Sub OpenSqlConnection()  
    ' Retrieve the connection string.  
    Dim connectionString As String = GetConnectionString()  
  
    Using connection As New SqlConnection(connectionString)  
        connection.Open()  
        Console.WriteLine("ConnectionString: {0}", _  
           connection.ConnectionString)  
    End Using  
End Sub  
```  
  
```csharp  
private static void OpenSqlConnection()  
{  
    // Retrieve the connection string.  
    string connectionString = GetConnectionString();  
  
    using (SqlConnection connection =   
        new SqlConnection(connectionString))  
    {  
        connection.Open();  
        Console.WriteLine("ConnectionString: {0}",   
             connection.ConnectionString);  
    }  
}  
```  
  
> [!NOTE]
>  No se admiten las instancias de usuario en código de Common Language Runtime (CLR) cuando se está ejecutando dentro de SQL Server. Se producirá una <xref:System.InvalidOperationException> si se llama a `Open` en una conexión <xref:System.Data.SqlClient.SqlConnection> que tiene `User Instance=true` en la cadena de conexión.  
  
## <a name="lifetime-of-a-user-instance-connection"></a>Duración de la conexión a una instancia de usuario  
 A diferencia de las versiones de SQL Server que se ejecutan como un servicio, no es necesario iniciar y detener manualmente las instancias de SQL Server. Cada vez que un usuario inicia sesión y se conecta a una instancia de usuario, ésta se inicia si no se está ejecutando ya. Las bases de datos de instancias de usuario tienen establecida la opción `AutoClose` para que la base de datos se cierre automáticamente después de un período de inactividad. El proceso sqlser.exe que se ha iniciado se mantiene en ejecución durante un período de espera limitado después de que se cierre la última conexión a la instancia, de modo que no es necesario volver a iniciarla si se abre otra conexión antes de que pase el tiempo de espera. La instancia de usuario se cierra automáticamente si no se abre ninguna conexión nueva antes de que haya expirado el período de espera. Un administrador del sistema en la instancia primaria puede establecer la duración del período de tiempo de espera para una instancia de usuario mediante el uso de **sp_configure** para cambiar la **tiempo de espera de instancia de usuario** opción. El valor predeterminado es de 60 minutos.  
  
> [!NOTE]
>  Si en la cadena de conexión se utiliza `Min Pool Size` con un valor mayor de cero, el concentrador de conexión siempre mantendrá unas cuantas conexiones abiertas y la instancia de usuario no se cerrará automáticamente.  
  
## <a name="how-user-instances-work"></a>Cómo funcionan las instancias de usuario  
 La primera vez que se genera una instancia de usuario para cada usuario, el **maestro** y **msdb** bases de datos del sistema se copian desde la carpeta de datos de la plantilla en una ruta de acceso en el repositorio de datos de aplicación local del usuario directorio para su uso exclusivo por la instancia de usuario. La ruta de acceso suele ser `C:\Documents and Settings\<UserName>\Local Settings\Application Data\Microsoft\Microsoft SQL Server Data\SQLEXPRESS`. Cuando se inicia una instancia de usuario, el **tempdb**, registro y seguimiento de archivos también se escriben en este directorio. Se genera un nombre para la instancia cuya exclusividad está garantizada para cada usuario.  
  
 De forma predeterminada, se concede permisos a todos los miembros del grupo Builtin\Users de Windows para conectarse a la instancia local, así como permisos de lectura y ejecución para los binarios de SQL Server. Una vez comprobadas las credenciales del usuario que llama y que hospeda la instancia de usuario, éste se convierte en el `sysadmin` de esa instancia. Solo hay habilitada memoria compartida para las instancias de usuario, lo que significa que solo es posible realizar operaciones en el equipo local.  
  
 Los usuarios deben recibir permisos tanto de lectura como de escritura para los archivos .mdf y .ldf especificados en la cadena de conexión.  
  
> [!NOTE]
>  Los archivos .mdf y .ldf son los archivos de la base de datos y del registro, respectivamente. Estos dos archivos forman un conjunto, así que hay que prestar mucha atención durante las operaciones de copia de seguridad y restauración. El archivo de la base de datos contiene información sobre la versión exacta del archivo de registro, y no será posible abrir la base de datos si está unida al archivo de registro incorrecto.  
  
 Para evitar que se corrompan datos, las bases de datos en las instancias de usuario se abren con acceso exclusivo. Si dos instancias de usuario diferentes comparten la misma base de datos en el mismo equipo, el usuario de la primera instancia debe cerrar la base de datos para que se pueda abrir en una segunda instancia.  
  
## <a name="user-instance-scenarios"></a>Escenarios de instancias de usuario  
 Las instancias de usuario proporcionan a los desarrolladores de aplicaciones de base de datos un almacén de datos de SQL Server que no depende de que los desarrolladores tengan cuentas administrativas en sus equipos de desarrollo. Las instancias de usuario se basan en el modelo Access/Jet, en el que la aplicación de base de datos simplemente se conecta a un archivo y automáticamente el usuario tiene todos los permisos sobre los objetos de la base de datos sin necesidad de que intervenga un administrador del sistema para concedérselos. Resulta muy práctico en situaciones en las que el usuario está utilizando una cuenta de privilegios mínimos, no tiene permisos de administrador para el servidor o el equipo local y necesita crear objetos y aplicaciones de base de datos. Las instancias de usuario permiten a los usuarios crear instancias en tiempo de ejecución que se ejecutan en el propio contexto de seguridad del usuario y no en el contexto de seguridad de un servicio del sistema con más privilegios.  
  
> [!IMPORTANT]
>  Las instancias de usuario solo se deberían utilizar cuando todas las aplicaciones que las usen sean de plena confianza.  
  
 Los escenarios de instancias de usuario incluyen:  
  
-   Cualquier aplicación de un único usuario en la que no sea necesario compartir datos  
  
-   Implementación ClickOnce Si .NET Framework 2.0, o posterior, y SQL Server Express ya están instalados en el equipo de destino, los usuarios que no sean administradores pueden instalar y utilizar el paquete de instalación que se descargó como resultado de una acción ClickOnce. Un administrador debe instalar SQL Server Express si forma parte de la instalación. Para obtener más información, consulte [implementación de ClickOnce para aplicaciones de formularios Windows Forms](http://msdn.microsoft.com/en-us/34d8c770-48f2-460c-8d67-4ea5684511df).  
  
-   Hospedaje de ASP.NET dedicado con autenticación de Windows. Una sola instancia de SQL Express Server se puede hospedar en una intranet. La aplicación se conecta usando la cuenta de Windows ASPNET, sin que haya suplantación. No se debería utilizar instancias de usuario en escenarios de hospedaje compartido o de terceros en los que todas las aplicaciones compartirían la misma instancia de usuario y dejarían de permanecer aisladas las unas de las otras.  
  
## <a name="see-also"></a>Vea también  
 [SQL Server y ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [Cadenas de conexión](../../../../../docs/framework/data/adonet/connection-strings.md)  
 [Conexión a un origen de datos](../../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)

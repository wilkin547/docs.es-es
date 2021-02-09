---
description: 'Más información acerca de: Trabajar con registros de aplicaciones en Visual Basic'
title: Trabajar con registros de aplicaciones
ms.date: 07/20/2015
helpviewer_keywords:
- logs, application
- application event logs, Visual Basic
- application event logs
ms.assetid: 2581afd1-5791-4bc4-86b2-46244e9fe468
ms.openlocfilehash: 0c05bd63cfbae668c58a87aa39651b6c3ef166ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792276"
---
# <a name="working-with-application-logs-in-visual-basic"></a>Trabajar con registros de aplicaciones en Visual Basic

Los objetos `My.Application.Log` y `My.Log` facilitan la escritura de información de registro y seguimiento en los registros.

## <a name="how-messages-are-logged"></a>Cómo se registran los mensajes

En primer lugar, se comprueba la gravedad del mensaje con la propiedad <xref:System.Diagnostics.TraceSource.Switch%2A> de la propiedad <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> del registro. De forma predeterminada, solo los mensajes de gravedad "Información" y superior se pasan a los agentes de escucha de seguimiento especificados en la colección `TraceListener` del registro. A continuación, cada agente de escucha compara la gravedad del mensaje con la propiedad <xref:System.Diagnostics.TraceSource.Switch%2A> del agente de escucha. Si la gravedad del mensaje es bastante alta, el agente de escucha escribe el mensaje.

En el siguiente diagrama se muestra cómo un mensaje escrito en el método `WriteEntry` se pasa a los métodos `WriteLine` de lo agentes de escucha de seguimiento del registro:

![Diagrama que muestra la llamada My log.](./media/working-with-application-logs/my-log-call-messages.png)

Puede cambiar el archivo de configuración de la aplicación para modificar el comportamiento de los agentes de escucha de registro y de seguimiento. En el diagrama siguiente se muestra la correspondencia entre las partes del registro y el archivo de configuración.

![Diagrama que muestra la configuración de My log.](./media/working-with-application-logs/my-log-configuration.png)

## <a name="where-messages-are-logged"></a>Dónde se registran los mensajes

Si el ensamblado no tiene ningún archivo de configuración, los objetos `My.Application.Log` y `My.Log` escriben en la salida de depuración de la aplicación (a través de la clase <xref:System.Diagnostics.DefaultTraceListener> ). Además, el objeto `My.Application.Log` escribe en el archivo de registro del ensamblado (a través de la clase <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> ), mientras que el objeto `My.Log` escribe en la salida de la página web ASP.NET (a través de la clase <xref:System.Web.WebPageTraceListener> ).

La salida de depuración se puede ver en la ventana **Salida** de Visual Studio al ejecutar la aplicación en modo de depuración. Para abrir la ventana **Salida** , haga clic en el elemento de menú **Depurar** , seleccione **Windows**, y, después, haga clic en **Salida**. En la ventana **Salida** , seleccione **Depurar** desde el cuadro **Mostrar resultados desde** .

De forma predeterminada, `My.Application.Log` escribe el archivo de registro en la ruta de acceso de los datos de aplicaciones del usuario. Puede obtener la ruta de acceso de la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> del objeto <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> . El formato de la ruta de acceso es el siguiente:

`BasePath`\\`CompanyName`\\`ProductName`\\`ProductVersion`

A continuación se indica un valor típico de `BasePath` .

C:\Documents and Settings\\`username`\Application Data

Los valores de `CompanyName`, `ProductName`y `ProductVersion` proceden de la información de ensamblado de la aplicación. El formato del nombre de archivo de registro es *nombreDeEnsamblado*.log, donde *nombreDeEnsamblado* es el nombre de archivo del ensamblado sin la extensión. Si se necesita más de un archivo de registro, por ejemplo, si el registro original no está disponible cuando la aplicación intenta escribir en el registro, el formato del nombre de archivo de registro es *nombreDeEnsamblado*-*iteration*.log, donde `iteration` es un `Integer`.

Para invalidar el comportamiento predeterminado, puede agregar o cambiar los archivos de configuración del equipo y de la aplicación. Para obtener más información, consulta [Tutorial: Cambiar el lugar donde My.Application.Log escribe información](walkthrough-changing-where-my-application-log-writes-information.md).

## <a name="configuring-log-settings"></a>Configurar el registro

El objeto `Log` tiene una implementación predeterminada que funciona sin un archivo de configuración de la aplicación, app.config. Para cambiar los valores predeterminados, debe agregar un archivo de configuración con la nueva configuración. Para obtener más información, consulta [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).

Las secciones de configuración de registro se encuentran en el nodo `<system.diagnostics>` del nodo principal `<configuration>` del archivo app.config. La información de registro se define en varios nodos:

- Los agentes de escucha del objeto `Log` se definen en el nodo `<sources>` denominado DefaultSource.

- El filtro de gravedad del objeto `Log` se definen en el nodo `<switches>` denominado DefaultSwitch.

- Los agentes de escucha de registro se definen en el nodo `<sharedListeners>` .

 En el código siguiente, se muestran ejemplos de los nodos `<sources>`, `<switches>`y `<sharedListeners>` :

```xml
<configuration>
  <system.diagnostics>
    <sources>
      <source name="DefaultSource" switchName="DefaultSwitch">
        <listeners>
          <add name="FileLog"/>
        </listeners>
      </source>
    </sources>
    <switches>
      <add name="DefaultSwitch" value="Information" />
    </switches>
    <sharedListeners>
      <add name="FileLog"
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
          Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,
          PublicKeyToken=b03f5f7f11d50a3a, processorArchitecture=MSIL"
        initializeData="FileLogWriter"
      />
    </sharedListeners>
  </system.diagnostics>
</configuration>
```

## <a name="changing-log-settings-after-deployment"></a>Cambiar la configuración de registro después de la implementación

Al desarrollar una aplicación, su configuración se almacena en el archivo app.config, tal como se muestra en los ejemplos anteriores. Después de implementar su aplicación, puede configurar el registro mediante la edición del archivo de configuración. En una aplicación basada en Windows, el nombre de este archivo es *nombreDeAplicación*.exe.config y debe encontrarse en la misma carpeta que el archivo ejecutable. En una aplicación web, es el archivo Web.config asociado al proyecto.

Cuando la aplicación ejecuta el código que crea una instancia de una clase por primera vez, comprueba el archivo de configuración para obtener información sobre el objeto. En el caso del objeto `Log` , estos sucede la primera vez que se accede al objeto `Log` . El sistema examina el archivo de configuración una sola vez par cada objeto concreto (la primera vez que la aplicación crea el objeto). Por lo tanto, es posible que deba reiniciar la aplicación para que los cambios surtan efecto.

En una aplicación implementada, el código de seguimiento se habilita volviendo a configurar los objetos modificadores antes de que se inicie la aplicación. Normalmente, esto implica activar y desactivar los objetos modificadores. Para ello, se deben cambiar los niveles de seguimiento y, luego, reiniciar la aplicación.

## <a name="security-considerations"></a>Consideraciones sobre la seguridad

Tenga en cuenta lo siguiente al escribir datos en el registro:

- **Evite la pérdida de información de usuario.** Asegúrese de que la aplicación solo escribe información aprobada en el registro. Por ejemplo, es posible que se acepte que el registro de la aplicación contenga nombres de usuario, pero no contraseñas de usuario.

- **Proteja las ubicaciones del registro.** Cualquier registro que contenga información que pueda ser confidencial debe almacenarse en una ubicación segura.

- **Evite información engañosa.** En general, la aplicación debe validar todos los datos introducidos por un usuario antes de usarlos. Se incluye la escritura de datos en el registro de la aplicación.

- **Evite la denegación de servicio.** Si su aplicación escribe demasiada información en el registro, podría llenar el registro o dificultar la búsqueda de información importante.

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [Registrar información de la aplicación](index.md)

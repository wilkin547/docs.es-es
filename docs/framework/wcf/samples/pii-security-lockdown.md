---
title: Bloqueo de seguridad PII
ms.date: 03/30/2017
ms.assetid: c44fb338-9527-4dd0-8607-b8787d15acb4
ms.openlocfilehash: 62e1495927cad669771c560603919e8f6b94d863
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559381"
---
# <a name="pii-security-lockdown"></a>Bloqueo de seguridad PII
En este ejemplo se muestra cómo controlar varias características relacionadas con la seguridad de un servicio de Windows Communication Foundation (WCF) mediante:  
  
- Cifrado de información confidencial en el archivo de configuración de un servicio.  
  
- Encerrar los elementos en el archivo de configuración para que los subdirectorios del servicio anidados no puedan reemplazar los valores.  
  
- Controlar el registro de Información de identificación personal (PII) en los registros de seguimiento y de mensajes.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\SecurityLockdown`  
  
## <a name="discussion"></a>Debate  
 Cada una de estas características puede utilizarse por separado o conjuntamente para controlar los aspectos de la seguridad de un servicio. No se trata de una guía definitiva para proteger un servicio WCF.  
  
 Los archivos de configuración de .NET Framework pueden contener información confidencial como cadenas de conexión para conectar a las bases de datos. En escenarios compartidos hospedados en web puede ser deseable cifrar esta información en el archivo de configuración para un servicio, para que los datos que contiene el archivo de configuración sean resistentes a la vista casual. La versión de .NET Framework 2.0 y posteriores tienen la capacidad de cifrar partes del archivo de configuración utilizando la interfaz del programa de aplicaciones Windows Data Protection (DPAPI) o el proveedor Criptográfico de RSA. El aspnet_regiis.exe, que utiliza DPAPI o RSA, puede cifrar partes selectas de un archivo de configuración.  
  
 En escenarios hospedados en web es posible tener los servicios en subdirectorios de otros servicios. El valor predeterminado semántico para determinar los valores de configuración permite a los archivos de configuración de los directorios anidados reemplazar los valores de configuración del directorio primario. En algunas situaciones puede no ser deseable por varias razones. La configuración del servicio WCF admite el bloqueo de valores de configuración para que la configuración anidada genere excepciones cuando se ejecuta un servicio anidado con valores de configuración invalidados.  
  
 Este ejemplo muestra cómo controlar el registro de información de identificación personal conocida (PII) en los registros de seguimiento y mensajes, como el nombre de usuario y contraseña. De forma predeterminada, el registro de PII conocida está deshabilitado, sin embargo en ciertas situaciones el registro de PII puede ser importante para depurar una aplicación. Este ejemplo se basa en el [Introducción](getting-started-sample.md). Además, este ejemplo utiliza traza y registro de mensajes. Para obtener más información, vea el ejemplo de [seguimiento y registro de mensajes](tracing-and-message-logging.md) .  
  
## <a name="encrypting-configuration-file-elements"></a>Cifrar los elementos de configuración  
 Para los propósitos de seguridad en un entorno de hospedaje en web compartido, puede ser deseable cifrar ciertos elementos de configuración, como cadenas de conexión a bases de datos que pueden contener información confidencial. Un elemento de configuración se puede cifrar mediante la herramienta aspnet_regiis.exe que se encuentra en la carpeta .NET Framework, por ejemplo,%WINDIR%\Microsoft.NET\Framework\v4.0.20728.  
  
#### <a name="to-encrypt-the-values-in-the-appsettings-section-in-webconfig-for-the-sample"></a>Para cifrar los valores de la sección appSettings de Web.config para el ejemplo  
  
1. Abra un símbolo del sistema mediante el comando de inicio >ejecutar.... Escriba `cmd` y haga clic en **Aceptar**.  
  
2. Navegue al directorio .NET Framework actual ejecutando el comando siguiente: `cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`.  
  
3. Cifre la configuración del appSettings en la carpeta Web.config ejecutando el comando siguiente: `aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`.  
  
 Para obtener más información acerca de cómo cifrar secciones de archivos de configuración, consulte la sección sobre cómo usar DPAPI en la configuración de ASP.NET ([creación de aplicaciones ASP.net seguras: autenticación, autorización y comunicación segura](/previous-versions/msp-n-p/ff649248(v=pandp.10))) y un procedimiento en RSA en la configuración de ASP.net ([Cómo: cifrar secciones de configuración en ASP.net 2,0 con RSA](/previous-versions/msp-n-p/ff650304(v=pandp.10))).  
  
## <a name="locking-configuration-file-elements"></a>Bloquear los elementos de archivo de configuración  
 En escenarios hospedados en web, es posible tener los servicios en subdirectorios de servicios. En estas situaciones, los valores de configuración para el servicio en el subdirectorio se calculan examinando los valores en Machine.config y combinando consecutivamente con cualquier archivo Web.config en directorios primarios bajando el árbol de directorios y combinando finalmente el archivo Web.config en el directorio que contiene el servicio. El comportamiento predeterminado para la mayoría de los elementos de configuración es permitir los archivos de configuración de los subdirectorios reemplazar los valores establecidos en los directorios primarios. En ciertas situaciones puede ser deseable para evitar que los archivos de configuración en subdirectorios invaliden los valores establecidos en la configuración del directorio primario.  
  
 .NET Framework proporciona una manera de bloquear los elementos de archivo de configuración para que las configuraciones que reemplazan los elementos de configuración bloqueados produzcan excepciones en tiempo de ejecución.  
  
 Un elemento de configuración se puede bloquear si se especifica el atributo `lockItem` para un nodo en el archivo de configuración. Por ejemplo, para bloquear el nodo CalculatorServiceBehavior en el archivo de configuración de modo que los servicios de calculadora de los archivos de configuración anidados no puedan cambiar el comportamiento, se puede usar la configuración siguiente.  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>
          <serviceBehaviors>
             <behavior name="CalculatorServiceBehavior" lockItem="true">
               <serviceMetadata httpGetEnabled="True"/>
               <serviceDebug includeExceptionDetailInFaults="False" />
             </behavior>
          </serviceBehaviors>
       </behaviors>
    </system.serviceModel>  
</configuration>  
```  
  
 El bloqueo de los elementos de configuración puede ser más específico. Se puede especificar una lista de elementos como valor de `lockElements` para bloquear un conjunto de elementos dentro de una colección de subelementos. Se puede especificar una lista de atributos como el valor a `lockAttributes` para bloquear un conjunto de atributos dentro de un elemento. Una colección completa de elementos o atributos se puede bloquear salvo una lista especificada especificando los atributos`lockAllElementsExcept` o`lockAllAttributesExcept` en un nodo.  
  
## <a name="pii-logging-configuration"></a>Configuración de registro de PII  
 Dos modificadores controlan el registro de PII: un valor de nivel de equipo situado en Machine.config gracias al cual un administrador de equipo puede permitir o denegar el registro de PII y un valor de aplicación que permite a un administrador de aplicación alternar el registro de PII para cada origen en un archivo Web.config o App.config.  
  
 La configuración de todo el equipo se controla estableciendo `enableLoggingKnownPii` en `true` o `false` , en el `machineSettings` elemento de Machine.config. Por ejemplo, lo siguiente permite a las aplicaciones activar el registro de PII.  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <machineSettings enableLoggingKnownPii="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
> El archivo Machine.config tiene una ubicación predeterminada: %WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG.  
  
 Si el atributo `enableLoggingKnownPii` no se encuentra en Machine.config, no se permite el registo de PII.  
  
 Para habilitar el registro de PII para una aplicación se establece el atributo `logKnownPii` del elemento de origen en `true` o `false` en el archivo Web.config o App.config. Por ejemplo, lo siguiente habilita el registro de PII para el registro de mensajes y el registro de seguimiento.  
  
```xml  
<configuration>  
    <system.diagnostics>  
        <sources>  
            <source name="System.ServiceModel.MessageLogging" logKnownPii="true">  
                <listeners>
                ...
                </listeners>  
            </source>  
            <source name="System.ServiceModel" switchValue="Verbose, ActivityTracing">  
            <listeners>  
        ...
            </listeners>  
            </source>  
        </sources>  
    </system.diagnostics>  
</configuration>  
```  
  
 Si no se especifica el atributo `logKnownPii`, a continuación, PII no está registrado.  
  
 PII solo está registrado si ambos `enableLoggingKnownPii` están establecidos en `true`, y `logKnownPii` está establecido en `true`.  
  
> [!NOTE]
> System.Diagnostics omite todos los atributos en todos los orígenes exceptuando el primero enumerado en el archivo de configuración. Agregar el atributo `logKnownPii` al segundo origen en el archivo de configuración no tiene ningún efecto.  
  
> [!IMPORTANT]
> Para ejecutar este ejemplo, se incluye la modificación manual de Machine.config. Se debe tener cuidado al modificar Machine.config como valores incorrectos o la sintaxis puede impedir que se ejecuten todas las aplicaciones .NET Framework.  
  
 También es posible cifrar elementos de archivo de configuración mediante DPAPI y RSA. Para obtener más información, vea los siguientes vínculos:  
  
- [Creación de aplicaciones de ASP.NET seguras: autenticación, autorización y comunicación segura](/previous-versions/msp-n-p/ff649248(v=pandp.10))  
  
- [Cómo cifrar secciones de configuración en ASP.NET 2.0 utilizando RSA](/previous-versions/msp-n-p/ff650304(v=pandp.10))  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Para configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Edite Machine.config para establecer el atributo `enableLoggingKnownPii` en `true`, agregando los nodos primarios si es necesario.  
  
3. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
4. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
#### <a name="to-clean-up-the-sample"></a>Para limpiar el ejemplo  
  
1. Edite Machine.config para establecer el atributo `enableLoggingKnownPii` en `false`.  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de supervisión de AppFabric](/previous-versions/appfabric/ff383407(v=azure.10))

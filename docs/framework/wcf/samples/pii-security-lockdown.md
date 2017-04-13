---
title: "Bloqueo de seguridad PII | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c44fb338-9527-4dd0-8607-b8787d15acb4
caps.latest.revision: 25
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 25
---
# Bloqueo de seguridad PII
Este ejemplo muestra cómo controlar varias características relacionadas con la seguridad de un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] por:  
  
-   Cifrado de información confidencial en el archivo de configuración de un servicio.  
  
-   Encerrar los elementos en el archivo de configuración para que los subdirectorios del servicio anidados no puedan reemplazar los valores.  
  
-   Controlar el registro de Información de identificación personal \(PII\) en los registros de seguimiento y de mensajes.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.  Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\SecurityLockdown`  
  
## Explicación  
 Cada una de estas características puede utilizarse por separado o conjuntamente para controlar los aspectos de la seguridad de un servicio.  Ésta no es una guía definitiva para proteger un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Los archivos de configuración de .NET Framework pueden contener información confidencial como cadenas de conexión para conectar a las bases de datos.  En escenarios compartidos hospedados en web puede ser deseable cifrar esta información en el archivo de configuración para un servicio, para que los datos que contiene el archivo de configuración sean resistentes a la vista casual.  La versión de .NET Framework 2.0 y posteriores tienen la capacidad de cifrar partes del archivo de configuración utilizando la interfaz del programa de aplicaciones Windows Data Protection \(DPAPI\) o el proveedor Criptográfico de RSA.  El aspnet\_regiis.exe, que utiliza DPAPI o RSA, puede cifrar partes selectas de un archivo de configuración.  
  
 En escenarios hospedados en web es posible tener los servicios en subdirectorios de otros servicios.  El valor predeterminado semántico para determinar los valores de configuración permite a los archivos de configuración de los directorios anidados reemplazar los valores de configuración del directorio primario.  En algunas situaciones puede no ser deseable por varias razones.  La configuración de servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite el bloqueo de valores de configuración para que la configuración anidada genere excepciones cuando se ejecute un servicio anidados usando valores de configuración invalidados.  
  
 Este ejemplo muestra cómo controlar el registro de información de identificación personal conocida \(PII\) en los registros de seguimiento y mensajes, como el nombre de usuario y contraseña.  De forma predeterminada, el registro de PII conocida está deshabilitado, sin embargo en ciertas situaciones el registro de PII puede ser importante para depurar una aplicación.  Este ejemplo se basa en el [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md).  Además, este ejemplo utiliza traza y registro de mensajes.  Para obtener más información, consulte el ejemplo [Seguimiento y registro de mensajes](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).  
  
## Cifrar los elementos de configuración  
 Para los propósitos de seguridad en un entorno de hospedaje en web compartido, puede ser deseable cifrar ciertos elementos de configuración, como cadenas de conexión a bases de datos que pueden contener información confidencial.  Un elemento de configuración se puede cifrar con la herramienta aspnet\_regiis.exe situada en la carpeta de .NET Framework; por ejemplo, %WINDIR%\\Micrsoft.NET\\Framework\\v4.0.20728.  
  
#### Para cifrar los valores de la sección appSettings de Web.config para el ejemplo  
  
1.  Abra un símbolo del sistema con Inicio \-\>Ejecutar...  Escriba `cmd` y haga clic en **Aceptar**.  
  
2.  Navegue al directorio .NET Framework actual ejecutando el comando siguiente: `cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`.  
  
3.  Cifre la configuración del appSettings en la carpeta Web.config ejecutando el comando siguiente: `aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`.  
  
 Para encontrar más información sobre cómo cifrar secciones de archivos de configuración, lea las instrucciones sobre DPAPI en la configuración de ASP.NET \([Crear aplicaciones ASP.NET seguras: Autenticación, Autorización y Comunicación segura](http://go.microsoft.com/fwlink/?LinkId=95137)\) y las instrucciones sobre RSA en la configuración de ASP.NET \([Cómo: Cifrar secciones de configuración en ASP.NET 2.0 mediante RSA](http://go.microsoft.com/fwlink/?LinkId=95138)\).  
  
## Bloquear los elementos de archivo de configuración  
 En escenarios hospedados en web, es posible tener los servicios en subdirectorios de servicios.  En estas situaciones, los valores de configuración para el servicio en el subdirectorio se calculan examinando los valores en Machine.config y combinando consecutivamente con cualquier archivo Web.config en directorios primarios bajando el árbol de directorios y combinando finalmente el archivo Web.config en el directorio que contiene el servicio.  El comportamiento predeterminado para la mayoría de los elementos de configuración es permitir los archivos de configuración de los subdirectorios reemplazar los valores establecidos en los directorios primarios.  En ciertas situaciones puede ser deseable para evitar que los archivos de configuración en subdirectorios invaliden los valores establecidos en la configuración del directorio primario.  
  
 .NET Framework proporciona una manera de bloquear los elementos de archivo de configuración para que las configuraciones que reemplazan los elementos de configuración bloqueados produzcan excepciones en tiempo de ejecución.  
  
 Un elemento de configuración se puede bloquear si se especifica el atributo `lockItem` para un nodo en el archivo de configuración. Por ejemplo, para bloquear el nodo CalculatorServiceBehavior en el archivo de configuración de modo que los servicios de calculadora de los archivos de configuración anidados no puedan cambiar el comportamiento, se puede usar la configuración siguiente.  
  
```  
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
  
 El bloqueo de los elementos de configuración puede ser más específico.  Se puede especificar una lista de elementos como valor de `lockElements` para bloquear un conjunto de elementos dentro de una colección de subelementos.  Se puede especificar una lista de atributos como el valor a `lockAttributes` para bloquear un conjunto de atributos dentro de un elemento.  Una colección completa de elementos o atributos se puede bloquear salvo una lista especificada especificando los atributos`lockAllElementsExcept` o`lockAllAttributesExcept` en un nodo.  
  
## Configuración de registro de PII  
 Dos modificadores controlan el registro de PII: un valor de nivel de equipo situado en Machine.config gracias al cual un administrador de equipo puede permitir o denegar el registro de PII y un valor de aplicación que permite a un administrador de aplicación alternar el registro de PII para cada origen en un archivo Web.config o App.config.  
  
 El valor de nivel de equipo se controla estableciendo `enableLoggingKnownPii` en `true` o `false`, en el elemento `machineSettings` de Machine.config.  Por ejemplo, lo siguiente permite a las aplicaciones activar el registro de PII.  
  
```  
<configuration>  
    <system.serviceModel>  
        <machineSettings enableLoggingKnownPii="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  El archivo Machine.config tiene una ubicación predeterminada: %WINDIR%\\Microsoft.NET\\Framework\\v2.0.50727\\CONFIG.  
  
 Si el atributo `enableLoggingKnownPii` no se encuentra en Machine.config, no se permite el registo de PII.  
  
 Para habilitar el registro de PII para una aplicación se establece el atributo `logKnownPii` del elemento de origen en `true` o `false` en el archivo Web.config o App.config.  Por ejemplo, lo siguiente habilita el registro de PII para el registro de mensajes y el registro de seguimiento.  
  
```  
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
>  System.Diagnostics omite todos los atributos en todos los orígenes exceptuando el primero enumerado en el archivo de configuración.  Agregar el atributo `logKnownPii` al segundo origen en el archivo de configuración no tiene ningún efecto.  
  
> [!IMPORTANT]
>  La ejecución de este ejemplo implica la modificación manual de Machine.config.  Se debería tener cuidado al modificar Machine.config, ya que los valores incorrectos o la sintaxis pueden evitar que todas las aplicaciones .NET Framework se ejecuten.  
  
 También es posible cifrar elementos de archivo de configuración mediante DPAPI y RSA.  Para obtener más información, vea los siguientes vínculos:  
  
-   [Crear aplicaciones ASP.NET seguras: Autenticación, Autorización y Comunicación segura](http://go.microsoft.com/fwlink/?LinkId=95137)  
  
-   [Cómo: Cifrar secciones de configuración en ASP.NET 2.0 mediante RSA](http://go.microsoft.com/fwlink/?LinkId=95138)  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo el [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Edite Machine.config para establecer el atributo `enableLoggingKnownPii` en `true`, agregando los nodos primarios si es necesario.  
  
3.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones en [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Para ejecutar el ejemplo en una configuración con un solo equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
#### Para limpiar el ejemplo  
  
1.  Edite Machine.config para establecer el atributo `enableLoggingKnownPii` en `false`.  
  
## Vea también  
 [Ejemplos de supervisión de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
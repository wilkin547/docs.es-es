---
title: Bloqueo de seguridad PII
ms.date: 03/30/2017
ms.assetid: c44fb338-9527-4dd0-8607-b8787d15acb4
ms.openlocfilehash: ad4f4a024b04a028b815faedded58713e001cab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144271"
---
# <a name="pii-security-lockdown"></a><span data-ttu-id="5786b-102">Bloqueo de seguridad PII</span><span class="sxs-lookup"><span data-stu-id="5786b-102">PII Security Lockdown</span></span>
<span data-ttu-id="5786b-103">En este ejemplo se muestra cómo controlar varias características relacionadas con la seguridad de un servicio de Windows Communication Foundation (WCF) mediante:</span><span class="sxs-lookup"><span data-stu-id="5786b-103">This sample demonstrates how to control several security-related features of a Windows Communication Foundation (WCF) service by:</span></span>  
  
- <span data-ttu-id="5786b-104">Cifrado de información confidencial en el archivo de configuración de un servicio.</span><span class="sxs-lookup"><span data-stu-id="5786b-104">Encrypting sensitive information in a service's configuration file.</span></span>  
  
- <span data-ttu-id="5786b-105">Encerrar los elementos en el archivo de configuración para que los subdirectorios del servicio anidados no puedan reemplazar los valores.</span><span class="sxs-lookup"><span data-stu-id="5786b-105">Locking elements in the configuration file so that nested service subdirectories cannot override settings.</span></span>  
  
- <span data-ttu-id="5786b-106">Controlar el registro de Información de identificación personal (PII) en los registros de seguimiento y de mensajes.</span><span class="sxs-lookup"><span data-stu-id="5786b-106">Controlling the logging of Personally Identifiable Information (PII) in trace and message logs.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5786b-107">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="5786b-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5786b-108">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5786b-108">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="5786b-109">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5786b-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5786b-110">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="5786b-110">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\SecurityLockdown`  
  
## <a name="discussion"></a><span data-ttu-id="5786b-111">Discusión</span><span class="sxs-lookup"><span data-stu-id="5786b-111">Discussion</span></span>  
 <span data-ttu-id="5786b-112">Cada una de estas características puede utilizarse por separado o conjuntamente para controlar los aspectos de la seguridad de un servicio.</span><span class="sxs-lookup"><span data-stu-id="5786b-112">Each of these features can be used separately or together to control aspects of a service's security.</span></span> <span data-ttu-id="5786b-113">Esta no es una guía definitiva para proteger un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="5786b-113">This is not a definitive guide to securing a WCF service.</span></span>  
  
 <span data-ttu-id="5786b-114">Los archivos de configuración de .NET Framework pueden contener información confidencial como cadenas de conexión para conectar a las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="5786b-114">The .NET Framework configuration files can contain sensitive information such as connection strings to connect to databases.</span></span> <span data-ttu-id="5786b-115">En escenarios compartidos hospedados en web puede ser deseable cifrar esta información en el archivo de configuración para un servicio, para que los datos que contiene el archivo de configuración sean resistentes a la vista casual.</span><span class="sxs-lookup"><span data-stu-id="5786b-115">In shared, Web-hosted scenarios it may be desirable to encrypt this information in the configuration file for a service so that the data contained within the configuration file is resistant to casual viewing.</span></span> <span data-ttu-id="5786b-116">La versión de .NET Framework 2.0 y posteriores tienen la capacidad de cifrar partes del archivo de configuración utilizando la interfaz del programa de aplicaciones Windows Data Protection (DPAPI) o el proveedor Criptográfico de RSA.</span><span class="sxs-lookup"><span data-stu-id="5786b-116">.NET Framework 2.0 and later has the ability to encrypt portions of the configuration file using the Windows Data Protection application programming interface (DPAPI) or the RSA Cryptographic provider.</span></span> <span data-ttu-id="5786b-117">El aspnet_regiis.exe, que utiliza DPAPI o RSA, puede cifrar partes selectas de un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5786b-117">The aspnet_regiis.exe using the DPAPI or RSA can encrypt select portions of a configuration file.</span></span>  
  
 <span data-ttu-id="5786b-118">En escenarios hospedados en web es posible tener los servicios en subdirectorios de otros servicios.</span><span class="sxs-lookup"><span data-stu-id="5786b-118">In Web-hosted scenarios it is possible to have services in subdirectories of other services.</span></span> <span data-ttu-id="5786b-119">El valor predeterminado semántico para determinar los valores de configuración permite a los archivos de configuración de los directorios anidados reemplazar los valores de configuración del directorio primario.</span><span class="sxs-lookup"><span data-stu-id="5786b-119">The default semantic for determining configuration values allows configuration files in the nested directories to override the configuration values in the parent directory.</span></span> <span data-ttu-id="5786b-120">En algunas situaciones puede no ser deseable por varias razones.</span><span class="sxs-lookup"><span data-stu-id="5786b-120">In certain situations this may be undesirable for a variety of reasons.</span></span> <span data-ttu-id="5786b-121">La configuración del servicio WCF admite el bloqueo de valores de configuración para que la configuración anidada genere excepciones cuando se ejecuta un servicio anidado mediante valores de configuración invalidados.</span><span class="sxs-lookup"><span data-stu-id="5786b-121">WCF service configuration supports the locking of configuration values so that nested configuration generates exceptions when a nested service is run using overridden configuration values.</span></span>  
  
 <span data-ttu-id="5786b-122">Este ejemplo muestra cómo controlar el registro de información de identificación personal conocida (PII) en los registros de seguimiento y mensajes, como el nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="5786b-122">This sample demonstrates how to control the logging of known Personally Identifiable Information (PII) in trace and message logs, such as username and password.</span></span> <span data-ttu-id="5786b-123">De forma predeterminada, el registro de PII conocida está deshabilitado, sin embargo en ciertas situaciones el registro de PII puede ser importante para depurar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="5786b-123">By default, logging of known PII is disabled however in certain situations logging of PII can be important in debugging an application.</span></span> <span data-ttu-id="5786b-124">Este ejemplo se basa en la [introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5786b-124">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="5786b-125">Además, este ejemplo utiliza traza y registro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="5786b-125">In addition, this sample uses tracing and message logging.</span></span> <span data-ttu-id="5786b-126">Para obtener más información, vea el [seguimiento y registro](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) de mensajes ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5786b-126">For more information, see the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample.</span></span>  
  
## <a name="encrypting-configuration-file-elements"></a><span data-ttu-id="5786b-127">Cifrar los elementos de configuración</span><span class="sxs-lookup"><span data-stu-id="5786b-127">Encrypting Configuration File Elements</span></span>  
 <span data-ttu-id="5786b-128">Para los propósitos de seguridad en un entorno de hospedaje en web compartido, puede ser deseable cifrar ciertos elementos de configuración, como cadenas de conexión a bases de datos que pueden contener información confidencial.</span><span class="sxs-lookup"><span data-stu-id="5786b-128">For security purposes in a shared Web-hosting environment, it may be desirable to encrypt certain configuration elements, such as database connection strings that may contain sensitive information.</span></span> <span data-ttu-id="5786b-129">Un elemento de configuración se puede cifrar mediante la herramienta aspnet_regiis.exe que se encuentra en la carpeta .NET Framework, por ejemplo, %WINDIR%.</span><span class="sxs-lookup"><span data-stu-id="5786b-129">A configuration element may be encrypted using the aspnet_regiis.exe tool found in the .NET Framework folder For example, %WINDIR%\Microsoft.NET\Framework\v4.0.20728.</span></span>  
  
#### <a name="to-encrypt-the-values-in-the-appsettings-section-in-webconfig-for-the-sample"></a><span data-ttu-id="5786b-130">Para cifrar los valores de la sección appSettings de Web.config para el ejemplo</span><span class="sxs-lookup"><span data-stu-id="5786b-130">To encrypt the values in the appSettings section in Web.config for the sample</span></span>  
  
1. <span data-ttu-id="5786b-131">Abra un símbolo del sistema mediante Start->Run....</span><span class="sxs-lookup"><span data-stu-id="5786b-131">Open a command prompt by using Start->Run….</span></span> <span data-ttu-id="5786b-132">Escriba `cmd` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5786b-132">Type in `cmd` and click **OK**.</span></span>  
  
2. <span data-ttu-id="5786b-133">Navegue al directorio .NET Framework actual ejecutando el comando siguiente: `cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`.</span><span class="sxs-lookup"><span data-stu-id="5786b-133">Navigate to the current .NET Framework directory by issuing the following command: `cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`.</span></span>  
  
3. <span data-ttu-id="5786b-134">Cifre la configuración del appSettings en la carpeta Web.config ejecutando el comando siguiente: `aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`.</span><span class="sxs-lookup"><span data-stu-id="5786b-134">Encrypt the appSettings configuration settings in the Web.config folder by issuing the following command: `aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`.</span></span>  
  
 <span data-ttu-id="5786b-135">Puede encontrar más información sobre el cifrado de secciones de archivos de configuración leyendo un modo de acceso en DPAPI en ASP.NET configuración (Creación de[aplicaciones de ASP.NET segura: autenticación, autorización y comunicación segura)](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))y un modo de comunicación en RSA en ASP.NET configuración ([Cómo: cifrar secciones de configuración en ASP.NET 2.0 mediante RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))).</span><span class="sxs-lookup"><span data-stu-id="5786b-135">More information about encrypting sections of configuration files can be found by reading a how-to on DPAPI in ASP.NET configuration ([Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))) and a how-to on RSA in ASP.NET configuration ([How To: Encrypt Configuration Sections in ASP.NET 2.0 Using RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))).</span></span>  
  
## <a name="locking-configuration-file-elements"></a><span data-ttu-id="5786b-136">Bloquear los elementos de archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="5786b-136">Locking configuration file elements</span></span>  
 <span data-ttu-id="5786b-137">En escenarios hospedados en web, es posible tener los servicios en subdirectorios de servicios.</span><span class="sxs-lookup"><span data-stu-id="5786b-137">In Web-hosted scenarios, it is possible to have services in subdirectories of services.</span></span> <span data-ttu-id="5786b-138">En estas situaciones, los valores de configuración para el servicio en el subdirectorio se calculan examinando los valores en Machine.config y combinando consecutivamente con cualquier archivo Web.config en directorios primarios bajando el árbol de directorios y combinando finalmente el archivo Web.config en el directorio que contiene el servicio.</span><span class="sxs-lookup"><span data-stu-id="5786b-138">In these situations, configuration values for the service in the subdirectory are calculated by examining values in Machine.config and successively merging with any Web.config files in parent directories moving down the directory tree and finally merging the Web.config file in the directory that contains the service.</span></span> <span data-ttu-id="5786b-139">El comportamiento predeterminado para la mayoría de los elementos de configuración es permitir los archivos de configuración de los subdirectorios reemplazar los valores establecidos en los directorios primarios.</span><span class="sxs-lookup"><span data-stu-id="5786b-139">The default behavior for most configuration elements is to allow configuration files in subdirectories to override the values set in parent directories.</span></span> <span data-ttu-id="5786b-140">En ciertas situaciones puede ser deseable para evitar que los archivos de configuración en subdirectorios invaliden los valores establecidos en la configuración del directorio primario.</span><span class="sxs-lookup"><span data-stu-id="5786b-140">In certain situations it may be desirable to prevent configuration files in subdirectories from overriding values set in parent directory configuration.</span></span>  
  
 <span data-ttu-id="5786b-141">.NET Framework proporciona una manera de bloquear los elementos de archivo de configuración para que las configuraciones que reemplazan los elementos de configuración bloqueados produzcan excepciones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5786b-141">The .NET Framework provides a way to lock configuration file elements so that configurations that override locked configuration elements throw run-time exceptions.</span></span>  
  
 <span data-ttu-id="5786b-142">Un elemento de configuración se puede bloquear si se especifica el atributo `lockItem` para un nodo en el archivo de configuración. Por ejemplo, para bloquear el nodo CalculatorServiceBehavior en el archivo de configuración de modo que los servicios de calculadora de los archivos de configuración anidados no puedan cambiar el comportamiento, se puede usar la configuración siguiente.</span><span class="sxs-lookup"><span data-stu-id="5786b-142">A configuration element can be locked by specifying the `lockItem` attribute for a node in the configuration file, for example, to lock the CalculatorServiceBehavior node in the configuration file so that calculator services in nested configuration files cannot change the behavior, the following configuration can be used.</span></span>  
  
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
  
 <span data-ttu-id="5786b-143">El bloqueo de los elementos de configuración puede ser más específico.</span><span class="sxs-lookup"><span data-stu-id="5786b-143">Locking of configuration elements can be more specific.</span></span> <span data-ttu-id="5786b-144">Se puede especificar una lista de elementos como valor de `lockElements` para bloquear un conjunto de elementos dentro de una colección de subelementos.</span><span class="sxs-lookup"><span data-stu-id="5786b-144">A list of elements can be specified as the value to the `lockElements` to lock a set of elements within a collection of sub-elements.</span></span> <span data-ttu-id="5786b-145">Se puede especificar una lista de atributos como el valor a `lockAttributes` para bloquear un conjunto de atributos dentro de un elemento.</span><span class="sxs-lookup"><span data-stu-id="5786b-145">A list of attributes can be specified as the value to the `lockAttributes` to lock a set of attributes within an element.</span></span> <span data-ttu-id="5786b-146">Una colección completa de elementos o atributos se puede bloquear salvo una lista especificada especificando los atributos`lockAllElementsExcept` o`lockAllAttributesExcept` en un nodo.</span><span class="sxs-lookup"><span data-stu-id="5786b-146">An entire collection of elements or attributes can be locked except for a specified list by specifying the `lockAllElementsExcept` or `lockAllAttributesExcept` attributes on a node.</span></span>  
  
## <a name="pii-logging-configuration"></a><span data-ttu-id="5786b-147">Configuración de registro de PII</span><span class="sxs-lookup"><span data-stu-id="5786b-147">PII Logging Configuration</span></span>  
 <span data-ttu-id="5786b-148">Dos modificadores controlan el registro de PII: un valor de nivel de equipo situado en Machine.config gracias al cual un administrador de equipo puede permitir o denegar el registro de PII y un valor de aplicación que permite a un administrador de aplicación alternar el registro de PII para cada origen en un archivo Web.config o App.config.</span><span class="sxs-lookup"><span data-stu-id="5786b-148">Logging of PII is controlled by two switches: a computer-wide setting found in Machine.config that allows a computer administrator to permit or deny logging of PII and an application setting that allows an application administrator to toggle logging of PII for each source in a Web.config or App.config file.</span></span>  
  
 <span data-ttu-id="5786b-149">La configuración de todo el `enableLoggingKnownPii` equipo `true` `false`se controla estableciendo en o , en el `machineSettings` elemento de Machine.config. Por ejemplo, lo siguiente permite a las aplicaciones activar el registro de PII.</span><span class="sxs-lookup"><span data-stu-id="5786b-149">The computer-wide setting is controlled by setting `enableLoggingKnownPii` to `true` or `false`, in the `machineSettings` element in Machine.config. For example, the following allows applications to turn on logging of PII.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <machineSettings enableLoggingKnownPii="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
> <span data-ttu-id="5786b-150">El archivo Machine.config tiene una ubicación predeterminada: %WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="5786b-150">The Machine.config file has a default location: %WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG.</span></span>  
  
 <span data-ttu-id="5786b-151">Si el atributo `enableLoggingKnownPii` no se encuentra en Machine.config, no se permite el registo de PII.</span><span class="sxs-lookup"><span data-stu-id="5786b-151">If the `enableLoggingKnownPii` attribute is not present in Machine.config, logging of PII is not allowed.</span></span>  
  
 <span data-ttu-id="5786b-152">Para habilitar el registro de PII para una aplicación se establece el atributo `logKnownPii` del elemento de origen en `true` o `false` en el archivo Web.config o App.config.</span><span class="sxs-lookup"><span data-stu-id="5786b-152">Enabling logging of PII for an application is done by setting the `logKnownPii` attribute of the source element to `true` or `false` in the Web.config or App.config file.</span></span> <span data-ttu-id="5786b-153">Por ejemplo, lo siguiente habilita el registro de PII para el registro de mensajes y el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5786b-153">For example, the following enables logging of PII for both message logging and trace logging.</span></span>  
  
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
  
 <span data-ttu-id="5786b-154">Si no se especifica el atributo `logKnownPii`, a continuación, PII no está registrado.</span><span class="sxs-lookup"><span data-stu-id="5786b-154">If the `logKnownPii` attribute is not specified, then PII is not logged.</span></span>  
  
 <span data-ttu-id="5786b-155">PII solo está registrado si ambos `enableLoggingKnownPii` están establecidos en `true`, y `logKnownPii` está establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="5786b-155">PII is only logged if both `enableLoggingKnownPii` is set to `true`, and `logKnownPii` is set to `true`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5786b-156">System.Diagnostics omite todos los atributos en todos los orígenes exceptuando el primero enumerado en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5786b-156">System.Diagnostics ignores all attributes on all sources except the first one listed in the configuration file.</span></span> <span data-ttu-id="5786b-157">Agregar el atributo `logKnownPii` al segundo origen en el archivo de configuración no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="5786b-157">Adding the `logKnownPii` attribute to the second source in the configuration file has no effect.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5786b-158">Para ejecutar este ejemplo implica la modificación manual de Machine.config. Se debe tener cuidado al modificar Machine.config, ya que los valores o la sintaxis incorrectos pueden impedir que se ejecuten todas las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5786b-158">To run this sample involves manual modification of Machine.config. Care should be taken when modifying Machine.config as incorrect values or syntax may prevent all .NET Framework applications from running.</span></span>  
  
 <span data-ttu-id="5786b-159">También es posible cifrar elementos de archivo de configuración mediante DPAPI y RSA.</span><span class="sxs-lookup"><span data-stu-id="5786b-159">It is also possible to encrypt configuration file elements using DPAPI and RSA.</span></span> <span data-ttu-id="5786b-160">Para obtener más información, vea los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="5786b-160">For more information, see the following links:</span></span>  
  
- <span data-ttu-id="5786b-161">[Creación de aplicaciones de ASP.NET segura: autenticación, autorización y comunicación segura](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="5786b-161">[Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))</span></span>  
  
- <span data-ttu-id="5786b-162">[Cómo cifrar secciones de configuración en ASP.NET 2.0 utilizando RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="5786b-162">[How To: Encrypt Configuration Sections in ASP.NET 2.0 Using RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5786b-163">Para configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="5786b-163">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="5786b-164">Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="5786b-164">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="5786b-165">Edite Machine.config para establecer el atributo `enableLoggingKnownPii` en `true`, agregando los nodos primarios si es necesario.</span><span class="sxs-lookup"><span data-stu-id="5786b-165">Edit Machine.config to set the `enableLoggingKnownPii` attribute to `true`, adding the parent nodes if necessary.</span></span>  
  
3. <span data-ttu-id="5786b-166">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5786b-166">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="5786b-167">Para ejecutar el ejemplo en una configuración de un equipo o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="5786b-167">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
#### <a name="to-clean-up-the-sample"></a><span data-ttu-id="5786b-168">Para limpiar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="5786b-168">To clean up the sample</span></span>  
  
1. <span data-ttu-id="5786b-169">Edite Machine.config para establecer el atributo `enableLoggingKnownPii` en `false`.</span><span class="sxs-lookup"><span data-stu-id="5786b-169">Edit Machine.config to set the `enableLoggingKnownPii` attribute to `false`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5786b-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5786b-170">See also</span></span>

- <span data-ttu-id="5786b-171">[Ejemplos de supervisión de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="5786b-171">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>

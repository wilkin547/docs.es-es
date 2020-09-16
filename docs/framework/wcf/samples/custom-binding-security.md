---
title: Seguridad de enlace personalizado
ms.date: 03/30/2017
ms.assetid: a6383dff-4308-46d2-bc6d-acd4e18b4b8d
ms.openlocfilehash: ce4cd76a053b9b3611751fe081d0ca710240049d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555710"
---
# <a name="custom-binding-security"></a>Seguridad de enlace personalizado

Este ejemplo muestra cómo configurar la seguridad mediante un enlace personalizado. Muestra cómo utilizar un enlace personalizado para habilitar la seguridad de nivel de mensaje junto con un transporte seguro. Esto es útil cuando se exige un transporte seguro que transmita los mensajes entre el cliente y servicio y simultáneamente los mensajes deben ser seguros en el nivel de mensaje. Los enlaces proporcionados por el sistema no admiten esta configuración.

Este ejemplo está compuesto por un programa de consola de cliente (EXE) y un programa de consola de servicio (EXE). El servicio implementa un contrato dúplex. La interfaz `ICalculatorDuplex`, que expone las operaciones matemáticas (sumar, restar, multiplicar y dividir), define el contrato. La interfaz `ICalculatorDuplex` permite al cliente realizar las operaciones de matemática, calculando un resultado en ejecución sobre una sesión. Independientemente, el servicio puede devolver resultados en la interfaz `ICalculatorDuplexCallback`. Un contrato dúplex requiere una sesión, porque se debe establecer un contexto para poner en correlación el conjunto de mensajes que se envían entre el cliente y el servicio. Se define un enlace personalizado que admite la comunicación dúplex y es seguro.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

La configuración del servicio define un enlace personalizado que admite lo siguiente:

- Comunicación TCP protegida mediante el protocolo TLS/SSL.

- Seguridad de mensaje de Windows.

La configuración de enlace personalizado permite el transporte seguro, habilitando simultáneamente la seguridad de nivel de mensaje. El orden de los elementos de enlace es importante en la definición de un enlace personalizado, ya que cada uno representa una capa en la pila del canal (vea [enlaces personalizados](../extending/custom-bindings.md)). El enlace personalizado se define en los archivos de configuración de cliente y servicio, como se muestra en la configuración del ejemplo siguiente.

```xml
<bindings>
  <!-- Configure a custom binding. -->
  <customBinding>
    <binding name="Binding1">
      <security authenticationMode="SecureConversation"
                 requireSecurityContextCancellation="true">
      </security>
      <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>
      <sslStreamSecurity requireClientCertificate="false"/>
      <tcpTransport/>
    </binding>
  </customBinding>
</bindings>
```

El enlace personalizado utiliza un certificado de servicio para autenticar el servicio en el nivel de transporte y proteger los mensajes durante la transmisión entre el cliente y servicio. Esto lo lleva a cabo el elemento de enlace `sslStreamSecurity`. El certificado del servicio se configura utilizando un comportamiento del servicio como se muestra en la configuración del ejemplo siguiente.

```xml
<behaviors>
    <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
        <serviceMetadata />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <serviceCredentials>
        <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName"/>
        </serviceCredentials>
    </behavior>
    </serviceBehaviors>
</behaviors>
```

Además, el enlace personalizado utiliza seguridad de mensajes con tipo de credencial de Windows; éste es el tipo de credencial predeterminado. Esto lo lleva a cabo el elemento de enlace `security`. Cliente y servicio se autentican utilizando la seguridad de nivel de mensaje si el mecanismo de autenticación Kerberos está disponible. Esto sucede si el ejemplo se ejecuta en el entorno de Active Directory. Si el mecanismo de autenticación Kerberos no está disponible, se utiliza la autenticación NTLM. NTLM autentica el cliente para el servicio pero no autentica el servicio para el cliente. El `security` elemento de enlace se configura para utilizar `SecureConversation` `authenticationType` , lo que da lugar a la creación de una sesión de seguridad tanto en el cliente como en el servicio. Esto se exige para que funcione el contrato del dúplex del servicio.

Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.

```console
Press <ENTER> to terminate client.
Result(100)
Result(50)
Result(882.5)
Result(441.25)
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)
```

Al ejecutar el ejemplo, se ven los mensajes devueltos al cliente en la interfaz de devolución de llamada enviada del servicio. Se muestra cada resultado intermedio, seguido por la ecuación completa en la realización de todas las operaciones. Presione Entrar para cerrar el cliente.

El archivo Setup.bat incluido con este ejemplo permite configurar el cliente y el servidor con los certificados de servicio pertinentes para ejecutar una aplicación hospedada que requiera seguridad basada en certificado. Este archivo por lotes debe modificarse para que funcione en varios equipos o en un escenario sin hospedaje.

A continuación se proporciona una descripción breve de las diferentes secciones de los archivos por lotes que se aplican en este ejemplo con objeto de que se puedan modificar para ejecutarse con la configuración adecuada.

- Crear el certificado de servidor.

  Las líneas siguientes del archivo Setup.bat crean el certificado de servidor que se va a usar. La variable `%SERVER_NAME%`especifica el nombre del servidor. Cambie esta variable para especificar su propio nombre de servidor. Este archivo por lotes determina como valor predeterminado el nombre del servidor como host local.

  El certificado se almacena en el almacén de CurrentUser para los servicios hospedados en web.

  ```bat
  echo ************
  echo Server cert setup starting
  echo %SERVER_NAME%
  echo ************
  echo making server cert
  echo ************
  makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
  ```

- Instalar el certificado del servidor en el almacén de certificados de confianza del cliente.

  Las líneas siguientes del archivo Setup.bat copian el certificado de servidor en el almacén de usuarios de confianza del cliente. Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.

  ```console
  certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
  ```

  > [!NOTE]
  > El archivo por lotes Setup.bat está diseñado para ejecutarse desde el símbolo del sistema de Visual Studio 2010. Requiere que la variable de entorno de MSSDK se dirija al directorio donde está instalado el SDK. Esta variable de entorno se establece automáticamente dentro de un símbolo del sistema de Visual Studio 2010.

### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).

3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).

### <a name="to-run-the-sample-on-the-same-computer"></a>Para ejecutar el ejemplo en el mismo equipo

1. Abra un Símbolo del sistema para desarrolladores para la ventana de Visual Studio con privilegios de administrador y ejecute Setup.bat desde la carpeta de instalación de ejemplo. De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.

    > [!NOTE]
    > El archivo por lotes Setup.bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012. La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup.bat.

2. Inicie Service.exe desde \service\bin.

3. Inicie Client.exe desde \client\bin. La actividad del cliente se muestra en la aplicación de consola del cliente.

4. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).

### <a name="to-run-the-sample-across-computers"></a>Para ejecutar el ejemplo en varios equipos

1. En el equipo del servicio:

    1. Cree un directorio virtual denominado servicemodelsamples en el equipo del servicio.

    2. Copie los archivos de programa de servicio del directorio \inetpub\wwwroot\servicemodelsamples al directorio virtual del equipo de servicio. Asegúrese de que copia los archivos en el subdirectorio \bin.

    3. Copie los archivos Setup.bat y Cleanup.bat en el equipo del servicio.

    4. Ejecute el siguiente comando en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador: `Setup.bat service` . Así se crea el certificado del servicio con un nombre de sujeto que coincide con el nombre del equipo en el que se ejecutó el archivo por lotes.

        > [!NOTE]
        > El archivo por lotes Setup.bat está diseñado para ejecutarse desde el símbolo del sistema de Visual Studio 2010. Requiere que la variable de entorno path señale al directorio donde está instalado el SDK. Esta variable de entorno se establece automáticamente dentro de un símbolo del sistema de Visual Studio 2010.

    5. Cambie en [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) el archivo de Service.exe.config para que refleje el nombre de sujeto del certificado generado en el paso anterior.

    6. Ejecute Service.exe desde un símbolo del sistema.

2. En el equipo cliente:

    1. Copie los archivos de programa del cliente de la carpeta \client\bin\ al equipo cliente. Copie también el archivo Cleanup.bat.

    2. Ejecute Cleanup.bat para quitar cualquier certificado antiguo de ejemplos anteriores.

    3. Exporte el certificado del servicio abriendo un Símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador y ejecutando el siguiente comando en el equipo del servicio (sustituya `%SERVER_NAME%` por el nombre completo del equipo donde se está ejecutando el servicio):

        ```console
        certmgr -put -r LocalMachine -s My -c -n %SERVER_NAME% %SERVER_NAME%.cer
        ```

    4. Copie % SERVER_NAME%.cer en el equipo cliente (sustituya % SERVER_NAME% con el nombre completo del equipo donde se está ejecutando el servicio).

    5. Importe el certificado del servicio abriendo un Símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador y ejecutando el siguiente comando en el equipo cliente (sustituya% SERVER_NAME% por el nombre completo del equipo en el que se está ejecutando el servicio):

        ```console
        certmgr.exe -add -c %SERVER_NAME%.cer -s -r CurrentUser TrustedPeople
        ```

        Los pasos c, d y e no son necesarios si el certificado procede de un emisor de confianza.

    6. Modifique el archivo App.config del cliente como sigue:

        ```xml
        <client>
            <endpoint name="default"
                address="net.tcp://ReplaceThisWithServiceMachineName:8000/ServiceModelSamples/Service"
                binding="customBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex"
                behaviorConfiguration="CalculatorClientBehavior" />
        </client>
        ```

    7. Si el servicio se está ejecutando con una cuenta que no es NetworkService o LocalSystem en un entorno de dominio, puede que sea necesario modificar la identidad del extremo de servicio en el archivo App.config del cliente para establecer el UPN o SPN adecuado en función de la cuenta que se utilice para ejecutar el servicio. Para obtener más información acerca de la identidad del punto de conexión, consulte el tema [identidad de servicio y autenticación](../feature-details/service-identity-and-authentication.md) .

    8. Ejecute Client.exe desde un símbolo del sistema.

### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo

- Ejecute Cleanup.bat en la carpeta de ejemplos después de que haya terminado de ejecutar el ejemplo.

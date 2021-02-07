---
description: Más información acerca de cómo ejecutar los ejemplos de Windows Communication Foundation
title: Ejecución de los ejemplos de Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: db8a83da-95c1-4a21-a9d2-48caeb6398ea
ms.openlocfilehash: 4edbd7aef8eed42e4815666c15ff07aa2c2e82de
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703736"
---
# <a name="running-the-windows-communication-foundation-samples"></a>Ejecución de los ejemplos de Windows Communication Foundation

Los ejemplos de Windows Communication Foundation (WCF) se pueden ejecutar en una configuración de un solo equipo o entre equipos. Tal y como se proporcionan, los ejemplos están listos para ejecutarse en un equipo único. En una configuración de equipos cruzada, es necesario modificar la configuración del archivo de configuración de un ejemplo. Los procedimientos siguientes explican cómo ejecutar un ejemplo en mismo equipo y en configuraciones de equipos cruzadas. Observe que hay variaciones en los pasos para los servicios hospedados en Internet Information Services (IIS) y los ejemplos autohospedados. La mayoría de los ejemplos se hospedan en IIS; vea la información readme del ejemplo para determinar cómo se hospeda.  
  
 En Windows Vista, los ejemplos que no se hospedan en IIS requieren privilegios elevados para registrar un agente de escucha con Http.sys. Utilice Httpcfg.exe para registrar las direcciones de escucha del servicio con la cuenta bajo la que el servicio se está ejecutando o inicie el servicio desde un símbolo del sistema que se ejecuta con privilegios de administrador.  
  
> [!NOTE]
> Antes de compilar o ejecutar cualquiera de los ejemplos de WCF, asegúrese de que ha realizado el [procedimiento de instalación único para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
### <a name="to-run-the-sample-on-the-same-machine"></a>Para ejecutar el ejemplo en el mismo equipo  
  
1. Si IIS hospeda el servicio, asegúrese de que puede tener acceso al servicio mediante un explorador escribiendo la dirección siguiente: `http://localhost/servicemodelsamples/service.svc` . Como respuesta se debe mostrar una página de confirmación. Si no se muestra la página de confirmación, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
2. Si el servicio es autohospedado, ejecute Service.exe desde \service\bin, bajo la carpeta específica del lenguaje. La actividad del servicio se muestra en la ventana de la consola del servicio.  
  
3. Ejecute Client.exe desde \client\bin\ \\ , en la carpeta específica del lenguaje. La actividad del cliente se muestra en la ventana de consola del cliente.  
  
4. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-run-the-sample-across-machines"></a>Para ejecutar el ejemplo en los equipos  
  
1. Si el servicio se hospeda en IIS:  
  
    1. En el equipo del servicio, cree un directorio virtual denominado ServiceModelSamples. El archivo por lotes Setupvroot.bat incluido con [el procedimiento de instalación único para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md) se puede usar para crear el directorio de disco y el directorio virtual.  
  
    2. Copie los archivos de programa de servicio del directorio %SystemDrive%\Inetpub \wwwroot\servicemodelsamples al directorio virtual ServiceModelSamples del equipo de servicio. Asegúrese de que incluye los archivos en el directorio \bin.  
  
    3. Pruebe que puede tener acceso al servicio desde el equipo cliente utilizando un explorador.  
  
     Si el servicio es autohospedado:  
  
    1. Cree un directorio en el equipo del servicio para mantener los archivos del servicio.  
  
    2. Copie los archivos de programa de servicio de la carpeta \service\bin\, bajo la carpeta específica del lenguaje, al equipo del servicio.  
  
    3. En el archivo de configuración del servicio, cambie el valor de la dirección de la definición del punto de conexión para que coincida con la nueva dirección de su servicio. Reemplace cualquier referencia a "localhost" con un nombre de dominio completo en la dirección.  
  
    4. Inicie Service.exe desde un símbolo del sistema.  
  
2. Copie los archivos de programa del cliente de la carpeta \client\bin\, en la carpeta específica del lenguaje, al equipo del cliente.  
  
3. Fije la dirección del punto de conexión.  
  
    1. Si el servicio no se está ejecutando bajo una cuenta de dominio, abra el archivo de configuración del cliente y cambie el valor de dirección de la definición de extremo para que coincida con la nueva dirección de su servicio. Reemplace cualquier referencia a "localhost" con un nombre de dominio completo en la dirección.  
  
    2. Si el servicio se está ejecutando bajo una cuenta de dominio, regenere la configuración del cliente ejecutando Svcutil.exe en el servicio. Para obtener más información sobre la ejecución de Svcutil.exe, vea [Building the Windows Communication Foundation samples](building-the-samples.md). Utilice el archivo generado en lugar del archivo de configuración en el ejemplo. El archivo de configuración generado tiene información de identidad adicional y contiene todos los valores necesarios para conectarse al punto de conexión de servicio, aunque se trate de la configuración predeterminada. Para obtener más información acerca de la información de identidad, vea [identidad de servicio y autenticación](../feature-details/service-identity-and-authentication.md), y [\<identity>](../../configure-apps/file-schema/wcf/identity.md) .  
  
4. En el equipo cliente, inicie Client.exe desde el símbolo del sistema.  
  
### <a name="to-debug-a-service"></a>Para depurar un servicio  
  
1. Compile la solución (cliente y servicio) mediante el menú **compilar** o Ctrl + Mayús + B.  
  
2. Si el servicio se hospeda en IIS:  
  
    1. Active el servicio mediante un explorador escribiendo la dirección `http://localhost/servicemodelsamples/service.svc` .  
  
    2. En la solución, elija el menú **depurar** y el elemento de menú **asociar al proceso** .  
  
    3. Active la casilla **Mostrar los procesos de todos los usuarios**.  
  
    4. Seleccione el proceso de trabajador host W3wp.exe para depurar (seleccione ASPNet_wp.exe en Windows XP).  
  
3. Ahora puede establecer puntos de interrupción en el código del servicio y habilitar puntos de interrupción en excepciones.  
  
4. Haga clic con el botón secundario en el elemento de proyecto de cliente y elija **depurar**, **Iniciar nueva instancia**.  
  
### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo  
  
- Si el servicio se hospeda en IIS por razones de seguridad, quite la definición del directorio virtual y los permisos concedidos en los pasos de instalación cuando acabe con los ejemplos.  
  
## <a name="see-also"></a>Vea también

- [Compilación de los ejemplos de Windows Communication Foundation](building-the-samples.md)
- [Sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))

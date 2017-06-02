---
title: "Ejecuci&#243;n de los ejemplos de Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: db8a83da-95c1-4a21-a9d2-48caeb6398ea
caps.latest.revision: 26
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 26
---
# Ejecuci&#243;n de los ejemplos de Windows Communication Foundation
Los ejemplos [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se pueden ejecutar en un equipo único o en una configuración de equipos cruzada.  Tal y como se proporcionan, los ejemplos están listos para ejecutarse en un equipo único.  En una configuración de equipos cruzada, es necesario modificar la configuración del archivo de configuración de un ejemplo.  Los procedimientos siguientes explican cómo ejecutar un ejemplo en mismo equipo y en configuraciones de equipos cruzadas.  Observe que hay variaciones en los pasos para los servicios hospedados en Internet Information Services \(IIS\) y los ejemplos autohospedados.  La mayoría de los ejemplos se hospedan en IIS; vea la información readme del ejemplo para determinar cómo se hospeda.  
  
 En [!INCLUDE[wv](../../../../includes/wv-md.md)], los ejemplos que no están hospedados en IIS exigen privilegios elevados para registrar un agente de escucha con Http.sys.  Utilice Httpcfg.exe para registrar las direcciones de escucha del servicio con la cuenta bajo la que el servicio se está ejecutando o inicie el servicio desde un símbolo del sistema que se ejecuta con privilegios de administrador.  
  
> [!NOTE]
>  Antes de compilar o ejecutar cualquiera de los ejemplos [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], asegúrese de que ha realizado [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
### Para ejecutar el ejemplo en el mismo equipo  
  
1.  Si el servicio está hospedado en IIS, asegúrese de que puede tener acceso al servicio usando un explorador; para ello, escriba la dirección siguiente: http:\/\/localhost\/servicemodelsamples\/service.svc.  Como respuesta se debe mostrar una página de confirmación.  Si no se muestra la página de confirmación, vea [Troubleshooting Tips](http://msdn.microsoft.com/es-es/8787c877-5e96-42da-8214-fa737a38f10b).  
  
2.  Si el servicio es autohospedado, ejecute Service.exe desde \\service\\bin, bajo la carpeta específica del lenguaje.  La actividad del servicio se muestra en la ventana de la consola del servicio.  
  
3.  Ejecute Client.exe desde \\client\\bin\\, desde la carpeta específica del lenguaje.  La actividad del cliente se muestra en la ventana de consola del cliente.  
  
4.  Si el cliente y el servicio no se pueden comunicar, vea [Troubleshooting Tips](http://msdn.microsoft.com/es-es/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### Para ejecutar el ejemplo en los equipos  
  
1.  Si el servicio se hospeda en IIS:  
  
    1.  En el equipo del servicio, cree un directorio virtual denominado ServiceModelSamples.  El archivo por lotes Setupvroot.bat incluido con [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) se puede utilizar para crear el directorio de disco y el directorio virtual.  
  
    2.  Copie los archivos de programa de servicio del directorio %SystemDrive%\\Inetpub \\wwwroot\\servicemodelsamples al directorio virtual ServiceModelSamples del equipo de servicio.  Asegúrese de que incluye los archivos en el directorio \\bin.  
  
    3.  Pruebe que puede tener acceso al servicio desde el equipo cliente utilizando un explorador.  
  
     Si el servicio es autohospedado:  
  
    1.  Cree un directorio en el equipo del servicio para mantener los archivos del servicio.  
  
    2.  Copie los archivos de programa de servicio de la carpeta \\service\\bin\\, bajo la carpeta específica del lenguaje, al equipo del servicio.  
  
    3.  En el archivo de configuración del servicio, cambie el valor de la dirección de la definición del extremo para que coincida con la nueva dirección de su servicio.  Reemplace cualquier referencia a "localhost" con un nombre de dominio completo en la dirección.  
  
    4.  Inicie Service.exe desde un símbolo del sistema.  
  
2.  Copie los archivos de programa del cliente de la carpeta \\client\\bin\\, en la carpeta específica del lenguaje, al equipo del cliente.  
  
3.  Fije la dirección del extremo.  
  
    1.  Si el servicio no se está ejecutando bajo una cuenta de dominio, abra el archivo de configuración del cliente y cambie el valor de dirección de la definición de extremo para que coincida con la nueva dirección de su servicio.  Reemplace cualquier referencia a "localhost" con un nombre de dominio completo en la dirección.  
  
    2.  Si el servicio se está ejecutando bajo una cuenta de dominio, regenere la configuración del cliente ejecutando Svcutil.exe en el servicio.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo ejecutar SvcUtil.exe, vea [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  Utilice el archivo generado en lugar del archivo de configuración en el ejemplo.  El archivo de configuración generado tiene información de identidad adicional y contiene todos los valores necesarios para conectarse al extremo de servicio, aunque se trate de la configuración predeterminada.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] sobre la información de identidad, vea [Identidad del servicio y autenticación](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md) y [\<identidad\>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md).  
  
4.  En el equipo cliente, inicie Client.exe desde el símbolo del sistema.  
  
### Para depurar un servicio  
  
1.  Compile la solución \(cliente y servicio\) mediante el menú **Compilar** o CTRL\+SHIFT\+B.  
  
2.  Si el servicio se hospeda en IIS:  
  
    1.  Active el servicio en un explorador utilizando la dirección http:\/\/localhost\/servicemodelsamples\/service.svc.  
  
    2.  En la solución, elija el menú **Depurar** y el elemento de menú **Asociar al proceso**.  
  
    3.  Active la casilla **Mostrar los procesos de todos los usuarios**.  
  
    4.  Seleccione el proceso de trabajador host W3wp.exe para depurar \(seleccione ASPNet\_wp.exe en Windows XP\).  
  
3.  Ahora puede establecer puntos de interrupción en el código del servicio y habilitar puntos de interrupción en excepciones.  
  
4.  Haga clic con el botón derecho en el elemento de proyecto del cliente y elija **Depurar**, **Iniciar nueva instancia**.  
  
### Para realizar una limpieza después de ejecutar el ejemplo  
  
-   Si el servicio se hospeda en IIS por razones de seguridad, quite la definición del directorio virtual y los permisos concedidos en los pasos de instalación cuando acabe con los ejemplos.  
  
## Vea también  
 [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md)   
 [Running the Samples in a Workgroup and Across Machines](http://msdn.microsoft.com/es-es/a451a525-e7ce-452d-9da9-620221260113)   
 [Troubleshooting Tips](http://msdn.microsoft.com/es-es/8787c877-5e96-42da-8214-fa737a38f10b)
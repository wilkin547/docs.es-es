---
title: "C&#243;mo instalar y configurar los componentes de activaci&#243;n de WFC | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "activación HTTP [WCF]"
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# C&#243;mo instalar y configurar los componentes de activaci&#243;n de WFC
En este tema se describen los pasos necesarios para configurar Windows Process Activation Service \(también conocido como WAS\) en [!INCLUDE[wv](../../../../includes/wv-md.md)] para hospedar servicios de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] que no se comunican sobre protocolos de red HTTP.Las siguientes secciones describen los pasos para realizar esta configuración:  
  
-   Instale \(o confirme la instalación de\) los componentes de activación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   Configure WAS para que admita un protocolo que no sea HTTP.El procedimiento siguiente configura [!INCLUDE[wv](../../../../includes/wv-md.md)] para la activación del TCP.  
  
 Después de instalar y configurar WAS, vea [Procedimiento para hospedar un servicio WCF en WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) para que los procedimientos creen un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que exponga un extremo que no sea HTTP que emplee WAS.  
  
### Instalación de los componentes de activación que no son HTTP de WCF  
  
1.  Haga clic en el botón **Inicio**y, a continuación, haga clic en **Panel de control**.  
  
2.  Haga clic en **Programas**y, a continuación, haga clic en **Programas y características**.  
  
3.  En el menú **Tareas**, haga clic en **Activar o desactivar las características de Windows**.  
  
4.  Encuentre el nodo [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], selecciónelo y, a continuación, expándalo.  
  
5.  Seleccione la casilla **Componentes de activación no HTTP de WCF** y guarde el valor.  
  
### Configuración de WAS para admitir la activación TCP  
  
1.  Para admitir la activación del net.tcp, el sitio web predeterminado debe enlazarse primero a un puerto net.tcp.Puede hacer esto utilizando Appcmd.exe, que está instalado con el conjunto de herramientas de administración [!INCLUDE[iisver](../../../../includes/iisver-md.md)].En una ventana de símbolo de sistema para administradores, ejecute el siguiente comando.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Este comando es una línea de texto única.Este comando agrega un enlace del sitio net.tcp al sitio web predeterminado que realiza escuchas en el puerto TCP 808 con cualquier nombre de host.  
  
2.  Aunque todas las aplicaciones dentro de un sitio comparten un enlace net. tcp común, cada aplicación puede habilitar la compatibilidad net. tcp individualmente.Para habilitar net.tcp para la aplicación, ejecute el siguiente comando desde un símbolo del sistema del nivel del administrador:  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  Este comando es una sola línea de texto.Este comando permite tener acceso a la aplicación \/\<*WCF Application*\> usando http:\/\/localhost\/*\/\<WCF Application\>* y net.tcp:\/\/localhost \/*\<WCF Application\>*.  
  
     Quite el enlace de sitio net.tcp que agregó para este ejemplo.  
  
     Para su comodidad, los dos pasos siguientes se implementan en un archivo de información llamado RemoveNetTcpSiteBinding.cmd localizado en el directorio de ejemplo.  
  
    1.  Quite el net.tcp de la lista de protocolos habilitados ejecutando el comando siguiente en una ventana de símbolo del sistema del nivel del administrador:  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  Este comando es una línea de texto única.  
  
    2.  Quite el enlace del sitio net.tcp ejecutando el siguiente comando desde una ventana de símbolo del sistema elevado:  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  Este comando es una línea de texto única.  
  
### Quitar el net.tcp de la lista de protocolos habilitados  
  
1.  Para quitar el net.tcp de la lista de protocolos habilitados, ejecute el siguiente comando en una ventana de símbolo del sistema del nivel del administrador:  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  Este comando es una línea de texto única.  
  
### Quitar el enlace de sitio de net.tcp  
  
1.  Para quitar el enlace del sitio net.tcp ejecute el siguiente comando desde una ventana de símbolo del sistema en el nivel de administrador:  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Este comando es una sola línea de texto.  
  
## Vea también  
 [Activación TCP](../../../../docs/framework/wcf/samples/tcp-activation.md)   
 [Activación MSMQ](../../../../docs/framework/wcf/samples/msmq-activation.md)   
 [Activación NamedPipe](../../../../docs/framework/wcf/samples/namedpipe-activation.md)   
 [Características de hospedaje de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
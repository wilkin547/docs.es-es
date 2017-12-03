---
title: "Cómo instalar y configurar los componentes de activación de WFC"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ee57276efda7edcc464c300e2f1d100b6a7c9109
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a>Cómo instalar y configurar los componentes de activación de WFC
En este tema se describen los pasos necesarios para configurar Windows Process Activation Service (también conocido como WAS) en [!INCLUDE[wv](../../../../includes/wv-md.md)] para hospedar servicios de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] que no se comunican sobre protocolos de red HTTP. Las siguientes secciones describen los pasos para realizar esta configuración:  
  
-   Instale (o confirme la instalación de) los componentes de activación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   Configure WAS para que admita un protocolo que no sea HTTP. El procedimiento siguiente configura [!INCLUDE[wv](../../../../includes/wv-md.md)] para la activación del TCP.  
  
 Después de instalar y configurar el servicio WAS, vea [Cómo: hospedar un servicio WCF en WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) para los procedimientos crear un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicio que expone un punto de conexión distintos de HTTP que utiliza el servicio WAS.  
  
### <a name="to-install-the-wcf-non-http-activation-components"></a>Instalación de los componentes de activación que no son HTTP de WCF  
  
1.  Haga clic en el **iniciar** botón y, a continuación, haga clic en **el Panel de Control**.  
  
2.  Haga clic en **programas**y, a continuación, haga clic en **programas y características**.  
  
3.  En el **tareas** menú, haga clic en **o desactivar las características de Windows Active**.  
  
4.  Encuentre el nodo [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], selecciónelo y, a continuación, expándalo.  
  
5.  Seleccione el **componentes de activación no Http de WCF** cuadro y guardar la configuración.  
  
### <a name="to-configure-the-was-to-support-tcp-activation"></a>Configuración de WAS para admitir la activación TCP  
  
1.  Para admitir la activación del net.tcp, el sitio web predeterminado debe enlazarse primero a un puerto net.tcp. Puede hacer esto utilizando Appcmd.exe, que está instalado con el conjunto de herramientas de administración [!INCLUDE[iisver](../../../../includes/iisver-md.md)]. En una ventana de símbolo de sistema para administradores, ejecute el siguiente comando.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Este comando es una sola línea de texto. Este comando agrega un enlace del sitio net.tcp al sitio web predeterminado que realiza escuchas en el puerto TCP 808 con cualquier nombre de host.  
  
2.  Aunque todas las aplicaciones dentro de un sitio comparten un enlace net. tcp común, cada aplicación puede habilitar la compatibilidad net. tcp individualmente. Para habilitar net.tcp para la aplicación, ejecute el siguiente comando desde un símbolo del sistema del nivel del administrador:  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  Este comando es una sola línea de texto. Este comando habilita la /\<*aplicación WCF*> aplicación para tener acceso utilizando ambos http://localhost*/\<aplicación WCF >* y net.tcp:// localhost /*\<aplicación WCF >*.  
  
     Elimine el enlace del sitio de net.tcp que ha agregado para este ejemplo.  
  
     Para su comodidad, los dos pasos siguientes se implementan en un archivo de información llamado RemoveNetTcpSiteBinding.cmd localizado en el directorio de ejemplo.  
  
    1.  Quite el net.tcp de la lista de protocolos habilitados ejecutando el comando siguiente en una ventana de símbolo del sistema del nivel del administrador:  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  Este comando es una sola línea de texto.  
  
    2.  Quite el enlace del sitio net.tcp ejecutando el siguiente comando desde una ventana de símbolo del sistema elevado:  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  Este comando es una sola línea de texto.  
  
### <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a>Quitar el net.tcp de la lista de protocolos habilitados  
  
1.  Para quitar el net.tcp de la lista de protocolos habilitados, ejecute el siguiente comando en una ventana de símbolo del sistema del nivel del administrador:  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  Este comando es una sola línea de texto.  
  
### <a name="to-remove-the-nettcp-site-binding"></a>Quitar el enlace de sitio de net.tcp  
  
1.  Para quitar el enlace del sitio net.tcp ejecute el siguiente comando desde una ventana de símbolo del sistema en el nivel de administrador:  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Este comando es una sola línea de texto.  
  
## <a name="see-also"></a>Vea también  
 [Activación de TCP](../../../../docs/framework/wcf/samples/tcp-activation.md)  
 [Activación de MSMQ](../../../../docs/framework/wcf/samples/msmq-activation.md)  
 [Activación de canalización con nombre](../../../../docs/framework/wcf/samples/namedpipe-activation.md)  
 [Características de hospedaje de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)

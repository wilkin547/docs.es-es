---
title: "Instrucciones de instalaci&#243;n del certificado de servidor de Internet Information Services (IIS) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Instrucciones de instalaci&#243;n del certificado de servidor de Internet Information Services (IIS)
Para ejecutar los ejemplos que se comunican de forma segura con Internet Information Services \(IIS\), debe crear e instalar un certificado de servidor.  
  
## Paso 1.Crear certificados  
 Para crear un certificado para su equipo, abra un símbolo del sistema de Visual Studio con privilegios de administrador y ejecute el archivo Setup.bat que se incluye en cada uno de los ejemplos que utilizan la comunicación segura con IIS.Asegúrese de que la ruta de acceso incluye la carpeta que contiene makecert.exe antes de ejecutar este archivo por lotes.El siguiente comando se utiliza para crear el certificado en Setup.bat.  
  
```  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## Paso 2.Instalar certificados  
 Los pasos requeridos para instalar los certificados recién creados dependen de la versión de IIS que use.  
  
#### Para instalar IIS en IIS 5.1 \(Windows XP\) e IIS 6.0 \(Windows Server 2003\)  
  
1.  Abra el complemento MMC del administrador de Internet Information Services.  
  
2.  Haga clic con el botón secundario del mouse en el sitio web predeterminado y seleccione **Propiedades**.  
  
3.  Seleccione la pestaña **Seguridad de directorios**.  
  
4.  Haga clic en el botón **Certificado de servidor**.Se inicia el Asistente para certificados de servidor web.  
  
5.  Complete el asistente.Seleccione la opción para asignar un certificado.Seleccione el certificado ServiceModelSamples\-HTTPS\-Server de la lista de certificados que se muestran.  
  
     ![Asistente para certificados IIS](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate\_Wizard")  
  
6.  Pruebe el acceso al servicio en un explorador utilizando la dirección HTTPS https:\/\/localhost\/servicemodelsamples\/service.svc.  
  
#### Si SSL se configuró previamente utilizando httpcfg.exe  
  
1.  Utilice makecert.exe \(o ejecute setup.bat\) para crear el certificado de servidor.  
  
2.  Ejecute el Administrador de IIS e instale el certificado según los pasos anteriores.  
  
3.  Agregue la línea siguiente de código al programa cliente:  
  
> [!IMPORTANT]
>  Este código solo se requiere para los certificados de prueba como los creados por makecert.exe.No se recomienda para el código de producción.  
  
```  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### Para instalar IIS en IIS 7.0 \(Windows Vista y Windows Server 2008\)  
  
1.  En el menú **Inicio**, haga clic en **Ejecutar** y escriba **inetmgr** para abrir el complemento MMC de Internet Information Services \(IIS\).  
  
2.  Haga clic con el botón secundario en el **Sitio web predeterminado** y seleccione **Editar enlaces...**.  
  
3.  Haga clic en el botón **Agregar** del cuadro de diálogo **Enlaces de sitio**.  
  
4.  Seleccione **HTTPS** en la lista desplegable **Tipo**.  
  
5.  Seleccione **ServiceModelSamples\-HTTPS\-Server** en la lista desplegable **Certificado SSL** y haga clic en **Aceptar**.  
  
6.  Pruebe el acceso al servicio en un explorador utilizando la dirección HTTPS https:\/\/localhost\/servicemodelsamples\/service.svc.  
  
> [!NOTE]
>  Dado que el certificado de prueba que acaba de instalar no es un certificado de confianza, puede encontrar advertencias de seguridad de Internet Explorer adicionales al ir a las direcciones web locales protegidas con este certificado.  
  
## Quitar Certificados  
  
-   Utilice el Administrador de Internet Information Services según las instrucciones anteriores, pero quite el certificado o enlace en lugar de agregarlo.  
  
-   Quite el certificado de equipo utilizando el comando siguiente.  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```
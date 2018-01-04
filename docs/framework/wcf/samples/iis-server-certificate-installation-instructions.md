---
title: "Instrucciones de instalación del certificado de servidor de Internet Information Services (IIS)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cfb168ae60765a57017aaec6bdedaf796491f602
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a>Instrucciones de instalación del certificado de servidor de Internet Information Services (IIS)
Para ejecutar los ejemplos que se comunican de forma segura con Internet Information Services (IIS), debe crear e instalar un certificado de servidor.  
  
## <a name="step-1-creating-certificates"></a>Paso 1. Crear certificados  
 Para crear un certificado para su equipo, abra un símbolo del sistema de Visual Studio con privilegios de administrador y ejecute el archivo Setup.bat que se incluye en cada uno de los ejemplos que utilizan la comunicación segura con IIS. Asegúrese de que la ruta de acceso incluye la carpeta que contiene makecert.exe antes de ejecutar este archivo por lotes. El siguiente comando se utiliza para crear el certificado en Setup.bat.  
  
```  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a>Paso 2. Instalar certificados  
 Los pasos requeridos para instalar los certificados que acaba de crear dependen de la versión de IIS que está utilizando.  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a>Para instalar IIS en IIS 5.1 (Windows XP) e IIS 6.0 (Windows Server 2003)  
  
1.  Abra el complemento MMC del administrador de Internet Information Services.  
  
2.  Haga clic en el sitio Web predeterminado y seleccione **propiedades**.  
  
3.  Seleccione el **seguridad de directorios** ficha.  
  
4.  Haga clic en el **certificado de servidor** botón. Se inicia el Asistente para certificados de servidor web.  
  
5.  Complete el asistente. Seleccione la opción para asignar un certificado. Seleccione el certificado ServiceModelSamples-HTTPS-Server de la lista de certificados que se muestran.  
  
     ![Asistente para certificados IIS](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")  
  
6.  Pruebe el acceso al servicio en un explorador utilizando la dirección HTTPS https://localhost/servicemodelsamples/service.svc.  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a>Si SSL se configuró previamente utilizando httpcfg.exe  
  
1.  Utilice makecert.exe (o ejecute setup.bat) para crear el certificado de servidor.  
  
2.  Ejecute el Administrador de IIS e instale el certificado según los pasos anteriores.  
  
3.  Agregue la línea siguiente de código al programa cliente:  
  
> [!IMPORTANT]
>  Este código solo se requiere para los certificados de prueba como los creados por makecert.exe. No se recomienda para el código de producción.  
  
```  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a>Para instalar IIS en IIS 7.0 (Windows Vista y Windows Server 2008)  
  
1.  Desde el **iniciar** menú, haga clic en **ejecutar**, a continuación, escriba **inetmgr** para abrir el complemento MMC de servicios de Internet Information Server (IIS).  
  
2.  Haga clic en el **sitio Web predeterminado** y seleccione **modificar enlaces...**  
  
3.  Haga clic en el **agregar** botón de la **enlaces de sitios** cuadro de diálogo.  
  
4.  Seleccione **HTTPS** desde el **tipo** lista desplegable.  
  
5.  Seleccione el **ServiceModelSamples-HTTPS-Server** desde el **certificado SSL** lista desplegable y haga clic en **Aceptar**.  
  
6.  Pruebe el acceso al servicio en un explorador utilizando la dirección HTTPS https://localhost/servicemodelsamples/service.svc.  
  
> [!NOTE]
>  Dado que el certificado de prueba que acaba de instalar no es un certificado de confianza, puede encontrar advertencias de seguridad de Internet Explorer adicionales al ir a las direcciones web locales protegidas con este certificado.  
  
## <a name="removing-certificates"></a>Quitar Certificados  
  
-   Utilice el Administrador de Internet Information Services según las instrucciones anteriores, pero quite el certificado o enlace en lugar de agregarlo.  
  
-   Quite el certificado de equipo utilizando el comando siguiente.  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```

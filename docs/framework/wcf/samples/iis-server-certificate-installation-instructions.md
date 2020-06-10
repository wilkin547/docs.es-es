---
title: Instrucciones de instalación del certificado de servidor de Internet Information Services (IIS)
ms.date: 03/30/2017
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
ms.openlocfilehash: 301a10c615a13a42e1a6e1b89d2724476ca4fbae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594665"
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a>Instrucciones de instalación del certificado de servidor de Internet Information Services (IIS)
Para ejecutar los ejemplos que se comunican de forma segura con Internet Information Services (IIS), debe crear e instalar un certificado de servidor.  
  
## <a name="step-1-creating-certificates"></a>Paso 1. Crear certificados  
 Para crear un certificado para el equipo, abra una Símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador y ejecute el archivo Setup. bat que se incluye en cada uno de los ejemplos que utilizan la comunicación segura con IIS. Asegúrese de que la ruta de acceso incluye la carpeta que contiene makecert.exe antes de ejecutar este archivo por lotes. El siguiente comando se utiliza para crear el certificado en Setup.bat.  
  
```console  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a>Paso 2. Instalar certificados  
 Los pasos requeridos para instalar los certificados que acaba de crear dependen de la versión de IIS que está utilizando.  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a>Para instalar IIS en IIS 5.1 (Windows XP) e IIS 6.0 (Windows Server 2003)  
  
1. Abra el complemento MMC del administrador de Internet Information Services.  
  
2. Haga clic con el botón secundario en el sitio web predeterminado y seleccione **propiedades**.  
  
3. Seleccione la pestaña **seguridad de directorios** .  
  
4. Haga clic en el botón **certificado de servidor** . Se inicia el Asistente para certificados de servidor web.  
  
5. Complete el asistente. Seleccione la opción para asignar un certificado. Seleccione el certificado ServiceModelSamples-HTTPS-Server de la lista de certificados que se muestran.  
  
     ![Asistente de certificado IIS](media/iiscertificate-wizard.GIF "IISCertificate_Wizard")  
  
6. Pruebe el acceso al servicio en un explorador mediante la dirección HTTPS `https://localhost/servicemodelsamples/service.svc` .  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a>Si SSL se configuró previamente utilizando httpcfg.exe  
  
1. Utilice makecert.exe (o ejecute setup.bat) para crear el certificado de servidor.  
  
2. Ejecute el Administrador de IIS e instale el certificado según los pasos anteriores.  
  
3. Agregue la línea siguiente de código al programa cliente:  
  
> [!IMPORTANT]
> Este código solo se requiere para los certificados de prueba como los creados por makecert.exe. No se recomienda para el código de producción.  
  
```csharp  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a>Para instalar IIS en IIS 7.0 (Windows Vista y Windows Server 2008)  
  
1. En el menú **Inicio** , haga clic en **Ejecutar**y, a continuación, escriba **inetmgr** para abrir el complemento MMC de Internet Information Services (IIS).  
  
2. Haga clic con el botón secundario en el **sitio web predeterminado** y seleccione **Editar enlaces..** .  
  
3. Haga clic en el botón **Agregar** del cuadro de diálogo **enlaces de sitios** .  
  
4. Seleccione **https** en la lista desplegable **tipo** .  
  
5. Seleccione **ServiceModelSamples-https-Server** en la lista desplegable **certificado SSL** y haga clic en **Aceptar**.  
  
6. Pruebe el acceso al servicio en un explorador mediante la dirección HTTPS `https://localhost/servicemodelsamples/service.svc` .  
  
> [!NOTE]
> Dado que el certificado de prueba que acaba de instalar no es un certificado de confianza, puede encontrar advertencias de seguridad de Internet Explorer adicionales al ir a las direcciones web locales protegidas con este certificado.  
  
## <a name="removing-certificates"></a>Quitar Certificados  
  
- Utilice el Administrador de Internet Information Services según las instrucciones anteriores, pero quite el certificado o enlace en lugar de agregarlo.  
  
- Quite el certificado de equipo utilizando el comando siguiente.  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```

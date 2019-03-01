---
title: Procedimiento Ver certificados con el complemento de MMC
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 6ec86ffca9ae84a9c3276a3dd6de676919dcd2e0
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200291"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>Filtrar Ver certificados con el complemento de MMC
Cuando se crea un cliente segura o el servicio, puede usar un [certificado](working-with-certificates.md) como la credencial. Por ejemplo, un tipo común de credencial es el certificado X.509, que se crea con el <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> método. 

Hay tres tipos diferentes de almacenes de certificados que se pueden examinar con Microsoft Management Console (MMC) en los sistemas de Windows:

- Equipo local: El almacén es local en el dispositivo y global para todos los usuarios en el dispositivo.

- Usuario actual: El almacén es local para la cuenta de usuario actual en el dispositivo.

- Cuenta de servicio: El almacén es un servicio determinado en el dispositivo local.

  
## <a name="view-certificates-in-the-mmc-snap-in"></a>Ver los certificados en el complemento MMC 

El siguiente procedimiento muestra cómo examinar los almacenes en el dispositivo local para buscar un certificado adecuado: 
  
1. Seleccione **ejecutar** desde el **iniciar** menú y, a continuación, escriba *mmc*. 

    Aparece la consola MMC. 
  
2. Desde el **archivo** menú, seleccione **agregar o quitar complemento**. 
    
    El **agregar o quitar complementos** aparecerá la ventana.
  
3. Desde el **complementos disponibles** elija **certificados**, a continuación, seleccione **agregar**.  

    ![Agregar complemento de certificado](./media/mmc-add-certificate-snap-in.png)
  
4. En el **complemento certificados** ventana, seleccione **cuenta de equipo**y, a continuación, seleccione **siguiente**. 
  
    Si lo desea, puede seleccionar **mi cuenta de usuario** para el usuario actual o **cuenta de servicio** para un servicio determinado. 

    > [!NOTE]
    > Si no es un administrador para el dispositivo, puede administrar los certificados sólo para su cuenta de usuario.
  
5. En el **Seleccionar equipo** ventana, deje **ordenador** seleccionado y, a continuación, seleccione **finalizar**.  
  
6. En el **agregar o quitar complemento** ventana, seleccione **Aceptar**.  
  
    ![Agregar complemento de certificado](./media/mmc-certificate-snap-in-selected.png)

7. Opcional: Desde el **archivo** menú, seleccione **guardar** o **Guardar como** para guardar el archivo de consola MMC para su uso posterior.  

8. Para ver los certificados en el complemento de MMC, seleccione **raíz de consola** en el panel izquierdo, expanda **certificados (equipo Local)**.

    Aparece una lista de directorios para cada tipo de certificado. En cada directorio de certificado, puede ver, exportar, importar y eliminar sus certificados.
  

## <a name="view-certificates-with-the-certificate-manager-tool"></a>Ver certificados con la herramienta Administrador de certificados

También puede ver, exportar, importar y eliminar certificados utilizando la herramienta Administrador de certificados.

### <a name="to-view-certificates-for-the-local-device"></a>Para ver los certificados para el dispositivo local

1. Seleccione **ejecutar** desde el **iniciar** menú y, a continuación, escriba *certlm.msc*. 

    Aparece la herramienta Administrador de certificados para el dispositivo local. 
  
2. Para ver los certificados, en **certificados - equipo Local** en el panel izquierdo, expanda el directorio para el tipo de certificado que desea ver.

### <a name="to-view-certificates-for-the-current-user"></a>Para ver los certificados del usuario actual

1. Seleccione **ejecutar** desde el **iniciar** menú y, a continuación, escriba *certmgr.msc*. 

    Aparece la herramienta Administrador de certificados para el usuario actual. 
  
2. Para ver los certificados, en **certificados - usuario actual** en el panel izquierdo, expanda el directorio para el tipo de certificado que desea ver.

  
## <a name="see-also"></a>Vea también
- [Trabajar con certificados](working-with-certificates.md)
- [Cómo: Crear certificados temporales para su uso durante el desarrollo](how-to-create-temporary-certificates-for-use-during-development.md)
- [Cómo: Recuperar la huella digital de un certificado](how-to-retrieve-the-thumbprint-of-a-certificate.md)

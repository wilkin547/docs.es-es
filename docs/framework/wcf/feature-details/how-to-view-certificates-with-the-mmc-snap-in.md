---
title: 'Cómo: Ver certificados con el complemento MMC'
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 35048c24e838c513909fae8bedcba287001f5cef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184780"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>Cómo: Ver certificados con el complemento MMC
Al crear un cliente o servicio seguro, puede usar un [certificado](working-with-certificates.md) como credencial. Por ejemplo, un tipo común de credencial es el certificado X.509, que se crea con el <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> método.

Hay tres tipos diferentes de almacenes de certificados que puede examinar con Microsoft Management Console (MMC) en sistemas Windows:

- Equipo local: la tienda es local para el dispositivo y global para todos los usuarios del dispositivo.

- Usuario actual: el almacén es local para la cuenta de usuario actual en el dispositivo.

- Cuenta de servicio: la tienda es local a un servicio determinado en el dispositivo.

## <a name="view-certificates-in-the-mmc-snap-in"></a>Ver certificados en el complemento MMC

El siguiente procedimiento muestra cómo examinar los almacenes del dispositivo local para encontrar un certificado adecuado:
  
1. Seleccione **Ejecutar en** el menú **Inicio** y, a continuación, escriba *mmc*.

    Aparece el MMC.
  
2. En el menú **Archivo,** seleccione **Agregar o quitar forzado de cursor**.

    Aparecerá la ventana **Agregar o quitar complementos.**
  
3. En la lista **Complementos disponibles,** elija **Certificados**y, a continuación, seleccione **Agregar**.  

    ![Agregar complemento de certificado](./media/mmc-add-certificate-snap-in.png)
  
4. En la ventana **Complemento Certificados,** seleccione **Cuenta de**equipo y, a continuación, seleccione **Siguiente**.
  
    Opcionalmente, puede seleccionar **Mi cuenta** de usuario para el usuario actual o la cuenta de **servicio** para un servicio determinado.

    > [!NOTE]
    > Si no eres administrador de tu dispositivo, puedes administrar certificados solo para tu cuenta de usuario.
  
5. En la ventana **Seleccionar equipo,** deje seleccionado **Equipo local** y, a continuación, seleccione **Finalizar**.  
  
6. En la ventana **Agregar o quitar complemento,** seleccione **Aceptar**.  
  
    ![Agregar complemento de certificado](./media/mmc-certificate-snap-in-selected.png)

7. Opcional: en el menú **Archivo,** seleccione **Guardar** o **Guardar como** para guardar el archivo de consola de MMC para su uso posterior.  

8. Para ver los certificados en el complemento MMC, seleccione Raíz de **consola** en el panel izquierdo y, a continuación, expanda **Certificados (equipo local).**

    Aparece una lista de directorios para cada tipo de certificado. Desde cada directorio de certificados, puede ver, exportar, importar y eliminar sus certificados.

## <a name="view-certificates-with-the-certificate-manager-tool"></a>Ver certificados con la herramienta Administrador de certificados

También puede ver, exportar, importar y eliminar certificados mediante la herramienta Administrador de certificados.

### <a name="to-view-certificates-for-the-local-device"></a>Para ver los certificados del dispositivo local

1. Seleccione **Ejecutar en** el menú **Inicio** y, a continuación, escriba *certlm.msc*.

    Aparece la herramienta Administrador de certificados para el dispositivo local.
  
2. Para ver los certificados, en **Certificados - Equipo local** en el panel izquierdo, expanda el directorio del tipo de certificado que desea ver.

### <a name="to-view-certificates-for-the-current-user"></a>Para ver los certificados del usuario actual

1. Seleccione **Ejecutar en** el menú **Inicio** y, a continuación, escriba *certmgr.msc*.

    Aparece la herramienta Administrador de certificados para el usuario actual.
  
2. Para ver los certificados, en **Certificados - Usuario actual** en el panel izquierdo, expanda el directorio del tipo de certificado que desea ver.

## <a name="see-also"></a>Consulte también

- [Trabajar con certificados](working-with-certificates.md)
- [Cómo: Crear certificados temporales para su uso durante el desarrollo](how-to-create-temporary-certificates-for-use-during-development.md)
- [Cómo: Recuperar la huella digital de un certificado](how-to-retrieve-the-thumbprint-of-a-certificate.md)

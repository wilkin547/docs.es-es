---
title: 'Cómo: ver certificados con el complemento MMC'
description: Un cliente o servicio de WCF seguro puede usar un certificado como credencial. Obtenga información acerca de los tipos de almacenes de certificados que puede examinar mediante el complemento MMC.
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: e63034e48ae836f67f89b454829f7196c94610cd
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246680"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>Cómo: ver certificados con el complemento MMC
Al crear un cliente o servicio seguro, puede usar un [certificado](working-with-certificates.md) como credencial. Por ejemplo, un tipo común de credencial es el certificado X. 509, que se crea con el <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> método.

Existen tres tipos diferentes de almacenes de certificados que se pueden examinar con Microsoft Management Console (MMC) en los sistemas de Windows:

- Equipo local: el almacén es local para el dispositivo y es global para todos los usuarios del dispositivo.

- Usuario actual: el almacén es local para la cuenta de usuario actual en el dispositivo.

- Cuenta de servicio: el almacén es local para un servicio determinado en el dispositivo.

## <a name="view-certificates-in-the-mmc-snap-in"></a>Ver certificados en el complemento MMC

El siguiente procedimiento muestra cómo examinar los almacenes en el dispositivo local para encontrar un certificado adecuado:
  
1. Seleccione **Ejecutar** en el menú **Inicio** y escriba *MMC*.

    Aparece MMC.
  
2. En el menú **archivo** , seleccione **Agregar o quitar complemento**.

    Aparece la ventana **Agregar o quitar complementos** .
  
3. En la lista **complementos disponibles** , seleccione **certificados**y, a continuación, seleccione **Agregar**.  

    ![Agregar complemento de certificado](./media/mmc-add-certificate-snap-in.png)
  
4. En la ventana del **complemento certificados** , seleccione **cuenta de equipo**y, a continuación, seleccione **siguiente**.
  
    Opcionalmente, puede seleccionar **mi cuenta de usuario** para el usuario actual o la **cuenta de servicio** para un servicio determinado.

    > [!NOTE]
    > Si no es administrador de su dispositivo, puede administrar certificados solo para su cuenta de usuario.
  
5. En la ventana **seleccionar equipo** , deje seleccionado **equipo local** y, a continuación, seleccione **Finalizar**.  
  
6. En la ventana **Agregar o quitar complemento** , seleccione **Aceptar**.  
  
    ![Agregar complemento de certificado](./media/mmc-certificate-snap-in-selected.png)

7. Opcional: en el menú **archivo** , seleccione **Guardar** o **Guardar como** para guardar el archivo de consola MMC para su uso posterior.  

8. Para ver los certificados en el complemento MMC, seleccione raíz de **consola** en el panel izquierdo y, a continuación, expanda **certificados (equipo local)**.

    Aparece una lista de directorios para cada tipo de certificado. En cada directorio de certificados, puede ver, exportar, importar y eliminar sus certificados.

## <a name="view-certificates-with-the-certificate-manager-tool"></a>Ver certificados con la herramienta Administrador de certificados

También puede ver, exportar, importar y eliminar certificados mediante la herramienta Administrador de certificados.

### <a name="to-view-certificates-for-the-local-device"></a>Para ver los certificados del dispositivo local

1. Seleccione **Ejecutar** en el menú **Inicio** y, a continuación, escriba *certlm. msc*.

    Aparece la herramienta Administrador de certificados para el dispositivo local.
  
2. Para ver los certificados, en **certificados: equipo local** en el panel izquierdo, expanda el directorio del tipo de certificado que desea ver.

### <a name="to-view-certificates-for-the-current-user"></a>Para ver los certificados del usuario actual

1. Seleccione **Ejecutar** en el menú **Inicio** y, a continuación, escriba *certmgr.msc*.

    Aparece la herramienta Administrador de certificados para el usuario actual.
  
2. Para ver los certificados, en **certificados: usuario actual** en el panel izquierdo, expanda el directorio del tipo de certificado que desea ver.

## <a name="see-also"></a>Vea también

- [Trabajar con certificados](working-with-certificates.md)
- [Cómo: crear certificados temporales para su uso durante el desarrollo](how-to-create-temporary-certificates-for-use-during-development.md)
- [Cómo: recuperar la huella digital de un certificado](how-to-retrieve-the-thumbprint-of-a-certificate.md)

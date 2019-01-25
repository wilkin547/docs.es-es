---
title: Procedimiento Ver certificados con el complemento de MMC
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 72fd6a1be2f33e1bfeb08fd43f3436627ee842e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521587"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>Procedimiento Ver certificados con el complemento de MMC
Un tipo común de credencial es el certificado X.509. Al crear servicios o clientes seguros, puede especificar que un certificado se utilice como la credencial del cliente o servicio utilizando métodos como el método <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>. El método requiere varios parámetros, como el almacén donde se guarda el certificado y un valor que utilizar al buscar el certificado. El siguiente procedimiento muestra cómo examinar los almacenes de un equipo para encontrar un certificado adecuado. Para obtener un ejemplo de encontrar la huella digital del certificado, consulte [Cómo: Recuperar la huella digital de un certificado](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
### <a name="to-view-certificates-in-the-mmc-snap-in"></a>Para ver los certificados en el complemento de MMC  
  
1.  Abra una ventana de símbolo del sistema.  
  
2.  Tipo `mmc` y presione la tecla ENTRAR. Tenga en cuenta que para ver los certificados en el almacén del equipo local, debe estar en la función del Administrador.  
  
3.  En el **archivo** menú, haga clic en **agregar o quitar complemento**.  
  
4.  Haga clic en **Agregar**.  
  
5.  En el **Add Standalone Snap-in** cuadro de diálogo, seleccione **certificados**.  
  
6.  Haga clic en **Agregar**.  
  
7.  En el **complemento certificados** cuadro de diálogo, seleccione **cuenta de equipo** y haga clic en **siguiente**. Si lo desea, puede seleccionar **mi cuenta de usuario** o **cuenta de servicio**. Si no es ningún administrador del equipo, solo puede administrar los certificados para su cuenta de usuario.  
  
8.  En el **Seleccionar equipo** cuadro de diálogo, haga clic en **finalizar**.  
  
9. En el **Add Standalone Snap-in** cuadro de diálogo, haga clic en **cerrar**.  
  
10. En el **agregar o quitar complemento** cuadro de diálogo, haga clic en **Aceptar**.  
  
11. En el **raíz de consola** ventana, haga clic en **certificados (equipo Local)** para ver el certificado se almacena para el equipo.  
  
12. Opcional. Para ver los certificados para su cuenta, repita los pasos 3 a 6. En el paso 7, en lugar de seleccionar **cuenta de equipo**, haga clic en **mi cuenta de usuario** y repita los pasos del 8 al 10.  
  
13. Opcional. En el **archivo** menú, haga clic en **guardar** o **Guardar como**. Guarde el archivo de consola para utilizarlo más adelante.  
  
## <a name="viewing-certificates-with-internet-explorer"></a>Ver certificados con Internet Explorer  
 También puede ver, exportar, importar y eliminar certificados utilizando Internet Explorer.  
  
#### <a name="to-view-certificates-with-internet-explorer"></a>Para ver certificados con Internet Explorer  
  
1.  En Internet Explorer, haga clic en **herramientas**, a continuación, haga clic en **opciones de Internet** para mostrar el **opciones de Internet** cuadro de diálogo.  
  
2.  Haga clic en el **contenido** ficha.  
  
3.  En **certificados**, haga clic en **certificados**.  
  
4.  Para ver los detalles de cualquier certificado, seleccione el certificado y haga clic en **vista**.  
  
## <a name="see-also"></a>Vea también
- [Trabajo con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Cómo: Crear certificados temporales para su uso durante el desarrollo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
- [Cómo: Recuperar la huella digital de un certificado](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)

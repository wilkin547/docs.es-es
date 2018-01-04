---
title: "Cómo: Ver certificados con el complemento de MMC"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 582eaef518e10acb4c4c356226ce0be24d1b4c35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>Cómo: Ver certificados con el complemento de MMC
Un tipo común de credencial es el certificado X.509. Al crear servicios o clientes seguros, puede especificar que un certificado se utilice como la credencial del cliente o servicio utilizando métodos como el método <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>. El método requiere varios parámetros, como el almacén donde se guarda el certificado y un valor que utilizar al buscar el certificado. El siguiente procedimiento muestra cómo examinar los almacenes de un equipo para encontrar un certificado adecuado. Para obtener un ejemplo de encontrar la huella digital del certificado, consulte [Cómo: recuperar la huella digital de un certificado](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
### <a name="to-view-certificates-in-the-mmc-snap-in"></a>Para ver los certificados en el complemento de MMC  
  
1.  Abra una ventana de símbolo del sistema.  
  
2.  Tipo `mmc` y presione la tecla ENTRAR. Tenga en cuenta que para ver los certificados en el almacén del equipo local, debe estar en la función del Administrador.  
  
3.  En el **archivo** menú, haga clic en **agregar/quitar complemento**.  
  
4.  Haga clic en **Agregar**.  
  
5.  En el **Add Standalone Snap-in** cuadro de diálogo, seleccione **certificados**.  
  
6.  Haga clic en **Agregar**.  
  
7.  En el **complemento certificados** cuadro de diálogo, seleccione **cuenta de equipo** y haga clic en **siguiente**. Si lo desea, puede seleccionar **mi cuenta de usuario** o **cuenta de servicio**. Si no es ningún administrador del equipo, solo puede administrar los certificados para su cuenta de usuario.  
  
8.  En el **Seleccionar equipo** cuadro de diálogo, haga clic en **finalizar**.  
  
9. En el **Add Standalone Snap-in** cuadro de diálogo, haga clic en **cerrar**.  
  
10. En el **agregar o quitar complemento** cuadro de diálogo, haga clic en **Aceptar**.  
  
11. En el **raíz de consola** ventana, haga clic en **certificados (equipo Local)** para ver el certificado se almacena en el equipo.  
  
12. Opcional. Para ver los certificados para su cuenta, repita los pasos 3 a 6. En el paso 7, en lugar de seleccionar **cuenta de equipo**, haga clic en **mi cuenta de usuario** y repita los pasos 8 a 10.  
  
13. Opcional. En el **archivo** menú, haga clic en **guardar** o **Guardar como**. Guarde el archivo de consola para utilizarlo más adelante.  
  
## <a name="viewing-certificates-with-internet-explorer"></a>Ver certificados con Internet Explorer  
 También puede ver, exportar, importar y eliminar certificados utilizando Internet Explorer.  
  
#### <a name="to-view-certificates-with-internet-explorer"></a>Para ver certificados con Internet Explorer  
  
1.  En Internet Explorer, haga clic en **herramientas**, a continuación, haga clic en **opciones de Internet** para mostrar la **opciones de Internet** cuadro de diálogo.  
  
2.  Haga clic en el **contenido** ficha.  
  
3.  En **certificados**, haga clic en **certificados**.  
  
4.  Para ver los detalles de un certificado, seleccione el certificado y haga clic en **vista**.  
  
## <a name="see-also"></a>Vea también  
 [Trabajo con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Creación de certificados temporales que puedan utilizarse durante las operaciones de desarrollo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)  
 [Recuperación de la huella digital de un certificado](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)

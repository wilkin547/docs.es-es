---
title: 'Cómo: Hacer los certificados X.509 accesibles para WCF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
ms.openlocfilehash: 0917569b556c31413b715d75c83a96f3a4b015d7
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192205"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a>Cómo: Hacer los certificados X.509 accesibles para WCF
Para hacer que un certificado X.509 accesible a Windows Communication Foundation (WCF), el código de la aplicación debe especificar el nombre del almacén de certificados y la ubicación. En ciertas circunstancias, la identidad del proceso debe tener el acceso al archivo que contiene la clave privada asociada al certificado X.509. Para obtener la clave privada asociada con un certificado X.509 en un almacén de certificados, WCF debe tener permiso para hacerlo. De forma predeterminada, solo el propietario y la cuenta del sistema pueden tener acceso a la clave privada de un certificado.  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a>Para hacer los certificados X.509 accesibles para WCF  
  
1.  Conceda a la cuenta en que WCF se ejecuta el acceso de lectura al archivo que contiene la clave privada asociada con el certificado X.509.  
  
    1.  Determinar si WCF requiere acceso de lectura a la clave privada del certificado X.509.  
  
         La tabla siguiente detalla si una clave privada debe estar disponible al utilizar un certificado X.509.  
  
        |Uso del certificado X.509|Clave privada|  
        |---------------------------|-----------------|  
        |Firmar digitalmente un mensaje SOAP saliente.|Sí|  
        |Comprobar la firma de un mensaje SOAP entrante.|No|  
        |Cifrar un mensaje SOAP saliente.|No|  
        |Descifrar un mensaje SOAP entrante.|Sí|  
  
    2.  Determine la ubicación del almacén de certificados y diga dónde está almacenado el certificado.  
  
         El almacén de certificados en el que el certificado está almacenado se especifica en código de aplicación o en configuración. Por ejemplo, el ejemplo siguiente especifica que el certificado se encuentra en el almacén de certificados `CurrentUser` denominado `My`.  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3.  Determinar dónde se encuentra la clave privada del certificado en el equipo mediante el uso de la [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) herramienta.  
  
         El [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) herramienta requiere el nombre del almacén de certificados, la ubicación del almacén de certificados y algo que singularmente identifique el certificado. La herramienta acepta el nombre de sujeto del certificado o su huella digital como identificador único. Para obtener más información acerca de cómo determinar la huella digital de un certificado, consulte [Cómo: recuperar la huella digital de un certificado](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
         El siguiente ejemplo de código utiliza el [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) herramienta para determinar la ubicación de la clave privada de un certificado en el `My` almacenar en `CurrentUser` con una huella digital de `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.  
  
        ```  
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4.  Determine la cuenta que WCF que se ejecuta.  
  
         La tabla siguiente detalla la cuenta bajo la que se ejecuta WCF para un escenario determinado.  
  
        |Escenario|Identidad de proceso|  
        |--------------|----------------------|  
        |Cliente (consola o aplicación WinForms).|Usuario actualmente registrado.|  
        |Servicio que tiene host propio.|Usuario actualmente registrado.|  
        |Servicio que se hospeda en IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) ó IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]).|NETWORK SERVICE|  
        |Servicio que se hospeda en IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]).|Controlado por el elemento `<processModel>` en el archivo Machine.config. La cuenta predeterminada es ASPNET.|  
  
    5.  Conceder acceso de lectura al archivo que contiene la clave privada a la cuenta que WCF se está ejecutando, mediante una herramienta como icacls.exe.  
  
         En el ejemplo de código siguiente se modifica la lista de control de acceso discrecional (DACL) para que el archivo especificado conceder la lectura de la cuenta de servicio de red (: R) el acceso al archivo.  
  
        ```  
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a>Vea también  
- [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)  
- [Recuperación de la huella digital de un certificado](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)  
- [Trabajo con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)

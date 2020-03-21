---
title: 'Cómo: Configurar un puerto con un certificado SSL'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
ms.openlocfilehash: 90d5424e12bb770dc3da85e1b2738206f4777c0c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185105"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a>Cómo: Configurar un puerto con un certificado SSL

Al crear un servicio autohospedado de Windows <xref:System.ServiceModel.WSHttpBinding> Communication Foundation (WCF) con la clase que usa seguridad de transporte, también debe configurar un puerto con un certificado X.509. Si no está creando un servicio autohospedado, puede hospedar su servicio en Servicios de Internet Information Server (IIS). Para obtener más información, consulte Seguridad de [transporte HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 La herramienta que se usa para configurar un puerto depende del sistema operativo que se esté ejecutando en el equipo.  
  
 Si está ejecutando Windows Server 2003, utilice la herramienta HttpCfg.exe. En Windows Server 2003, esta herramienta está instalada. Para obtener más información, consulte [Httpcfg Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)). La [documentación de Herramientas de soporte técnico](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) de Windows explica la sintaxis de la herramienta Httpcfg.exe.  
  
 Si está ejecutando Windows Vista, utilice la herramienta Netsh.exe que ya está instalada.
  
> [!NOTE]
> La modificación de certificados almacenados en el equipo requiere privilegios administrativos.  
  
## <a name="determine-how-ports-are-configured"></a>Determinar cómo se configuran los puertos  
  
1. En Windows Server 2003 o Windows XP, use la herramienta HttpCfg.exe para ver la configuración de puerto actual, utilizando **los** modificadores query y **ssl,** como se muestra en el ejemplo siguiente.  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. En Windows Vista, utilice la herramienta Netsh.exe para ver la configuración de puerto actual, como se muestra en el ejemplo siguiente.  
  
    ```console  
    netsh http show sslcert  
    ```  
  
## <a name="get-a-certificates-thumbprint"></a>Obtener la huella digital de un certificado  
  
1. Use el complemento de certificados de MMC para buscar un certificado X.509 que tenga como finalidad la autenticación del cliente. Para más información, consulte [Visualización de certificados con el complemento MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
2. Obtenga acceso a la huella digital del certificado. Para más información, consulte [Cómo recuperar la huella digital de un certificado](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
3. Copie la huella digital del certificado en un editor de texto, como por ejemplo Bloc de notas.  
  
4. Quite todos los espacios entre los caracteres hexadecimales. Una manera de llevarlo a cabo es utilizar la característica del editor de texto buscar y reemplazar y reemplazar todos los espacios con un carácter nulo.  
  
## <a name="bind-an-ssl-certificate-to-a-port-number"></a>Enlazar un certificado SSL a un número de puerto  
  
1. En Windows Server 2003 o Windows XP, use la herramienta HttpCfg.exe en modo "set" en el almacén SSL (Secure Sockets Layer) para enlazar el certificado a un número de puerto. La herramienta utiliza la huella digital para identificar el certificado, tal y como se muestra en el ejemplo siguiente.  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - El modificador **-i** tiene `IP``port` la sintaxis de : e indica a la herramienta que establezca el certificado en el puerto 8012 del equipo. De forma opcional, también se pueden reemplazar los cuatro ceros que preceden el número por la dirección IP real del equipo.  
  
    - El modificador **-h** especifica la huella digital del certificado.  
  
2. En Windows Vista, utilice la herramienta Netsh.exe, como se muestra en el ejemplo siguiente.  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}
    ```  
  
    - El parámetro **certhash** especifica la huella digital del certificado.  
  
    - El parámetro **ipport** especifica la dirección IP y el puerto, y funciona igual que el modificador **-i** de la herramienta Httpcfg.exe descrita.  
  
    - El parámetro **appid** es un GUID que se puede usar para identificar la aplicación propietaria.  
  
## <a name="bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a>Enlazar un certificado SSL a un número de puerto y admitir certificados de cliente  
  
1. En Windows Server 2003 o Windows XP, para admitir clientes que se autentican con certificados X.509 en la capa de transporte, siga el procedimiento anterior pero pase un parámetro de línea de comandos adicional a HttpCfg.exe, como se muestra en el ejemplo siguiente.  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     El modificador **-f** tiene `n` la sintaxis de donde n es un número entre 1 y 7. El valor 2, como se mostraba en el ejemplo anterior, habilita los certificados de cliente en el nivel de transporte. El valor 3 habilita los certificados de cliente y los asigna a una cuenta de Windows. Consulte la Ayuda HttpCfg.exe para el comportamiento de otros valores.  
  
2. En Windows Vista, para admitir clientes que se autentican con certificados X.509 en la capa de transporte, siga el procedimiento anterior, pero con un parámetro adicional, como se muestra en el ejemplo siguiente.  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
## <a name="delete-an-ssl-certificate-from-a-port-number"></a>Eliminar un certificado SSL de un número de puerto  
  
1. Use la herramienta HttpCfg.exe o Netsh.exe para ver los puertos y huellas digitales de todos los enlaces del equipo. Para imprimir la información en el disco, utilice el carácter de redirección ">", como se muestra en el ejemplo siguiente.  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. En Windows Server 2003 o Windows XP, utilice la herramienta HttpCfg.exe con las palabras clave **delete** y **ssl.** Utilice el modificador **-i** para especificar el `IP`número :`port` y el modificador **-h** para especificar la huella digital.  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. En Windows Vista, utilice la herramienta Netsh.exe, como se muestra en el ejemplo siguiente.  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a>Ejemplo  

 El código siguiente muestra cómo crear un servicio autohospedado utilizando la clase <xref:System.ServiceModel.WSHttpBinding> establezca para seguridad de transporte. Cuando cree una aplicación, especifique el número de puerto en la dirección.  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a>Consulte también

- [Seguridad de transporte HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md)

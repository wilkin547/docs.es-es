---
title: "Cómo: Configurar un puerto con un certificado SSL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c67ed21a8e4a9170d72ce842505e7695b11c26c9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a>Cómo: Configurar un puerto con un certificado SSL
Cuando crea un [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] autohospedado con la clase <xref:System.ServiceModel.WSHttpBinding> que utiliza la seguridad de transporte, también debe configurar un puerto con un certificado X.509. Si no está creando un servicio autohospedado, puede hospedar su servicio en Servicios de Internet Information Server (IIS). [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Seguridad de transporte HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 La herramienta que se usa para configurar un puerto depende del sistema operativo que se esté ejecutando en el equipo.  
  
 Si está ejecutando [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use la herramienta HttpCfg.exe. Esta herramienta se instala con [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. Con [!INCLUDE[wxp](../../../../includes/wxp-md.md)], puede descargar la herramienta en [herramientas de soporte técnico de Windows XP Service Pack 2](http://go.microsoft.com/fwlink/?LinkId=88606). [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][General de Httpcfg](http://go.microsoft.com/fwlink/?LinkId=88605). El [Httpcfg](http://go.microsoft.com/fwlink/?LinkId=94840) explica la sintaxis de la herramienta Httpcfg.exe.  
  
 Si está ejecutando [!INCLUDE[wv](../../../../includes/wv-md.md)], use la herramienta Netsh.exe, que ya está instalada.  
  
 En este tema se describe cómo se realizan varios procedimientos:  
  
-   Determinar la configuración de puerto actual de un equipo.  
  
-   Obtener la huella digital de un certificado (necesario para los dos procedimientos siguientes).  
  
-   Enlazar un certificado SSL a una configuración de puerto.  
  
-   Enlazar un certificado SSL a una configuración del puerto y admitir los certificados de cliente.  
  
-   Eliminar un certificado SSL de un número de puerto.  
  
 Tenga en cuenta que para modificar los certificados almacenados en el equipo se requieren privilegios de administrador.  
  
### <a name="to-determine-how-ports-are-configured"></a>Determinar cómo se configuran los puertos  
  
1.  En [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use la herramienta HttpCfg.exe para ver la configuración de puerto actual, usando la **consulta** y **ssl** se activa, tal como se muestra en el ejemplo siguiente.  
  
    ```  
    httpcfg query ssl  
    ```  
  
2.  En [!INCLUDE[wv](../../../../includes/wv-md.md)], use la herramienta Netsh.exe para ver la configuración de puerto actual, como se muestra en el ejemplo siguiente.  
  
    ```  
    netsh http show sslcert  
    ```  
  
### <a name="to-get-a-certificates-thumbprint"></a>Para obtener una huella digital de un certificado  
  
1.  Use el complemento de certificados de MMC para buscar un certificado X.509 que tenga como finalidad la autenticación del cliente. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo: ver certificados con el complemento de MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
2.  Obtenga acceso a la huella digital del certificado. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo: recuperar la huella digital de un certificado](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
3.  Copie la huella digital del certificado en un editor de texto, como por ejemplo Bloc de notas.  
  
4.  Quite todos los espacios entre los caracteres hexadecimales. Una manera de llevarlo a cabo es utilizar la característica del editor de texto buscar y reemplazar y reemplazar todos los espacios con un carácter nulo.  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number"></a>Enlazar un Certificado SSL a un número de puerto  
  
1.  En [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use la herramienta HttpCfg.exe en modo "set" en el almacén SSL (Capa de sockets seguros) para enlazar el certificado a un número de puerto. La herramienta utiliza la huella digital para identificar el certificado, tal y como se muestra en el ejemplo siguiente.  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    -   El **-i** conmutador tiene la sintaxis de `IP`:`port` e indica a la herramienta para establecer el certificado en el puerto 8012 del equipo. De forma opcional, también se pueden reemplazar los cuatro ceros que preceden el número por la dirección IP real del equipo.  
  
    -   El **-h** conmutador especifica la huella digital del certificado.  
  
2.  En [!INCLUDE[wv](../../../../includes/wv-md.md)], use la herramienta Netsh.exe, como se muestra en el ejemplo siguiente.  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    -   El **certhash** parámetro especifica la huella digital del certificado.  
  
    -   El **puerto IP** parámetro especifica la dirección IP y puerto y funciona igual que el **-i** switch de la herramienta Httpcfg.exe descrita.  
  
    -   El **appid** parámetro es un GUID que puede usarse para identificar la aplicación propietaria.  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a>Para enlazar un Certificado SSL a un número de puerto y a certificados de cliente de compatibilidad  
  
1.  En [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], para admitir clientes que se autentican con certificados X.509 en el nivel de transporte, siga el procedimiento anterior pero pase un parámetro de línea de comandos adicional a HttpCfg.exe, tal y como se muestra en el ejemplo siguiente.  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     El **-f** conmutador tiene la sintaxis de `n` donde n es un número entre 1 y 7. El valor 2, como se mostraba en el ejemplo anterior, habilita los certificados de cliente en el nivel de transporte. El valor 3 habilita los certificados de cliente y los asigna a una cuenta de Windows. Consulte la Ayuda HttpCfg.exe para el comportamiento de otros valores.  
  
2.  En [!INCLUDE[wv](../../../../includes/wv-md.md)], para admitir los clientes que se autentican con certificados X.509 en el nivel de transporte, siga el procedimiento anterior pero pase un parámetro de línea de comandos adicional a HttpCfg.exe, tal y como se muestra en el ejemplo siguiente.  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### <a name="to-delete-an-ssl-certificate-from-a-port-number"></a>Eliminar un Certificado SSL desde un número de puerto  
  
1.  Use la herramienta HttpCfg.exe o Netsh.exe para ver los puertos y huellas digitales de todos los enlaces del equipo. Para imprimir la información en el disco, use el carácter de redirección ">", como se muestra en el ejemplo siguiente.  
  
    ```  
    httpcfg query ssl>myMachinePorts.txt  
    ```  
  
2.  En [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use la herramienta HttpCfg.exe con el **eliminar** y **ssl** palabras clave. Use la **-i** conmutador para especificar el `IP`:`port` número y la **-h** conmutador para especificar la huella digital.  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3.  En [!INCLUDE[wv](../../../../includes/wv-md.md)], use la herramienta Netsh.exe, como se muestra en el ejemplo siguiente.  
  
    ```  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra cómo crear un servicio autohospedado utilizando la clase <xref:System.ServiceModel.WSHttpBinding> establezca para seguridad de transporte. Cuando cree una aplicación, especifique el número de puerto en la dirección.  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a>Vea también  
 [Seguridad de transporte HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md)

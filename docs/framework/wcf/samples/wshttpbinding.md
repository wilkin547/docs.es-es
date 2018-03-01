---
title: WSHttpBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WS Profile binding
ms.assetid: 22d85b19-0135-4141-9179-a0e9c343ad73
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8ff105c626f72d34cf6963586a84aba945b5af01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="wshttpbinding"></a>WSHttpBinding
Este ejemplo muestra cómo implementar un servicio y un cliente típicos con [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Este ejemplo está compuesto de un programa de consola de cliente (client.exe) y una biblioteca de servicios hospedada por Internet Information Services (IIS). El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta. La interfaz `ICalculator`, que expone las operaciones matemáticas (sumar, restar, multiplicar y dividir), define el contrato. El cliente realiza solicitudes sincrónicas a una operación matemática determinada y el servicio responde con el resultado. La actividad del cliente es visible en la ventana de la consola.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsHttp`  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Este ejemplo se expone el `ICalculator` contrato con la [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). La configuración de este enlace se ha expandido en el archivo Web.config.  
  
```xml
<bindings>  
  <wsHttpBinding>  
    <!--The following is the expanded configuration section for a-->  
    <!--WSHttpBinding. Each property is configured with the default-->   
    <!--value. See the ReliableSession, TransactionFlow, -->  
    <!--TransportSecurity, and MessageSecurity samples in the WS -->  
    <!--directory to learn how to configure these features. -->  
    <binding name="Binding1"  
              bypassProxyOnLocal="false"   
              transactionFlow="false"   
              hostNameComparisonMode="StrongWildcard"  
              maxBufferPoolSize="524288"   
              maxReceivedMessageSize="65536"  
              messageEncoding="Text"   
              textEncoding="utf-8"   
              useDefaultWebProxy="true"  
              allowCookies="false">  
      <reliableSession ordered="true"   
                       inactivityTimeout="00:10:00"  
                       enabled="false" />  
      <security mode="Message">  
        <message clientCredentialType="Windows"   
                 negotiateServiceCredential="true"  
                 algorithmSuite="Default"   
                 establishSecurityContext="true" />  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
```  
  
 En el elemento `binding` de base, el valor `maxReceivedMessageSize` le permite configurar el tamaño máximo de un mensaje entrante (en bytes). El valor `hostNameComparisonMode` le permite configurar si se considera el nombre de host al demultiplexar los mensajes en el servicio. El valor `messageEncoding` le permite configurar si utilizar la codificación de texto o MTOM para los mensajes. El valor `textEncoding` le permite configurar la codificación de caracteres para los mensajes. El valor `bypassProxyOnLocal` le permite configurar si utilizar un proxy HTTP para la comunicación local. El valor `transactionFlow` configura si se fluye (si se configura una operación para el flujo de la transacción) la transacción actual.  
  
 En el [ \<reliableSession >](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) elemento, el valor booleano habilitado configura si las sesiones confiables están habilitadas. El valor `ordered` configura si se va a conservar la clasificación del mensaje. El valor `inactivityTimeout` configura cuánto tiempo puede estar una sesión inactiva antes de que se produzcan errores.  
  
 En el [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md), el `mode` valor configura el modo de seguridad debería utilizarse. En este ejemplo, los mensajes se utiliza la seguridad, que es la razón por la [ \<mensaje >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) se especifica dentro de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md).  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Instale [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mediante el siguiente comando.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Vea también

---
title: Tratamiento de errores y puentes
ms.date: 03/30/2017
ms.assetid: 4ae87d1a-b615-4014-a494-a53f63ff0137
ms.openlocfilehash: 20f5af5736e5869ead0f7c50ce0fff22391ea730
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33804396"
---
# <a name="bridging-and-error-handling"></a>Tratamiento de errores y puentes
Este ejemplo muestra cómo se utiliza el servicio de enrutamiento de Windows Communication Foundation (WCF) para puentear la comunicación entre un cliente y un servicio que utilizan enlaces diferentes. Este ejemplo también muestra cómo utilizar un servicio de seguridad de reserva para escenarios de conmutación por error. El servicio de enrutamiento es un componente WCF que facilita el proceso incluir un enrutador basado en contenido en la aplicación. Este ejemplo adapta el ejemplo de la calculadora de WCF estándar para comunicarse con el servicio de enrutamiento.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\ErrorHandlingAndBridging`  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 En este ejemplo, el cliente de la calculadora se configura para enviar los mensajes a un extremo que expone el enrutador. El servicio de enrutamiento se configura para aceptar todos los mensajes que se le envíen y reenviarlos a un extremo que corresponde al servicio de calculadora. Los siguientes puntos describen la configuración del servicio de calculadora principal, el servicio de calculadora de seguridad y el cliente de calculadora, y el modo en que se produce la comunicación entre el cliente y el servicio mediante el servicio de enrutamiento:  
  
-   El cliente de calculadora se configura para utilizar BasicHttpBinding mientras que el servicio de calculadora se configura para utilizar NetTcpBinding. El servicio de enrutamiento debe convertir automáticamente los mensajes antes de enviarlos al servicio de calculadora y también convierte las respuestas para que el cliente de la calculadora pueda tener acceso a ellos.  
  
-   El servicio de enrutamiento conoce dos servicios de calculadora: el principal y el de reserva. El servicio de enrutamiento intenta comunicarse primero con el extremo de servicio de calculadora principal. Si se produce un error en este intento debido a que el punto de conexión se desactiva, el servicio de enrutamiento intenta comunicarse con el punto de conexión del servicio de calculadora de reserva.  
  
 Por tanto, los mensajes enviados desde el cliente son recibidos por el enrutador y se vuelven a enrutar al servicio de calculadora real. Si el extremo de servicio de calculadora se desactiva, el servicio de enrutamiento enruta el mensaje al extremo de servicio de calculadora de reserva. Los mensajes del servicio de calculadora de reserva se devuelven al enrutador del servicio, que a su vez los pasa al cliente de la calculadora.  
  
> [!NOTE]
>  Una lista de reserva puede tener definido más de un extremo. En este caso, si el punto de conexión de servicio de seguridad se desactiva, el servicio de enrutamiento intenta conectarse al punto de conexión de reserva siguiente en la lista hasta que se produce una conexión correcta.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra RouterBridgingAndErrorHandling.sln.  
  
2.  Presione F5 o CTRL+MAYÚS+B en Visual Studio.  
  
    1.  Si desea iniciar de forma automática los proyectos necesarios al presionar F5, haga clic en la solución, seleccione **propiedades**y en el **proyecto de inicio** nodo bajo **propiedades comunes**, seleccione **proyectos de inicio múltiples**y establezca todos los proyectos en **iniciar**.  
  
    2.  Si compila el proyecto con CTRL+MAYÚS+B, debe iniciar las siguientes aplicaciones:  
  
        1.  El cliente de la calculadora (./CalculatorClient/bin/client.exe)  
  
        2.  El servicio de calculadora (./CalculatorService/bin/service.exe)  
  
        3.  El servicio de enrutamiento (./RoutingService/bin/RoutingService.exe)  
  
3.  En el cliente de la calculadora, presione Entrar para iniciar el cliente.  
  
     Debería ver los siguientes resultados:  
  
    ```Output  
    Add(100,15.99) = 115.99  
    Subtract(145,76.54) = 68.46  
    Multiply(9,81.25) = 731.25  
    Divide(22,7) = 3.14285714285714  
    ```  
  
## <a name="configurable-via-code-or-appconfig"></a>Configurable a través de código o App.onfig  
 El ejemplo viene configurado para utilizar un archivo App.config que define el comportamiento del enrutador. También puede cambiar el nombre del archivo App.config por otro de modo que no se reconozca y quitar el comentario de la llamada al método `ConfigureRouterViaCode()`. Cualquier método provoca el mismo comportamiento del enrutador.  
  
### <a name="scenario"></a>Escenario  
 En este ejemplo se muestra el enrutador del servicio que actúa como puente de protocolo y un controlador de errores. En este escenario, no se produce el enrutamiento basado en contenido; el servicio de enrutamiento actúa como un nodo de proxy transparente configurado para pasar los mensajes a un conjunto preconfigurado de extremos de destino directamente. El servicio de enrutamiento también sigue pasos adicionales para tratar de forma transparente los errores que ocurren al intentar enviar a los extremos con los que está configurado para comunicarse. Al actuar como puente de protocolo, el servicio de enrutamiento permite al usuario definir un protocolo para la comunicación externa y otra para la interna.  
  
### <a name="real-world-scenario"></a>Escenario real  
 Contoso desea proporcionar un punto de conexión de servicio interoperable, al tiempo que optimiza el rendimiento internamente. Por tanto, expone sus servicios a los demás a través de un punto de conexión utilizando BasicHttpBinding, mientras que, internamente, usa el servicio de enrutamiento para puentear esa conexión al punto de conexión mediante NetTcpBinding, que su servicio usa. Además, Contoso desea que su oferta de servicios tolere las interrupciones temporales en cualquiera de sus servicios de producción y, por lo tanto, proporcionar varios puntos de conexión virtuales detrás del servicio de enrutador utilizando las funciones de tratamiento de errores para conmutar por error automáticamente a los puntos de conexión de reserva cuando sea necesario.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de persistencia y el hospedaje de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)

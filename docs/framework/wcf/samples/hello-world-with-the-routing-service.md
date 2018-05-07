---
title: "\"Hola mundo\" con el Servicio de enrutamiento"
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: 88b7cdb9beabd8e4ff5ffc9a1c31a702a3cb4f02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="hello-world-with-the-routing-service"></a>"Hola mundo" con el Servicio de enrutamiento
Este ejemplo muestra el servicio de enrutamiento de Windows Communication Foundation (WCF). El servicio de enrutamiento es un componente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que permite incluir un enrutador basado en contenido fácilmente en una aplicación. En este ejemplo se adapta el ejemplo de la calculadora de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] estándar para comunicarse utilizando el servicio de enrutamiento. En este ejemplo, el cliente de la calculadora se configura para enviar los mensajes a un punto de conexión que expone el enrutador. El servicio de enrutamiento se configura para aceptar todos los mensajes que se le envíen y reenviarlos a un extremo que corresponde al servicio de calculadora. Por tanto, los mensajes enviados desde el cliente son recibidos por el enrutador y se vuelven a enrutar al servicio de calculadora real. Los mensajes del servicio de calculadora se devuelven al enrutador, que a su vez los devuelve al cliente de la calculadora.  
  
### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra HelloRoutingService.sln.  
  
2.  Presione F5 o CTRL+MAYÚS+B.  
  
    > [!NOTE]
    >  Si presiona F5, el cliente de la calculadora se inicia automáticamente. Si presiona CTRL+MAYÚS+B (para compilar), debe iniciar las siguientes aplicaciones.  
    >   
    >  1.  El cliente de la calculadora (./CalculatorClient/bin/client.exe)  
    > 2.  El servicio de calculadora (./CalculatorService/bin/service.exe)  
    > 3.  El servicio de enrutamiento (./RoutingService/bin/RoutingService.exe)  
  
3.  Presione Entrar para iniciar el cliente.  
  
     Debería ver los siguientes resultados:  
  
     Sumar(100;15,99) = 115,99  
  
     Restar(145;76,54) = 68,46  
  
     Multiplicar(9;81,25) = 731,25  
  
     Dividir(22;7) = 3.14285714285714  
  
## <a name="configurable-via-code-or-appconfig"></a>Configurable a través de código o de un archivo de configuración  
 El ejemplo viene configurado para utilizar un archivo App.config que define el comportamiento del enrutador. También puede cambiar el nombre del archivo de configuración por otro de modo que no se reconozca y quitar el comentario de la llamada al método ConfigureRouterViaCode(). Cualquier método provoca el mismo comportamiento del enrutador.  
  
### <a name="scenario"></a>Escenario  
 En este ejemplo se muestra el enrutador que actúa como suministro de mensajes básico. El servicio de enrutamiento actúa como un nodo de proxy transparente configurado para pasar los mensajes a un conjunto preconfigurado de puntos de conexión de destino directamente.  
  
### <a name="real-world-scenario"></a>Escenario real  
 Contoso desea aumentar la flexibilidad que tiene en la denominación, tratamiento, configuración y seguridad de sus servicios. Para ello, coloca un suministro de mensajes básico delante de sus servicios de modo que actúen como punto de conexión expuesto al público. Esto les permite implantar seguridad adicional delante de sus servicios reales y facilitar la implementación de soluciones escaladas horizontalmente o de versiones del servicio más adelante.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de persistencia y el hospedaje de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)

---
title: Reconfiguración dinámica
ms.date: 03/30/2017
ms.assetid: b20786ae-cce6-4f91-b6cb-9cae116faf8b
ms.openlocfilehash: a147a1d6cf61001832661376363ecc850ecad309
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43881999"
---
# <a name="dynamic-reconfiguration"></a>Reconfiguración dinámica
Este ejemplo muestra el servicio de enrutamiento de Windows Communication Foundation (WCF). El servicio de enrutamiento es un componente WCF que facilita la tarea debe incluir un enrutador basado en contenido en la aplicación. Este ejemplo adapta el ejemplo de calculadora de WCF estándar para comunicarse con el servicio de enrutamiento. En este ejemplo se muestra el modo en que el servicio de enrutamiento puede reconfigurarse dinámicamente en tiempo de ejecución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\DynamicReconfiguration`  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 Para reconfigurar el servicio de enrutamiento en tiempo de ejecución de forma dinámica, este ejemplo desencadena un temporizador cada cinco segundos que crea un nuevo objeto <xref:System.ServiceModel.Routing.RoutingConfiguration> y lo aplica. Esta configuración hace referencia al extremo de la calculadora normal o al extremo de la calculadora de redondeo. La aplicación cliente de la calculadora hace que sus mensajes sean devueltos por un servicio u otro, según a qué servicio de enrutamiento esté configurado para enrutar en ese momento.  
  
 La capacidad del servicio de enrutamiento se usa para la reconfiguración dinámica a través de un comportamiento personalizado. Este comportamiento personalizado asocia una extensión de servicio, que contiene un sencillo temporizador de subprocesos que se desencadena cada cinco segundos y que resulta en una devolución de llamada al método `UpdateRules`. Esta devolución de llamada crea y aplica la nueva configuración de enrutamiento. En una implementación real, esta devolución de llamada probablemente se lograría como resultado de algún otro tipo de evento, como una notificación de evento SQL o un anuncio de detección del WS.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra DynamicReconfiguration.sln.  
  
2.  Para abrir **el Explorador de soluciones**, seleccione **el Explorador de soluciones** desde el **vista** menú.  
  
3.  Presione **F5** o **CTRL + MAYÚS + B** en Visual Studio.  
  
    1.  Si desea iniciar automáticamente los proyectos necesarios al presionar **F5**, haga clic en la solución y seleccione **propiedades**. Seleccione el **proyecto de inicio** nodo bajo **propiedades comunes** en el panel izquierdo. Seleccione el **varios proyectos de inicio** botón de radio y establezca todos los proyectos que tienen el **iniciar** acción.  
  
    2.  Si compila el proyecto con **CTRL + MAYÚS + B**, debe iniciar las siguientes aplicaciones:  
  
        1.  El cliente de la calculadora (./CalculatorClient/bin/client.exe)  
  
        2.  El servicio de calculadora (./CalculatorService/bin/service.exe)  
  
        3.  El servicio de enrutamiento de calculadora (./RoundingCalcService/bin/service.exe)  
  
        4.  RoutingService (./RoutingService/bin/RoutingService.exe)  
  
4.  En la ventana de la consola del cliente de la calculadora, presione ENTRAR para iniciar el cliente y llame a las operaciones de servicio de calculadora.  
  
     El servicio de enrutamiento enruta los mensajes a la calculadora de redondeo y o bien a la calculadora normal ya que la configuración de enrutamiento cambia dinámicamente cada cinco segundos. Según el punto de conexión al que el servicio de enrutamiento está configurado para enviar los mensajes, hay diferentes resultados en la ventana de la consola del cliente.  
  
5.  Siga presionando ENTRAR varias veces durante más de cinco segundos y observe el cambio en los resultados del servicio.  
  
    1.  Lo siguiente es el resultado que se devuelve si el servicio de enrutador está configurado para enrutar los mensajes al servicio de calculadora de redondeo.  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.2  
        Divide(22,7) = 3.1  
        ```  
  
    2.  Lo siguiente es el resultado que se devuelve si el servicio de enrutamiento está configurado para enrutar los mensajes al servicio de calculadora de redondeo.  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
6.  El servicio de calculadora y el servicio de calculadora de redondeo también imprimen un registro de las operaciones invocadas en sus respectivas ventanas de consola.  
  
7.  En la ventana de consola de cliente, escriba "quit" y presione ENTRAR para salir.  
  
8.  Presione ENTRAR en las ventanas de la consola de servicios para terminar los servicios.  
  
## <a name="scenario"></a>Escenario  
 En este ejemplo se muestra el enrutador que actúa como enrutador basado en contenido que permite exponer varios tipos o la implementación de los servicios a través de un extremo.  
  
### <a name="real-world-scenario"></a>Escenario real  
 Contoso desea virtualizar todos sus servicios para exponer solo un extremo a través del que ofrecer acceso a varios tipos diferentes de servicios públicamente. En este caso, utilizan las capacidades de enrutamiento basado en contenido del servicio de enrutamiento para determinar dónde se deberían enviar las solicitudes entrantes.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de persistencia y el hospedaje de AppFabric](https://go.microsoft.com/fwlink/?LinkId=193961)

---
title: "Tratamiento de errores y puentes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4ae87d1a-b615-4014-a494-a53f63ff0137
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Tratamiento de errores y puentes
Este ejemplo muestra el modo en que se usa el servicio de enrutamiento de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para puentear la comunicación entre un cliente y un servicio que utilizan enlaces diferentes.Este ejemplo también muestra cómo utilizar un servicio de seguridad de reserva para escenarios de conmutación por error.El servicio de enrutamiento es un componente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que permite incluir un enrutador basado en contenido fácilmente en una aplicación.En este ejemplo se adapta el ejemplo de la calculadora de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] estándar para comunicarse utilizando el servicio de enrutamiento.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\RoutingServices\ErrorHandlingAndBridging`  
  
## Detalles del ejemplo  
 En este ejemplo, el cliente de la calculadora se configura para enviar los mensajes a un extremo que expone el enrutador.El servicio de enrutamiento se configura para aceptar todos los mensajes que se le envíen y reenviarlos a un extremo que corresponde al servicio de calculadora.Los siguientes puntos describen la configuración del servicio de calculadora principal, el servicio de calculadora de seguridad y el cliente de calculadora, y el modo en que se produce la comunicación entre el cliente y el servicio mediante el servicio de enrutamiento:  
  
-   El cliente de calculadora se configura para utilizar BasicHttpBinding mientras que el servicio de calculadora se configura para utilizar NetTcpBinding.El servicio de enrutamiento debe convertir automáticamente los mensajes antes de enviarlos al servicio de calculadora y también convierte las respuestas para que el cliente de la calculadora pueda tener acceso a ellos.  
  
-   El servicio de enrutamiento conoce dos servicios de calculadora: el principal y el de reserva.El servicio de enrutamiento intenta comunicarse primero con el extremo de servicio de calculadora principal.Si se produce un error en este intento debido a que el extremo se desactiva, el servicio de enrutamiento intenta comunicarse con el extremo del servicio de calculadora de reserva.  
  
 Por tanto, los mensajes enviados desde el cliente son recibidos por el enrutador y se vuelven a enrutar al servicio de calculadora real.Si el extremo de servicio de calculadora se desactiva, el servicio de enrutamiento enruta el mensaje al extremo de servicio de calculadora de reserva.Los mensajes del servicio de calculadora de reserva se devuelven al enrutador del servicio, que a su vez los pasa al cliente de la calculadora.  
  
> [!NOTE]
>  Una lista de reserva puede tener definido más de un extremo.En este caso, si el extremo de servicio de seguridad se desactiva, el servicio de enrutamiento intenta conectarse al extremo de reserva siguiente en la lista hasta que se produce una conexión correcta.  
  
#### Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra RouterBridgingAndErrorHandling.sln.  
  
2.  Presione F5 o CTRL\+MAYÚS\+B en Visual Studio.  
  
    1.  Si desea iniciar automáticamente los proyectos necesarios cuando presione F5, haga clic con el botón secundario en la solución, seleccione **Propiedades** y, en el nodo **Inicio del proyecto**, en **Propiedades comunes**, seleccione **Proyectos de inicio múltiples** y establezca todos los proyectos en **Iniciar**.  
  
    2.  Si compila el proyecto con CTRL\+MAYÚS\+B, debe iniciar las siguientes aplicaciones:  
  
        1.  El cliente de la calculadora \(.\/CalculatorClient\/bin\/client.exe\)  
  
        2.  El servicio de calculadora \(.\/CalculatorService\/bin\/service.exe\)  
  
        3.  El servicio de enrutamiento \(.\/RoutingService\/bin\/RoutingService.exe\)  
  
3.  En el cliente de la calculadora, presione Entrar para iniciar el cliente.  
  
     Debería ver los siguientes resultados:  
  
    ```Output  
    Sumar(100;15,99) = 115,99  
    Restar(145;76,54) = 68,46  
    Multiplicar(9;81,25) = 731,25  
    Dividir(22;7) = 3,14285714285714  
  
    ```  
  
## Configurable a través de código o App.onfig  
 El ejemplo viene configurado para utilizar un archivo App.config que define el comportamiento del enrutador.También puede cambiar el nombre del archivo App.config por otro de modo que no se reconozca y quitar el comentario de la llamada al método `ConfigureRouterViaCode()`.Cualquier método provoca el mismo comportamiento del enrutador.  
  
### Escenario  
 En este ejemplo se muestra el enrutador del servicio que actúa como puente de protocolo y un controlador de errores.En este escenario, no se produce el enrutamiento basado en contenido; el servicio de enrutamiento actúa como un nodo de proxy transparente configurado para pasar los mensajes a un conjunto preconfigurado de extremos de destino directamente.El servicio de enrutamiento también sigue pasos adicionales para tratar de forma transparente los errores que ocurren al intentar enviar a los extremos con los que está configurado para comunicarse.Al actuar como puente de protocolo, el servicio de enrutamiento permite al usuario definir un protocolo para la comunicación externa y otra para la interna.  
  
### Escenario real  
 Contoso desea proporcionar un extremo de servicio interoperable, al tiempo que optimiza el rendimiento internamente.Por tanto, expone sus servicios a los demás a través de un extremo utilizando BasicHttpBinding, mientras que, internamente, usa el servicio de enrutamiento para puentear esa conexión al extremo mediante NetTcpBinding, que su servicio usa.Además, Contoso desea que su oferta de servicios tolere las interrupciones temporales en cualquiera de sus servicios de producción y, por lo tanto, proporcionar varios extremos virtuales detrás del servicio de enrutador utilizando las funciones de tratamiento de errores para conmutar por error automáticamente a los extremos de reserva cuando sea necesario.  
  
## Vea también  
 [Ejemplos de hospedaje y persistencia de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)
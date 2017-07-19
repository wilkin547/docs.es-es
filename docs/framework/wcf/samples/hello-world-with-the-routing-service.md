---
title: "&quot;Hola mundo&quot; con el Servicio de enrutamiento | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &quot;Hola mundo&quot; con el Servicio de enrutamiento
En este ejemplo se muestra el servicio de enrutamiento de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].El servicio de enrutamiento es un componente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que permite incluir un enrutador basado en contenido fácilmente en una aplicación.En este ejemplo se adapta el ejemplo de la calculadora de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] estándar para comunicarse utilizando el servicio de enrutamiento.En este ejemplo, el cliente de la calculadora se configura para enviar los mensajes a un extremo que expone el enrutador.El servicio de enrutamiento se configura para aceptar todos los mensajes que se le envíen y reenviarlos a un extremo que corresponde al servicio de calculadora.Por tanto, los mensajes enviados desde el cliente son recibidos por el enrutador y se vuelven a enrutar al servicio de calculadora real.Los mensajes del servicio de calculadora se devuelven al enrutador, que a su vez los devuelve al cliente de la calculadora.  
  
### Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra HelloRoutingService.sln.  
  
2.  Presione F5 o CTRL\+MAYÚS\+B.  
  
    > [!NOTE]
    >  Si presiona F5, el cliente de la calculadora se inicia automáticamente.Si presiona CTRL\+MAYÚS\+B \(para compilar\), debe iniciar las siguientes aplicaciones.  
    >   
    >  1.  El cliente de la calculadora \(.\/CalculatorClient\/bin\/client.exe\)  
    > 2.  El servicio de calculadora \(.\/CalculatorService\/bin\/service.exe\)  
    > 3.  El servicio de enrutamiento \(.\/RoutingService\/bin\/RoutingService.exe\)  
  
3.  Presione Entrar para iniciar el cliente.  
  
     Debería ver los siguientes resultados:  
  
     Sumar\(100;15,99\) \= 115,99  
  
     Restar\(145;76,54\) \= 68,46  
  
     Multiplicar\(9;81,25\) \= 731,25  
  
     Dividir\(22;7\) \= 3.14285714285714  
  
## Configurable a través de código o de un archivo de configuración  
 El ejemplo viene configurado para utilizar un archivo de configuración que define el comportamiento del enrutador.También puede cambiar el nombre del archivo de configuración por otro de modo que no se reconozca y quitar el comentario de la llamada al método ConfigureRouterViaCode\(\).Cualquier método provoca el mismo comportamiento del enrutador.  
  
### Escenario  
 En este ejemplo se muestra el enrutador que actúa como suministro de mensajes básico.El servicio de enrutamiento actúa como un nodo de proxy transparente configurado para pasar los mensajes a un conjunto preconfigurado de extremos de destino directamente.  
  
### Escenario real  
 Contoso desea aumentar la flexibilidad que tiene en la denominación, tratamiento, configuración y seguridad de sus servicios.Para ello, coloca un suministro de mensajes básico delante de sus servicios de modo que actúen como extremo expuesto al público.Esto les permite implantar seguridad adicional delante de sus servicios reales y facilitar la implementación de soluciones escaladas horizontalmente o de versiones del servicio más adelante.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## Vea también  
 [Ejemplos de hospedaje y persistencia de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)
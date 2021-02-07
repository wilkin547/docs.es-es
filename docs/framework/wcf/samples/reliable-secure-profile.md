---
description: 'Más información sobre: perfil seguro confiable'
title: Perfil seguro confiable
ms.date: 03/30/2017
ms.assetid: 921edc41-e91b-40f9-bde9-b6148b633e61
ms.openlocfilehash: 6e9552b3a6e715f6eac6742f89b2e70a34f926a6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703827"
---
# <a name="reliable-secure-profile"></a>Perfil seguro confiable

Este ejemplo muestra cómo crear WCF y un [perfil seguro confiable (RSP)](http://www.ws-i.org/Profiles/ReliableSecureProfile-1.0.html). Este ejemplo muestra la implementación de un canal de [creación de conexiones](http://docs.oasis-open.org/ws-rx/wsmc/200702/wsmc-1.0-spec-cs-01.pdf) , que se puede componer junto con mensajería confiable y, opcionalmente, un canal seguro para crear un enlace seguro confiable basado en la especificación RSP.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ReliableSecureProfile`  
  
## <a name="discussion"></a>Debate  

 En este ejemplo se muestra un escenario de intercambio de mensajes bidireccional asincrónico confiable. El servicio tiene un contrato dúplex y el cliente implementa el contrato de devolución de llamadas dúplex. El cliente inicia una solicitud a un servicio, para el que se espera una respuesta en una conexión independiente. El mensaje de solicitud se envía de forma confiable. El cliente no desea abrir un punto de conexión para realizar escuchas hasta el fin. Por tanto, sondea el servicio con solicitudes de 'Establecer conexión' para el servicio de modo que la respuesta se devuelva en el canal secundario de esta solicitud de 'Establecer conexión'. En este ejemplo se muestra cómo conseguir una comunicación dúplex, confiable y segura a través de HTTP sin que el cliente exponga un punto de conexión para realizar escuchas (y cree una excepción de firewall).  
  
## <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Abra la solución **ReliableSecureProfile** .  
  
2. Haga clic con el botón derecho en el proyecto de **servicio** en **Explorador de soluciones**, seleccione **depurar**, **Iniciar nueva instancia** en el menú contextual. De esta forma se inicia el host de servicio.  
  
3. Haga clic con el botón derecho en el proyecto de **cliente** en **Explorador de soluciones**, seleccione **depurar**, **Iniciar nueva instancia** en el menú contextual. De esta forma se inicia el cliente.  
  
4. Escriba una cadena en el símbolo del sistema de la ventana de la consola del cliente y haga clic en ENTRAR. De este modo se envía la cadena de entrada al servicio, que calcula un valor hash de la misma.  
  
5. Vea el resultado en las ventanas de cliente cuando el servicio llama de nuevo a la operación de contrato de devolución de llamada dúplex para mostrar el resultado en la ventana de la consola del cliente. Hay un retraso intencionado en el servicio para simular una operación que tarda en ejecutarse y procesa los datos.  
  
6. Al supervisar el tráfico HTTP (mediante alguna de las herramientas de supervisión de red en línea, como Monitor de red, Fiddler, etc.), se muestra que se establece una secuencia para la comunicación entre el cliente y el servicio que el Perfil de protección confiable rechaza, y cómo sondea el cliente dicho servicio con las solicitudes 'Establecer conexión'. Cuando el servicio está preparado para devolver la respuesta procesada, utiliza el canal secundario de la última solicitud 'Establecer conexión' para enviar de vuelta los resultados.  
  
7. Presione ENTRAR en la ventana de la consola del servicio para cerrar el servicio. Presione ENTRAR en la ventana de la consola de cliente para cerrar el cliente.

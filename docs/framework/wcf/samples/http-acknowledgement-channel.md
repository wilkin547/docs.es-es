---
title: Canal de confirmación de HTTP
ms.date: 03/30/2017
ms.assetid: 469f3056-5ef2-4753-8acf-b574d23d83cf
ms.openlocfilehash: d83f3aa590471aa3d83b8f7bd1464ec1e6e106fc
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43559548"
---
# <a name="http-acknowledgement-channel"></a>Canal de confirmación de HTTP
El canal de confirmación HTTP es un ejemplo de canal en niveles que cambia el patrón de mensajería unidireccional, permitiendo que un servicio confirme o rechace los mensajes entrantes en lugar de enviar una confirmación de recibo automáticamente. Además, permite al servicio retrasar la confirmación hasta que pueda tener la garantía de que el mensaje se procesará.  
  
## <a name="demonstrates"></a>Demostraciones  
 <xref:System.ServiceModel.Channels.ReceiveContext>, ejemplo del canal en niveles (canal de confirmación HTTP).  
  
## <a name="discussion"></a>Explicación  
 El canal de confirmación HTTP implementa <xref:System.ServiceModel.Channels.ReceiveContext> para volver a dar forma al patrón de mensajería solicitud-respuesta HTTP para un patrón unidireccional con confirmación demorada. Con este nuevo patrón, un servicio puede garantizar el procesamiento de los mensajes enviando una confirmación en forma de código de estado OK 200 de HTTP sin bloquear el cliente hasta que el procesamiento de mensajes se complete o puede enviar un mensaje de error al cliente en forma de código de estado de error de servidor interno 500 de HTTP. Por ejemplo, un servicio podría enviar una confirmación después de escribir un mensaje en una cola y, a continuación, continuar el procesamiento del mensaje de forma asincrónica. En este escenario, un cliente podría estar seguro de que el servicio procesó al menos una vez sus mensajes, si reenviara cada mensaje hasta que recibiera una confirmación del servicio. Tenga en cuenta que si un servicio requiere el procesamiento de mensajes asincrónico a través de HTTP sin ninguna garantía del procesamiento de los mensajes, es más adecuado usar <xref:System.ServiceModel.Channels.OneWayBindingElement>.  
  
 <xref:System.ServiceModel.Channels.ReceiveContext> se utiliza para conservar el mensaje en su lugar mientras se determina si se puede procesar en el servicio. La capacidad de un servicio para procesar el mensaje correctamente se indica llamando a Complete en el objeto <xref:System.ServiceModel.Channels.ReceiveContext>, que envía un código de estado OK de HTTP y si el servicio puede procesar el mensaje, se indica llamando al método <xref:System.ServiceModel.Channels.ReceiveContext> del objeto `Abandon` en el objeto <xref:System.ServiceModel.Channels.ReceiveContext>, que envía un código de estado de error de servidor interno HTTP.  
  
 En este ejemplo, el cliente solicita la información de procesamiento enviando un identificador de empleado. En el extremo del servicio, si el identificador de empleado recibido es mayor que 50, el servicio envía un código de estado de HTTP 500 (error de servidor interno) al cliente; de lo contrario, se supone que el procesamiento se puede hacer correctamente y envía un código de estado HTTP 200 (correcto) al cliente.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] con privilegios de administrador.  
  
2.  Abra el **HttpAckChannel** solución.  
  
3.  Inicie una nueva instancia de la **servicio** proyecto haciendo clic en el proyecto en **el Explorador de soluciones**y seleccionando **depurar**, **Iniciar nueva instancia** en el menú contextual.  
  
4.  Inicie una nueva instancia de la **cliente** proyecto haciendo clic en el proyecto en **el Explorador de soluciones**y seleccionando **depurar**, y **Iniciar nueva instancia** en el menú contextual.  
  
5.  Cuando el servicio se haya iniciado, presione Entrar en la ventana de cliente para permitir al cliente enviar un mensaje al servicio.  
  
6.  El primer mensaje se procesa en el servicio y envía un código de estado OK de HTTP al cliente.  
  
7.  El segundo mensaje es incorrecto y envía un código de estado de error de servidor interno de HTTP al cliente, que genera un <xref:System.ServiceModel.CommunicationException> en el cliente.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpAckChannel`

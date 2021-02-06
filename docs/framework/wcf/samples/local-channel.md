---
description: 'Más información acerca de: canal local'
title: Canal local
ms.date: 03/30/2017
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
ms.openlocfilehash: a580abc1e8dcd89c40c9fdc02001deb094eb0b05
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631754"
---
# <a name="local-channel"></a>Canal local

Canal local es un canal de transporte Windows Communication Foundation (WCF) que se usa para la comunicación dentro del mismo dominio de aplicación. Esto es útil para los escenarios donde el cliente y el servicio se están ejecutando en el mismo dominio de aplicación y la sobrecarga de la pila del canal WCF típica (la serialización y deserialización de mensajes) se debe evitar.  
  
## <a name="demonstrates"></a>Muestra  

 Canal local  
  
## <a name="discussion"></a>Debate  

 El ejemplo consta de dos archivos de proyecto:  
  
- **LocalChannel**: la representación mediante programación del canal local dentro del dominio de aplicación actual. En este proyecto, el componente de envío coloca el mensaje en una cola en memoria y el componente receptor saca el mensaje de la cola para recibirlo.  
  
- **ClientAndService**: este proyecto hospeda un servicio en una aplicación de consola y, a continuación, ejecuta un cliente para llamar al servicio desde dentro del mismo dominio de aplicación.  
  
 El diseño del canal local omite la pila del canal y el proceso de serialización para aumentar la velocidad. El canal de transporte local se implementa utilizando una cola para las llamadas del servicio de transporte desde el cliente al servicio y para devolver el valor al cliente. En lugar de serializar los parámetros y los valores devueltos, en el ejemplo se copian los objetos.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Compile y ejecute la solución LocalChannel.  
  
2. El host del servicio se inicia y el cliente llama al servicio utilizando el canal local. Una ventana de la consola aparece para mostrar los resultados de la llamada del servicio.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`

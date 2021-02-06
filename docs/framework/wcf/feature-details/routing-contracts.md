---
description: 'Más información acerca de: enrutar contratos'
title: Enrutar contratos
ms.date: 03/30/2017
ms.assetid: 9ceea7ae-ea19-4cf9-ba4f-d071e236546d
ms.openlocfilehash: 7ccdb281402bdf61d3ba27f97019fd3126bdf29b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632794"
---
# <a name="routing-contracts"></a>Enrutar contratos

Los contratos de enrutamiento definen los patrones de mensaje que puede procesar el servicio de enrutamiento.  Todos los contratos son sin tipos y permiten al servicio recibir un mensaje sin conocimiento de la acción o del esquema del mensaje. Esto permite al servicio de enrutamiento enrutar mensajes genéricamente sin configuración adicional para las características de los mensajes subyacentes que se enrutan.  
  
## <a name="routing-contracts"></a>Enrutar contratos  

 Como el servicio de enrutamiento acepta un objeto de mensaje de WCF genérico, el aspecto más importante que se debe tener en cuenta al seleccionar un contrato es la forma del canal que se usará al comunicarse con los clientes y los servicios. Al procesar mensajes, el servicio de enrutamiento usa suministros de mensajes simétricos, así que, normalmente, la forma del contrato entrante debe coincidir con la forma del contrato saliente. Sin embargo, hay casos en los que el distribuidor del modelo de servicio puede modificar las formas, como cuando el distribuidor convierte un canal dúplex en un canal de solicitud-respuesta, o quita el soporte de la sesión de un canal cuando no es necesario y no se usa (es decir, cuando **SessionMode. allowed**, convirtiendo un **IInputSessionChannel** en **IInputChannel**).  
  
 Para admitir estos suministros de mensajes, el servicio de enrutamiento proporciona contratos en el espacio de nombres <xref:System.ServiceModel.Routing>, que se deben usar al definir los puntos de conexión de servicio empleados por el servicio de enrutamiento. Estos contratos son sin tipo, lo que permite recibir cualquier acción o tipo de mensaje, y permite al servicio de enrutamiento administrar mensajes sin conocer el esquema del mensaje concreto. Para obtener más información acerca de los contratos utilizados por el servicio de enrutamiento, consulte [enrutamiento de contratos](routing-contracts.md).  
  
 Los contratos proporcionados por el servicio de enrutamiento se encuentran en el espacio de nombres <xref:System.ServiceModel.Routing> y se describen en la siguiente tabla.  
  
|Contrato|Forma|Forma del canal|  
|--------------|-----------|-------------------|  
|<xref:System.ServiceModel.Routing.ISimplexDatagramRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputChannel-> IOutputChannel|  
|<xref:System.ServiceModel.Routing.ISimplexSessionRouter>|SessionMode = SessionMode.Required<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputSessionChannel-> IOutputSessionChannel|  
|<xref:System.ServiceModel.Routing.IRequestReplyRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true|IReplyChannel-> IRequestChannel|  
|<xref:System.ServiceModel.Routing.IDuplexSessionRouter>|SessionMode=SessionMode.Required<br /><br /> CallbackContract=typeof(ISimplexSession)<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true<br /><br /> TransactionFlow(TransactionFlowOption.Allowed)|IDuplexSessionChannel-> IDuplexSessionChannel|  
  
## <a name="see-also"></a>Vea también

- [Servicio de enrutamiento](routing-service.md)
- [Introducción al enrutamiento](routing-introduction.md)

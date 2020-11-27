---
title: Extensibilidad de los canales
ms.date: 03/30/2017
ms.assetid: 4cc3b20b-778a-4ae8-b58c-a3822fb13065
ms.openlocfilehash: 1a734c305e2a6f2fc759647ab5bdf380f7c7eeee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253847"
---
# <a name="channels-extensibility"></a>Extensibilidad de los canales

Esta sección contiene ejemplos que muestran los canales personalizados.  
  
## <a name="in-this-section"></a>En esta sección  

 [Canal local](local-channel.md)  
 Muestra el canal local, un canal de transporte WCF que se utiliza para la comunicación dentro del mismo dominio de aplicación.  
  
 [Perfil seguro confiable](reliable-secure-profile.md)  
 Muestra cómo crear WCF y un perfil seguro confiable (RSP).  
  
 [Distribuidor de canal personalizado](custom-channel-dispatcher.md)  
 Muestra cómo crear la pila del canal de manera personalizada implementando <xref:System.ServiceModel.ServiceHostBase> directamente y cómo crear un distribuidor de canal personalizado en un entorno de host web.  
  
 [Canal de fragmentación](chunking-channel.md)  
 Muestra cómo limitar la cantidad de memoria utilizada para almacenar en búfer los mensajes grandes enviados mediante WCF.
  
 [HttpCookieSession](httpcookiesession.md)  
 Muestra cómo crear un canal de protocolo personalizado para usar cookies de HTTP para la administración de sesiones.  
  
 [Interceptador de mensajes personalizados](custom-message-interceptor.md)  
 Muestra cómo implementar un elemento de enlace personalizado que crea generadores de canales y agentes de escucha de canales para interceptar todos los mensajes entrantes y salientes en un punto concreto en la pila de tiempo de ejecución.

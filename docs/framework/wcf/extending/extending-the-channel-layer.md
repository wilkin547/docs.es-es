---
description: Más información acerca de cómo extender la capa de canal
title: Extensión de la capa de canales
ms.date: 03/30/2017
helpviewer_keywords:
- extending channels [WCF]
ms.assetid: 4238db74-2fb6-4dc8-a326-f58527230810
ms.openlocfilehash: 4588a2749127e454801615cc8916d83fc15592bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685587"
---
# <a name="extending-the-channel-layer"></a>Extensión de la capa de canales

La capa de canales es responsable del intercambio de mensajes entre clientes y servicios. Las extensiones de canal pueden implementar nueva funcionalidad de protocolo, como seguridad o funcionalidad de transporte, como implementar un nuevo transporte de red para llevar los mensajes SOAP.  
  
## <a name="in-this-section"></a>En esta sección  

 [Información general del modelo de canales](channel-model-overview.md)  
 Proporciona una información general de alto nivel de qué canales son, las características que proporcionan y cómo funcionan tanto en una aplicación de servicio como de cliente.  
  
 [Desarrollo de canales](developing-channels.md)  
 Describe a fondo las funciones que representan los diversos tipos de infraestructuras de canales, cómo funciona el motor de estado y el ciclo de vida de estado, cómo administrar excepciones y errores, cómo implementar la compatibilidad de metadatos y cómo funcionan los canales con codificadores de mensajes.  
  
 [Codificadores personalizados](custom-encoders.md)  
 Describe el papel que los codificadores del mensaje juegan en los canales y cómo crear uno.  
  
 [Actualizaciones personalizadas de secuencias](custom-stream-upgrades.md)  
 Describe el proceso de actualización de las secuencias proporcionadas mediante transportes orientados a secuencias.

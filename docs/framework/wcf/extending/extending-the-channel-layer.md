---
title: Extensión de la capa de canales
ms.date: 03/30/2017
helpviewer_keywords:
- extending channels [WCF]
ms.assetid: 4238db74-2fb6-4dc8-a326-f58527230810
ms.openlocfilehash: 8d051ff84ea0562b3d7c810b2c884f4d8b787952
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273027"
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

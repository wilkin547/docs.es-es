---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 85bec8255e0d20d6e76ea354e5b8c42b83d7d8e6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598156"
---
# <a name="systemservicemodelmessageprocessingpaused"></a>System.ServiceModel.MessageProcessingPaused
System.ServiceModel.MessageProcessingPaused  
  
## <a name="description"></a>Descripción  
 Se intercambiaron los subprocesos al procesar un mensaje.  
  
 El procesamiento de un mensaje se puede detener por las siguientes razones:  
  
- ConcurrencyMode está establecido como único o reentrante y el servicio está procesando otro mensaje.  
  
- La transacción está habilitada y el servicio está procesando otra transacción.  
  
- El contexto de sincronización no es actual.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)

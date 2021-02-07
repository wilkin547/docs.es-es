---
description: 'Más información sobre: System. ServiceModel. MessageProcessingPaused'
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 77e4742bc5617904136b2ddd9cb90fe886d38b10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716187"
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

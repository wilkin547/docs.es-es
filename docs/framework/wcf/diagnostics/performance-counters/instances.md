---
description: 'Más información acerca de: instancias'
title: Instancias
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 9cd602164816a419b481ff600a7537593d4f500e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655271"
---
# <a name="instances"></a>Instancias

Nombre del contador: instancias.  
  
## <a name="description"></a>Descripción  

 Número de contextos de instancias que el servicio contiene actualmente.  
  
 La mayoría del tiempo, el número de contextos de instancias es idéntico al número de instancias. Sin embargo, los escenarios siguientes son la excepción a esta regla.  
  
- Un método del servicio llama el método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> explícitamente.  
  
- Un <xref:System.ServiceModel.ReleaseInstanceMode> se aplica a una instancia <xref:System.ServiceModel.OperationBehaviorAttribute>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.OperationBehaviorAttribute>

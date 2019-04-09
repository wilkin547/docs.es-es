---
title: Instancias
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 668cfb3026b9ab7259665f5e53873a512b1e2238
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118994"
---
# <a name="instances"></a>Instancias
Nombre del contador: instancias.  
  
## <a name="description"></a>Descripción  
 Número de contextos de instancias que el servicio contiene actualmente.  
  
 La mayoría del tiempo, el número de contextos de instancias es idéntico al número de instancias. Sin embargo, los escenarios siguientes son la excepción a esta regla.  
  
-   Un método del servicio llama el método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> explícitamente.  
  
-   Un <xref:System.ServiceModel.ReleaseInstanceMode> se aplica a una instancia <xref:System.ServiceModel.OperationBehaviorAttribute>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.OperationBehaviorAttribute>

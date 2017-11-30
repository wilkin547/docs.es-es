---
title: "Cómo: Realizar escuchas de solicitudes mediante sondeo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f0e05e3f66d591a28d7e84d358934959764dab6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a>Cómo: Realizar escuchas de solicitudes mediante sondeo
En el ejemplo siguiente se muestra una manera de que el código de usuario puede sondear un token de cancelación a intervalos regulares para ver si se ha solicitado la cancelación desde el subproceso que realiza la llamada. Este ejemplo se utiliza la <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> tipo, pero el mismo patrón se aplica a las operaciones asincrónicas creadas directamente por el <xref:System.Threading.ThreadPool?displayProperty=nameWithType> tipo o el <xref:System.Threading.Thread?displayProperty=nameWithType> tipo.  
  
## <a name="example"></a>Ejemplo  
 El sondeo necesita algún tipo de bucle o código recursivo que periódicamente se puede leer el valor booleano <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> propiedad. Si usas el <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> tipo y está esperando la tarea se complete en el subproceso que realiza la llamada, puede usar el <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> método para comprobar la propiedad y producir la excepción. Con este método, se asegura de que se produce la excepción correcta en respuesta a una solicitud. Si usas un <xref:System.Threading.Tasks.Task>, a continuación, llamar a este método es mejor que iniciar manualmente una <xref:System.OperationCanceledException>. Si no tiene que producir la excepción, puede comprobar la propiedad y volver del método si la propiedad es `true`.  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 Una llamada a <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> es muy rápido y no presenta una sobrecarga significativa en bucles.  
  
 Si se está llamando a <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, solo tiene que comprobar explícitamente la <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> propiedad si tiene otro trabajo pendiente en respuesta a la cancelación además de producir la excepción. En este ejemplo, puede ver que el código realmente tiene acceso a la propiedad dos veces: una vez en el acceso explícito y de nuevo en el <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> método. Sin embargo, dado el hecho de leer el <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> propiedad implica volátil solo una instrucción por acceso de lectura, el acceso de doble no es importante desde la perspectiva del rendimiento. Es preferible al llamar al método en lugar de producir manualmente la <xref:System.OperationCanceledException>.  
  
## <a name="see-also"></a>Vea también  
 [Cancelación en subprocesos administrados](../../../docs/standard/threading/cancellation-in-managed-threads.md)

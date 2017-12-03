---
title: "Cómo: Implementar una operación de servicios asincrónica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cd208cf361b78da7f755bbe77070d440fe07b4ac
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a>Cómo: Implementar una operación de servicios asincrónica
En aplicaciones de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], se puede implementar una operación de servicio de forma asincrónica o sincrónica sin dictar al cliente cómo llamarla. Por ejemplo, las operaciones de servicio asincrónicas pueden realizar llamadas sincrónicamente y a las operaciones de servicio sincrónicas se las puede llamar de manera asincrónica. Para obtener un ejemplo que muestra cómo llamar a una operación de forma asincrónica en una aplicación cliente, consulte [Cómo: llamar a las operaciones de servicio de forma asincrónica](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)]operaciones sincrónicas y asincrónicas, vea [diseñar contratos de servicio](../../../docs/framework/wcf/designing-service-contracts.md) y [sincrónica y operaciones asincrónicas](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md). En este tema se describe la estructura básica de una operación de servicio asincrónica, el código no está completo. Para obtener un ejemplo completo de servicio y el cliente consulte [asincrónico](http://msdn.microsoft.com/en-us/833db946-f511-4f64-a26f-2759a11217c7).  
  
### <a name="implement-a-service-operation-asynchronously"></a>Implementación de una operación de servicio de manera asincrónica  
  
1.  En su contrato de servicio, declare un par de métodos asincrónicos según las instrucciones de diseño asincrónico de .NET. El método `Begin` toma un parámetro, un objeto de devolución de llamada y un objeto de estado, y devuelve un <xref:System.IAsyncResult?displayProperty=nameWithType> y un método `End` correspondiente que toma <xref:System.IAsyncResult?displayProperty=nameWithType> y devuelven el valor devuelto. Para obtener más información acerca de las llamadas asincrónicas, vea [asincrónica Programming Design Patterns](http://go.microsoft.com/fwlink/?LinkId=248221).  
  
2.  Marque el método `Begin` del par de métodos asincrónicos con el atributo <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> y establezca la propiedad <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> en `true`. Por ejemplo, el código siguiente realiza los pasos 1 y 2.  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3.  Implemente el par de método `Begin/End` en su clase de servicio según las instrucciones de diseño asincrónicas. Por ejemplo, el siguiente ejemplo de código muestra una implementación en la que una cadena se escribe en la consola en porciones `Begin` y `End` de la operación de servicio asincrónica y el valor devuelto de la operación `End` se devuelve al cliente. Para obtener el ejemplo de código completo, consulte la sección Ejemplo.  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a>Ejemplo  
 Los siguientes ejemplos de código muestran:  
  
1.  Una interfaz del contrato de servicio con:  
  
    1.  Una operación `SampleMethod` sincrónica.  
  
    2.  Una operación `BeginSampleMethod` asincrónica.  
  
    3.  Una asincrónica `BeginServiceAsyncMethod` / `EndServiceAsyncMethod` par de operaciones.  
  
2.  Una implementación de servicio mediante un objeto <xref:System.IAsyncResult?displayProperty=nameWithType>.  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Diseño de contratos de servicio](../../../docs/framework/wcf/designing-service-contracts.md)  
 [Operaciones sincrónicas y asincrónicas](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)

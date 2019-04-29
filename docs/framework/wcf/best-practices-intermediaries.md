---
title: 'Procedimientos recomendados: intermediarios'
ms.date: 03/30/2017
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
ms.openlocfilehash: 0bd553486bfb89a0ec14c42a1bb7d2ed9c4c540d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608910"
---
# <a name="best-practices-intermediaries"></a>Procedimientos recomendados: intermediarios
Se debe tener cuidado para controlar los errores correctamente al llamar a intermediarios para asegurarse de que los canales en el lado servicio se han cerrado correctamente.  
  
 Considere el caso siguiente. Un cliente realiza una llamada a un intermedio que llama a un servicio de back-end.  El servicio back-end no define ningún contrato de error, de modo que cualquier error de ese servicio se tratará como un error no tipado.  El servicio back-end se produce un <xref:System.ApplicationException> y WCF anula correctamente el canal del servicio. <xref:System.ApplicationException> emerge como <xref:System.ServiceModel.FaultException> que se inicia en el intermediario. El intermediario vuelve a iniciar <xref:System.ApplicationException>. WCF interpreta esto como un error no tipado del intermediario y se lo reenvía al cliente. Al recibir el error, el intermediario y el cliente generan errores en los canales de lado de cliente. Sin embargo, el canal del lado de servicio del intermediario permanece abierto porque WCF no sabe que el error es irrecuperable.  
  
 La recomendación en este escenario es detectar si el error que procede del servicio es irrecuperable y, en tal caso, el intermediario debería producir un error en su canal de lado de servicio como se muestra en el fragmento de código siguiente.  
  
```csharp  
catch (Exception e)  
{  
    bool faulted = service.State == CommunicationState.Faulted;  
    service.Abort();  
    if (faulted)  
    {  
        throw new ApplicationException(e.Message);  
    }  
    else  
    {  
        throw;  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también

- [Control de errores de WCF](../../../docs/framework/wcf/wcf-error-handling.md)
- [Especificación y gestión de errores en contratos y servicios](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)

---
description: 'Más información sobre: control de errores en actividades asincrónicas'
title: Control de errores en actividades asincrónicas
ms.date: 03/30/2017
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
ms.openlocfilehash: df223998737259aca01a4dc18ed9f2a911d80366
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742412"
---
# <a name="error-handling-in-asynchronous-activities"></a>Control de errores en actividades asincrónicas

Proporcionar control de errores en una <xref:System.Activities.AsyncCodeActivity> implica el enrutamiento del error a través del sistema de devolución de llamada de la actividad. Este tema describe cómo obtener un error que se produce en una operación asincrónica de nuevo al host, mediante el ejemplo de la actividad SendMail.  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a>Devolviendo un error que se produce en una actividad asincrónica de nuevo al host  

 Enrutar un error en una operación asincrónica de nuevo al host en el ejemplo de la actividad SendMail implica los pasos siguientes:  
  
- Agregue una propiedad Exception a la clase `SendMailAsyncResult`.  
  
- Copie el error que se produce en esa propiedad en el controlador de eventos `SendCompleted`.  
  
- Produce la excepción en el controlador de eventos `EndExecute`.  
  
 El código resultante es el siguiente.  
  
```csharp  
class SendMailAsyncResult : IAsyncResult  
        {  
            …  
            public Exception Error { get; set; }
            …  
            void SendCompleted(object sender, AsyncCompletedEventArgs e)  
            {  
                Error = e.Error;  
                this.asyncWaitHandle.Set();  
                callback(this);  
            }  
         }  
  
    public sealed class SendMail: AsyncCodeActivity  
    {  
         …  
        protected override void EndExecute(AsyncCodeActivityContext context, IAsyncResult result)  
        {  
            SendMailAsyncResult sendMailResult = result as SendMailAsyncResult;  
            if (sendMailResult != null && sendMailResult.Error != null)  
                throw sendMailResult.Error;
        }  
    }  
```

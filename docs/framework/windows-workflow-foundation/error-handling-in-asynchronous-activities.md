---
title: "Control de errores en actividades asincrónicas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7606aeeeb3e2e583f9a217b78bcae4aebc6d8662
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="error-handling-in-asynchronous-activities"></a><span data-ttu-id="210fb-102">Control de errores en actividades asincrónicas</span><span class="sxs-lookup"><span data-stu-id="210fb-102">Error handling in asynchronous activities</span></span>
<span data-ttu-id="210fb-103">Proporcionar control de errores en una <xref:System.Activities.AsyncCodeActivity> implica el enrutamiento del error a través del sistema de devolución de llamada de la actividad.</span><span class="sxs-lookup"><span data-stu-id="210fb-103">Providing error handling in an <xref:System.Activities.AsyncCodeActivity> involves routing the error through the activity’s callback system.</span></span> <span data-ttu-id="210fb-104">Este tema describe cómo obtener un error que se produce en una operación asincrónica de nuevo al host, mediante el ejemplo de la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="210fb-104">This topic describes how to get an error that is thrown in an asynchronous operation back to the host, using the SendMail activity sample.</span></span>  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a><span data-ttu-id="210fb-105">Devolviendo un error que se produce en una actividad asincrónica de nuevo al host</span><span class="sxs-lookup"><span data-stu-id="210fb-105">Returning an error thrown in an asynchronous activity back to the host</span></span>  
 <span data-ttu-id="210fb-106">Enrutar un error en una operación asincrónica de nuevo al host en el ejemplo de la actividad SendMail implica los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="210fb-106">Routing an error in an asynchronous operation back to the host in the SendMail activity sample involves the following steps:</span></span>  
  
-   <span data-ttu-id="210fb-107">Agregue una propiedad Exception a la clase `SendMailAsyncResult`.</span><span class="sxs-lookup"><span data-stu-id="210fb-107">Add an Exception property to the `SendMailAsyncResult` class.</span></span>  
  
-   <span data-ttu-id="210fb-108">Copie el error que se produce en esa propiedad en el controlador de eventos `SendCompleted`.</span><span class="sxs-lookup"><span data-stu-id="210fb-108">Copy the thrown error to that property in the `SendCompleted` event handler.</span></span>  
  
-   <span data-ttu-id="210fb-109">Produce la excepción en el controlador de eventos `EndExecute`.</span><span class="sxs-lookup"><span data-stu-id="210fb-109">Throw the exception in the `EndExecute` event handler.</span></span>  
  
 <span data-ttu-id="210fb-110">El código resultante es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="210fb-110">The resulting code is as follows.</span></span>  
  
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

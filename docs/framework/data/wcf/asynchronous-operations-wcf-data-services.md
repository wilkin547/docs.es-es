---
title: Operaciones asincrónicas (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
- WCF Data Services, client library
ms.assetid: 679644c7-e3fc-422c-b14a-b44b683900d0
ms.openlocfilehash: 665e424ada24e5e2990eccde7193a91dc039b265
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45743805"
---
# <a name="asynchronous-operations-wcf-data-services"></a>Operaciones asincrónicas (Data Services de WCF)
Las aplicaciones web deben tolerar una latencia superior entre cliente y servidor que las aplicaciones que se ejecutan en redes internas. Para optimizar el rendimiento y la experiencia del usuario de la aplicación, se recomienda usar los métodos asincrónicos de las clases <xref:System.Data.Services.Client.DataServiceContext> y <xref:System.Data.Services.Client.DataServiceQuery%601> cuando se tenga acceso a los servidores de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] en la web.  
  
 Aunque los servidores de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] procesen solicitudes HTTP de forma sincrónica, algunos métodos de las bibliotecas de cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] son sincrónicas y esperan hasta que se complete el intercambio completo de solicitudes y respuestas antes de continuar con la ejecución. Los métodos asincrónicos de las bibliotecas de cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] no esperan a que se complete este intercambio y pueden permitir que la aplicación mantenga una interfaz de usuario que siga respondiendo mientras tanto.  
  
 Puede realizar operaciones asincrónicas mediante el uso de un par de métodos en el <xref:System.Data.Services.Client.DataServiceContext> y <xref:System.Data.Services.Client.DataServiceQuery%601> clases que empiezan por *comenzar* y *final* respectivamente. El *comenzar* métodos registran un delegado al que llama el servicio una vez completada la operación. El *final* se debe llamar a métodos en el delegado registrado para controlar la devolución de llamada desde las operaciones completadas. Cuando se llama a la *final* método para completar una operación asincrónica, debe hacerlo desde la misma <xref:System.Data.Services.Client.DataServiceQuery%601> o <xref:System.Data.Services.Client.DataServiceContext> instancia que usó para comenzar la operación. Cada *comenzar* método toma un `state` parámetro que puede pasar un objeto de estado a la devolución de llamada. Este objeto de estado se recupera de la <xref:System.IAsyncResult> que se suministra con la devolución de llamada y se usa para llamar a la correspondiente *final* método para completar la operación asincrónica. Por ejemplo, cuando se proporciona la instancia de <xref:System.Data.Services.Client.DataServiceQuery%601> como parámetro `state` al llamar al método <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> de la instancia, <xref:System.Data.Services.Client.DataServiceQuery%601> devuelve la misma instancia de <xref:System.IAsyncResult>. A continuación, esta instancia de <xref:System.Data.Services.Client.DataServiceQuery%601> se usa para llamar al método <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> para completar la operación de consulta. Para obtener más información, consulte [Cómo: ejecutar consultas asincrónicas de servicios de datos](../../../../docs/framework/data/wcf/how-to-execute-asynchronous-data-service-queries-wcf-data-services.md).  
  
> [!NOTE]
>  Las bibliotecas de cliente que se proporcionan en .NET Framework para Silverlight solo admiten operaciones asincrónicas. Para obtener más información, consulte [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149).  
  
 Las bibliotecas de cliente de .NET Framework admiten las siguientes operaciones asincrónicas:  
  
|Operación|Métodos|  
|---------------|-------------|  
|Ejecutar una instancia de <xref:System.Data.Services.Client.DataServiceQuery%601>.|-   <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>|  
|Ejecutar una consulta desde la instancia de <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>|  
|Ejecutar una consulta por lotes desde la instancia de <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecuteBatch%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecuteBatch%2A>|  
|Cargar una entidad relacionada en la instancia de <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginLoadProperty%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndLoadProperty%2A>|  
|Guardar los cambios efectuados en los objetos en la instancia de <xref:System.Data.Services.Client.DataServiceContext>|-   <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>|  
  
## <a name="threading-considerations-for-asynchronous-operations"></a>Consideraciones sobre los subprocesos para las operaciones asincrónicas  
 En una aplicación multiproceso, el delegado que se registra como devolución de llamada para la operación asincrónica no se le invoca necesariamente en el mismo subproceso que se usó para llamar a la *comenzar* método, que crea la solicitud inicial. En una aplicación donde se debe invocar la devolución de llamada en un subproceso concreto, debe serializar explícitamente la ejecución de la *final* método, que controla la respuesta para el subproceso deseado. Por ejemplo, en las aplicaciones basadas en Windows Presentation Foundation (WPF) y en las aplicaciones basadas en Silverlight, se deben calcular las referencias a la respuesta para el subproceso de interfaz de usuario mediante el método <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> en el objeto <xref:System.Windows.Threading.Dispatcher>. Para obtener más información, consulte [consultar el servicio de datos (WCF Data Services/Silverlight)](https://msdn.microsoft.com/library/3a7cdc07-c37e-4da2-b98b-c3763fd0970b).  
  
## <a name="see-also"></a>Vea también  
 [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

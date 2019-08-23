---
title: Operaciones asincrónicas (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
- WCF Data Services, client library
ms.assetid: 679644c7-e3fc-422c-b14a-b44b683900d0
ms.openlocfilehash: 01212b859e10ec1bbbb452486ce1aa6a2cecb583
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965827"
---
# <a name="asynchronous-operations-wcf-data-services"></a>Operaciones asincrónicas (Data Services de WCF)
Las aplicaciones web deben tolerar una latencia superior entre cliente y servidor que las aplicaciones que se ejecutan en redes internas. Para optimizar el rendimiento y la experiencia del usuario de la aplicación, se recomienda usar los métodos asincrónicos de las clases <xref:System.Data.Services.Client.DataServiceContext> y <xref:System.Data.Services.Client.DataServiceQuery%601> cuando se tenga acceso a los servidores de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] en la web.  
  
 Aunque los servidores de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] procesen solicitudes HTTP de forma sincrónica, algunos métodos de las bibliotecas de cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] son sincrónicas y esperan hasta que se complete el intercambio completo de solicitudes y respuestas antes de continuar con la ejecución. Los métodos asincrónicos de las bibliotecas de cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] no esperan a que se complete este intercambio y pueden permitir que la aplicación mantenga una interfaz de usuario que siga respondiendo mientras tanto.  
  
 Puede realizar operaciones asincrónicas mediante el uso de un par de métodos en <xref:System.Data.Services.Client.DataServiceContext> las <xref:System.Data.Services.Client.DataServiceQuery%601> clases y que comienzan con *Begin* y *End* respectivamente. Los métodos *Begin* registran un delegado al que llama el servicio cuando se completa la operación. Se debe llamar a los métodos *End* en el delegado registrado para controlar la devolución de llamada desde las operaciones completadas. Al llamar al método *End* para completar una operación asincrónica, debe hacerlo desde la misma <xref:System.Data.Services.Client.DataServiceQuery%601> instancia de o <xref:System.Data.Services.Client.DataServiceContext> que usó para comenzar la operación. Cada método *Begin* toma un `state` parámetro que puede pasar un objeto de estado a la devolución de llamada. Este objeto de estado se recupera del <xref:System.IAsyncResult> que se proporciona con la devolución de llamada y se usa para llamar al método *End* correspondiente para completar la operación asincrónica. Por ejemplo, cuando se proporciona la instancia de <xref:System.Data.Services.Client.DataServiceQuery%601> como parámetro `state` al llamar al método <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> de la instancia, <xref:System.Data.Services.Client.DataServiceQuery%601> devuelve la misma instancia de <xref:System.IAsyncResult>. A continuación, esta instancia de <xref:System.Data.Services.Client.DataServiceQuery%601> se usa para llamar al método <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> para completar la operación de consulta. Para obtener más información, vea [Cómo: Ejecutar consultas](../../../../docs/framework/data/wcf/how-to-execute-asynchronous-data-service-queries-wcf-data-services.md)asincrónicas del servicio de datos.  
  
> [!NOTE]
> Las bibliotecas de cliente que se proporcionan en .NET Framework para Silverlight solo admiten operaciones asincrónicas. Para obtener más información, vea [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149).  
  
 Las bibliotecas de cliente de .NET Framework admiten las siguientes operaciones asincrónicas:  
  
|Operación|Métodos|  
|---------------|-------------|  
|Ejecutar una instancia de <xref:System.Data.Services.Client.DataServiceQuery%601>.|-   <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>|  
|Ejecutar una consulta desde la instancia de <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>|  
|Ejecutar una consulta por lotes desde la instancia de <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecuteBatch%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecuteBatch%2A>|  
|Cargar una entidad relacionada en la instancia de <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginLoadProperty%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndLoadProperty%2A>|  
|Guardar los cambios efectuados en los objetos en la instancia de <xref:System.Data.Services.Client.DataServiceContext>|-   <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>|  
  
## <a name="threading-considerations-for-asynchronous-operations"></a>Consideraciones sobre los subprocesos para las operaciones asincrónicas  
 En una aplicación multiproceso, el delegado que se registra como devolución de llamada para la operación asincrónica no se invoca necesariamente en el mismo subproceso que se usó para llamar al método *Begin* , que crea la solicitud inicial. En una aplicación donde se debe invocar la devolución de llamada en un subproceso concreto, debe serializar explícitamente la ejecución del método *End* , que controla la respuesta, en el subproceso deseado. Por ejemplo, en las aplicaciones basadas en Windows Presentation Foundation (WPF) y en las aplicaciones basadas en Silverlight, se deben calcular las referencias a la respuesta para el subproceso de interfaz de usuario mediante el método <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> en el objeto <xref:System.Windows.Threading.Dispatcher>. Para obtener más información, vea [consultar el servicio de datos (WCF Data Services/Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc903932(v=vs.95)).  
  
## <a name="see-also"></a>Vea también

- [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

---
title: "Operaciones asincr&#243;nicas (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "operaciones asincrónicas [WCF Data Services]"
  - "Servicios de datos de Microsoft WCF, operaciones asincrónicas"
  - "Servicios de datos de Microsoft WCF, biblioteca de cliente"
ms.assetid: 679644c7-e3fc-422c-b14a-b44b683900d0
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Operaciones asincr&#243;nicas (WCF Data Services)
Las aplicaciones web deben tolerar una latencia superior entre cliente y servidor que las aplicaciones que se ejecutan en redes internas.  Para optimizar el rendimiento y la experiencia del usuario de la aplicación, se recomienda usar los métodos asincrónicos de las clases <xref:System.Data.Services.Client.DataServiceContext> y <xref:System.Data.Services.Client.DataServiceQuery%601> cuando se tenga acceso a los servidores de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] en la web.  
  
 Aunque los servidores de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] procesen solicitudes HTTP de forma sincrónica, algunos métodos de las bibliotecas de cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] son sincrónicas y esperan hasta que se complete el intercambio completo de solicitudes y respuestas antes de continuar con la ejecución.  Los métodos asincrónicos de las bibliotecas de cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] no esperan a que se complete este intercambio y pueden permitir que la aplicación mantenga una interfaz de usuario que siga respondiendo mientras tanto.  
  
 Puede realizar operaciones asincrónicas usando un par de métodos de las clases <xref:System.Data.Services.Client.DataServiceQuery%601> y <xref:System.Data.Services.Client.DataServiceContext> cuyos nombres comienzan por *Begin* y *End*, respectivamente.  Los métodos *Begin* registran un delegado al que llama el servicio cuando finaliza la operación.  Se debería llamar a los métodos *End* en el delegado registrado para controlar la devolución de llamada desde las operaciones completadas.  Cuando llame al método *End* para completar una operación asincrónica, debe hacer lo mismo desde la misma instancia de <xref:System.Data.Services.Client.DataServiceQuery%601> o <xref:System.Data.Services.Client.DataServiceContext> que usó para comenzar la operación.  Cada método *Begin* toma un parámetro `state` que puede pasar un objeto de estado a la devolución de llamada.  Este objeto de estado se recupera desde la interfaz <xref:System.IAsyncResult> que se proporciona con la devolución de llamada y se usa para llamar al método *End* correspondiente para completar la operación asincrónica.  Por ejemplo, cuando se proporciona la instancia de <xref:System.Data.Services.Client.DataServiceQuery%601> como parámetro `state` al llamar al método <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> de la instancia, <xref:System.IAsyncResult> devuelve la misma instancia de <xref:System.Data.Services.Client.DataServiceQuery%601>.  A continuación, esta instancia de <xref:System.Data.Services.Client.DataServiceQuery%601> se usa para llamar al método <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> para completar la operación de consulta.  Para obtener más información, consulta [Cómo: Ejecutar consultas de servicio de datos asincrónicos](../../../../docs/framework/data/wcf/how-to-execute-asynchronous-data-service-queries-wcf-data-services.md).  
  
> [!NOTE]
>  Las bibliotecas de cliente que se proporcionan en .NET Framework para Silverlight solo admiten operaciones asincrónicas.  Para obtener más información, vea [WCF Data Services \(Silverlight\)](http://go.microsoft.com/fwlink/?LinkID=143149).  
  
 Las bibliotecas de cliente de .NET Framework admiten las siguientes operaciones asincrónicas:  
  
|Operación|Métodos|  
|---------------|-------------|  
|Ejecutar una instancia de <xref:System.Data.Services.Client.DataServiceQuery%601>.|-   <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>|  
|Ejecutar una consulta desde la instancia de <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>|  
|Ejecutar una consulta por lotes desde la instancia de <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecuteBatch%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecuteBatch%2A>|  
|Cargar una entidad relacionada en la instancia de <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginLoadProperty%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndLoadProperty%2A>|  
|Guardar los cambios efectuados en los objetos en la instancia de <xref:System.Data.Services.Client.DataServiceContext>|-   <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>|  
  
## Consideraciones sobre los subprocesos para las operaciones asincrónicas  
 En una aplicación multiproceso, al delegado que se registra como devolución de llamada para la operación asincrónica no se le invoca necesariamente en el mismo subproceso que se usó para llamar al método *Begin*, encargado de crear la solicitud inicial.  En una aplicación cuya devolución de llamada se debe invocar en un subproceso concreto, debe calcular explícitamente las referencias a la ejecución del método *End*, que controla la respuesta, para el subproceso deseado.  Por ejemplo, en las aplicaciones basadas en Windows Presentation Foundation \(WPF\) y en las aplicaciones basadas en Silverlight, se deben calcular las referencias a la respuesta para el subproceso de interfaz de usuario mediante el método <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> en el objeto <xref:System.Windows.Threading.Dispatcher>.  Para obtener más información, consulta [Querying the Data Service \(WCF Data Services\/Silverlight\)](http://msdn.microsoft.com/es-es/3a7cdc07-c37e-4da2-b98b-c3763fd0970b).  
  
## Vea también  
 [Biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
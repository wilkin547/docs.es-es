---
title: Procedimiento para registrar información sobre servicios
description: Conozca cómo registrar información sobre servicios. Establezca la propiedad AutoLog si quiere que el proyecto de servicio de Windows interactúe con el registro de eventos de la aplicación.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoLog property
- services, logging information
- Windows Service applications, logging information about
- event logs, service applications
- application event logs, service applications
- logs, service applications
ms.assetid: c0d8140f-c055-4d8e-a2e0-37358a550116
ms.openlocfilehash: 0d6c245e3defb7d518093cca904572d3db00fcf8
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608561"
---
# <a name="how-to-log-information-about-services"></a>Procedimiento para registrar información sobre servicios
De forma predeterminada, todos los proyectos de servicio de Windows tienen la capacidad de interactuar con el registro de eventos de la aplicación y escriben información y excepciones en él. Utilice la propiedad <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> para indicar si quiere esta funcionalidad en la aplicación. De forma predeterminada, el registro está activado para cualquier servicio que se cree con la plantilla de proyecto de servicio de Windows. Puede utilizar una forma estática de la clase <xref:System.Diagnostics.EventLog> para escribir información de servicio en un registro sin tener que crear una instancia de un componente <xref:System.Diagnostics.EventLog> ni registrar manualmente un origen.  
  
 El instalador del servicio registra automáticamente cada uno de los servicios del proyecto como un origen de eventos válido con el registro de aplicaciones en el equipo donde está instalado el servicio, cuando el registro está activado. El servicio registra información cada vez que el servicio se inicia, se detiene, se pone en pausa, se reanuda, se instala o se desinstala. También registra los errores que se producen. No es necesario escribir nada de código para escribir entradas en el registro cuando se utiliza el comportamiento predeterminado; el servicio se encarga de ello automáticamente.  
  
 Si quiere escribir en un registro de eventos distinto del registro de aplicaciones, debe establecer la propiedad <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> en `false`, crear su propio registro de eventos personalizado dentro del código de servicios y registrar el servicio como un origen válido de entradas para este registro. Después, debe escribir código para registrar las entradas en el registro cada vez que se produzca una acción que le interese.  
  
> [!NOTE]
> Si utiliza un registro de eventos personalizado y configura la aplicación de servicio para escribir en él, no debe intentar acceder al registro de eventos antes de establecer la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> del servicio en el código. El registro de eventos necesita el valor de esta propiedad para registrar el servicio como un origen válido de eventos.  
  
### <a name="to-enable-default-event-logging-for-your-service"></a>Para habilitar el registro de eventos predeterminado para el servicio  
  
- Establezca la propiedad <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> del componente a `true`.  
  
    > [!NOTE]
    > De manera predeterminada, esta propiedad está establecida en `true`. No necesitará establecerla explícitamente a menos que esté creando procesamientos más complejos, tales como la evaluación de una condición y el posterior establecimiento de la propiedad <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> según el resultado de esa condición.  
  
### <a name="to-disable-event-logging-for-your-service"></a>Para deshabilitar el registro de eventos para el servicio  
  
- Establezca la propiedad <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> del componente a `false`.  
  
     [!code-csharp[VbRadconService#17](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#17)]
     [!code-vb[VbRadconService#17](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#17)]  
  
### <a name="to-set-up-logging-to-a-custom-log"></a>Para configurar el registro en un registro personalizado  
  
1. Establezca la propiedad <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> en `false`.  
  
    > [!NOTE]
    > Debe establecer el valor de <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> en false para poder utilizar un registro personalizado.  
  
2. Configure una instancia de un componente <xref:System.Diagnostics.EventLog> en la aplicación de servicio de Windows.  
  
3. Cree un registro personalizado mediante una llamada al método <xref:System.Diagnostics.EventLog.CreateEventSource%2A> y especifique la cadena de origen y el nombre del archivo de registro que quiere crear.  
  
4. Establezca la propiedad <xref:System.Diagnostics.EventLog.Source%2A> de la instancia de componente <xref:System.Diagnostics.EventLog> en la cadena de origen que creó en el paso 3.  
  
5. Escriba las entradas mediante el acceso al método <xref:System.Diagnostics.EventLog.WriteEntry%2A> en la instancia de componente <xref:System.Diagnostics.EventLog> .  
  
     El código siguiente muestra cómo configurar el registro en un registro personalizado.  
  
    > [!NOTE]
    > En este ejemplo de código, una instancia de un componente <xref:System.Diagnostics.EventLog> se denomina `eventLog1` (`EventLog1` en Visual Basic). Si ha creado una instancia con otro nombre en el paso 2, cambie el código de forma acorde.  
  
     [!code-csharp[VbRadconService#14](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#14)]
     [!code-vb[VbRadconService#14](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#14)]  
    [!code-csharp[VbRadconService#15](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#15)]
    [!code-vb[VbRadconService#15](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#15)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a las aplicaciones de servicios de Windows](introduction-to-windows-service-applications.md)

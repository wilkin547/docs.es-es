---
title: Arquitectura de programación de aplicaciones de servicio
description: Comprenda la arquitectura de programación de aplicaciones de servicio. Las aplicaciones de servicios de Windows se basan en una clase que hereda de System.ServiceProcess.ServiceBase.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceController components, programming architecture
- ServiceBase class, service states
- Windows Service applications, code model
- services, programming architecture
- ServiceController class
- services, states
- ServiceProcessInstaller class, service application code model
- Windows Service applications, states
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
author: ghogen
ms.openlocfilehash: c59ccc5a8b2f11fda9c4734487092c1aabb74908
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925584"
---
# <a name="service-application-programming-architecture"></a>Arquitectura de programación de aplicaciones de servicio
Las aplicaciones de servicios de Windows se basan en una clase que hereda de la clase <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>. Se sustituyen los métodos de esta clase y se define la funcionalidad para que determinen el comportamiento del servicio.  
  
 Las principales clases implicadas en la creación de servicios son:  
  
- <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>: puede reemplazar los métodos de la clase <xref:System.ServiceProcess.ServiceBase> cuando crea un servicio y define el código para determinar cómo funciona el servicio en esta clase heredada.  
  
- <xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType> y <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType>: utilice estas clases para instalar y desinstalar el servicio.  
  
 Además, se puede utilizar una clase llamada <xref:System.ServiceProcess.ServiceController> para manipular el propio servicio. Esta clase no está implicada en la creación de un servicio, pero se puede usar para iniciar y detener el servicio, pasarle comandos y devolver una serie de enumeraciones.  
  
## <a name="defining-your-services-behavior"></a>Definición del comportamiento del servicio  
 En la clase de servicio, se reemplazan las funciones de clase base que determinan lo que sucede cuando se cambia el estado del servicio en el Administrador de control de servicios. La clase <xref:System.ServiceProcess.ServiceBase> expone los siguientes métodos, que puede reemplazar para agregar un comportamiento personalizado.  
  
|Método|Reemplazar por|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|Indique qué acciones se deben tomar cuando el servicio comience a ejecutarse. Debe escribir código en este procedimiento para que el servicio realice un trabajo útil.|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|Indique lo que debería suceder cuando el servicio esté en pausa.|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|Indique lo que debería suceder cuando el servicio deje de funcionar.|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|Indique lo que debería suceder cuando el servicio reanude su funcionamiento normal después de haber sido pausado.|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|Indique lo que debería suceder justo antes de que el sistema se apague, si el servicio se está ejecutando en ese momento.|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|Indique lo que debería suceder cuando el servicio recibe un comando personalizado. Para obtener más información sobre comandos personalizados, consulte MSDN Online.|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|Indique cómo debe responder el servicio cuando se recibe un evento de administración de energía, como una batería baja o una operación suspendida.|  
  
> [!NOTE]
> Estos métodos representan los estados por los que pasa el servicio durante su vigencia; el servicio pasa de un estado a otro. Por ejemplo, nunca conseguirá que el servicio responda a un comando <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> antes de que se haya llamado a <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.  
  
 Hay varias otras propiedades y métodos que son de interés. Se incluyen los siguientes:  
  
- El método <xref:System.ServiceProcess.ServiceBase.Run%2A> en la clase <xref:System.ServiceProcess.ServiceBase>. Este es el punto de entrada principal para el servicio. Cuando crea un servicio utilizando la plantilla de servicio de Windows, el código se inserta en el método `Main` de la aplicación para ejecutar el servicio. El código es similar al siguiente:  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    > Estos ejemplos usan una matriz del tipo <xref:System.ServiceProcess.ServiceBase>, en la que cada servicio que contiene la aplicación puede agregarse, y entonces todos los servicios pueden ejecutarse juntos. Sin embargo, si solo está creando un único servicio, puede optar por no usar la matriz y simplemente declarar un nuevo objeto heredado de <xref:System.ServiceProcess.ServiceBase> y después ejecutarlo. Como ejemplo, vea [Cómo: Escribir servicios mediante programación](how-to-write-services-programmatically.md).  
  
- Una serie de propiedades de la clase <xref:System.ServiceProcess.ServiceBase>. Determinan qué métodos se pueden llamar en el servicio. Por ejemplo, cuando la propiedad <xref:System.ServiceProcess.ServiceBase.CanStop%2A> se establece en `true`, se puede llamar al método <xref:System.ServiceProcess.ServiceBase.OnStop%2A> del servicio. Cuando la propiedad <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> se establece en `true`, se pueden llamar a los métodos <xref:System.ServiceProcess.ServiceBase.OnPause%2A> y <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>. Cuando configure una de estas propiedades en `true`, deberá reemplazar y definir el procesamiento para los métodos asociados.  
  
    > [!NOTE]
    > El servicio debe reemplazar al menos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A> para ser útil.  
  
 También puede utilizar un componente llamado <xref:System.ServiceProcess.ServiceController> para comunicarse con un servicio existente y controlar su comportamiento.  
  
## <a name="see-also"></a>Vea también

- [Introducción a las aplicaciones de servicios de Windows](introduction-to-windows-service-applications.md)
- [Cómo: Creación de servicios de Windows](how-to-create-windows-services.md)

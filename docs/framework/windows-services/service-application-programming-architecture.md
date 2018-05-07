---
title: Arquitectura de programación de aplicaciones de servicio
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
manager: douge
ms.openlocfilehash: f0c760d0f9b65fc9b612a8bee8abb68fa5b4ecae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="service-application-programming-architecture"></a>Arquitectura de programación de aplicaciones de servicio
Las aplicaciones de servicio de Windows se basan en una clase que hereda de la <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> clase. Reemplace los métodos de esta clase y definir la funcionalidad de ellos determinar cómo se comporta el servicio.  
  
 Las clases principales implicados en la creación de servicios son:  
  
-   <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> : Reemplaza métodos desde la <xref:System.ServiceProcess.ServiceBase> clase al crear un servicio y defina el código para determinar cómo funciona el servicio en esta clase heredada.  
  
-   <xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType> y <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> : use estas clases para instalar y desinstalar el servicio.  
  
 Además, una clase denominada <xref:System.ServiceProcess.ServiceController> puede utilizarse para manipular el propio servicio. Esta clase no está implicada en la creación de un servicio, pero puede utilizarse para iniciar y detener el servicio, pasarle comandos y devolver una serie de enumeraciones.  
  
## <a name="defining-your-services-behavior"></a>Definir el comportamiento del servicio.  
 En la clase de servicio, reemplace las funciones de clase base que determinan lo que sucede cuando el estado del servicio se cambia en el Administrador de Control de servicios. La <xref:System.ServiceProcess.ServiceBase> clase expone los métodos siguientes, que se pueden invalidar para agregar comportamiento personalizado.  
  
|Método|Invalidar para|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|Indicar qué acciones deben ejecutarse cuando el servicio comienza a ejecutarse. Debe escribir código en este procedimiento para el servicio realizar trabajo útil.|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|Indicar qué debe ocurrir cuando el servicio está en pausa.|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|Indicar qué debe ocurrir cuando el servicio deja de ejecutarse.|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|Indicar qué debe ocurrir cuando el servicio reanuda el funcionamiento normal después de una pausa.|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|Indicar qué debe ocurrir justo antes de su sistema cerrando, si el servicio se está ejecutando en ese momento.|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|Indicar qué debe ocurrir cuando el servicio recibe un comando personalizado. Para obtener más información sobre los comandos personalizados, consulte MSDN online.|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|Indica cómo debe responder el servicio cuando se recibe un evento de administración de energía, como una operación de suspensión o de batería baja.|  
  
> [!NOTE]
>  Estos métodos representan los Estados que el servicio se mueve a través de su duración; el servicio realice la transición de un estado al siguiente. Por ejemplo, nunca obtendrán el servicio responda a un <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> comando antes de <xref:System.ServiceProcess.ServiceBase.OnStart%2A> se ha llamado.  
  
 Hay varias otras propiedades y métodos que son de interés. Se incluyen los siguientes:  
  
-   El <xref:System.ServiceProcess.ServiceBase.Run%2A> método en la <xref:System.ServiceProcess.ServiceBase> clase. Éste es el punto de entrada principal para el servicio. Cuando se crea un servicio mediante la plantilla de servicio de Windows, el código se inserta en la aplicación `Main` método para ejecutar el servicio. Este código tiene el siguiente aspecto:  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  Estos ejemplos utilizan una matriz de tipo <xref:System.ServiceProcess.ServiceBase>, en la que se puede agregar cada servicio que contenga la aplicación y, a continuación, todos los servicios pueden ejecutar juntos. Si sólo va a crear un único servicio, sin embargo, puede elegir no usar la matriz y declarar simplemente un nuevo objeto heredar <xref:System.ServiceProcess.ServiceBase> y, a continuación, ejecútelo. Para obtener un ejemplo, vea [Cómo: escribir servicios mediante programación](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).  
  
-   Una serie de propiedades de la <xref:System.ServiceProcess.ServiceBase> clase. Determinan qué métodos se pueden llamar en el servicio. Por ejemplo, cuando la <xref:System.ServiceProcess.ServiceBase.CanStop%2A> propiedad está establecida en `true`, el <xref:System.ServiceProcess.ServiceBase.OnStop%2A> se puede llamar el método en su servicio. Cuando el <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> propiedad está establecida en `true`, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> y <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> puede llamar a métodos. Al establecer una de estas propiedades para `true`, a continuación, se debe invalidar y definir los procesos para los métodos asociados.  
  
    > [!NOTE]
    >  El servicio debe reemplazar al menos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A> para ser útil.  
  
 También puede utilizar un componente denominado el <xref:System.ServiceProcess.ServiceController> comunicarse y controlar el comportamiento de un servicio existente.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las aplicaciones de servicios de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Creación de servicios de Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)

---
title: "Service Application Programming Architecture | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ServiceController components, programming architecture"
  - "ServiceBase class, service states"
  - "Windows Service applications, code model"
  - "services, programming architecture"
  - "ServiceController class"
  - "services, states"
  - "ServiceProcessInstaller class, service application code model"
  - "Windows Service applications, states"
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 15
---
# Service Application Programming Architecture
Las aplicaciones de servicio de Windows se basan en una clase que hereda de la clase <xref:System.ServiceProcess.ServiceBase?displayProperty=fullName>.  Reemplace los métodos procedentes de esta clase y defina su funcionalidad para determinar el comportamiento del servicio.  
  
 Las principales clases implicadas en la creación de servicios son las siguientes:  
  
-   <xref:System.ServiceProcess.ServiceBase?displayProperty=fullName>: reemplace los métodos de la clase <xref:System.ServiceProcess.ServiceBase> cuando cree un servicio y defina el código para determinar cómo funciona el servicio en esta clase heredada.  
  
-   <xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=fullName> y <xref:System.ServiceProcess.ServiceInstaller?displayProperty=fullName>: utilice estas clases para instalar y desinstalar su servicio.  
  
 Además, una clase denominada <xref:System.ServiceProcess.ServiceController> se puede utilizar para manipular el servicio.  Esta clase no está implicada en la creación de servicios, pero puede utilizarse para iniciar y detener el servicio, pasarle comandos y devolver una serie de enumeraciones.  
  
## Definir el comportamiento del servicio  
 En la clase de servicio, reemplace las funciones de clase base que determinan lo que ocurre cuando se cambia el estado del servicio en el Administrador de control de servicios.  La clase <xref:System.ServiceProcess.ServiceBase> expone los siguientes métodos, que puede reemplazar para agregar comportamientos personalizados.  
  
|Método|Reemplácelo para|  
|------------|----------------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|Indicar qué acciones deben ejecutarse cuando empieza a funcionar el servicio.  Para que el servicio ejecute un trabajo útil, deberá escribir código en este procedimiento.|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|Indicar qué debe ocurrir cuando se pausa el servicio.|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|Indicar qué debe ocurrir cuando se detenga la ejecución del servicio.|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|Indicar qué debe ocurrir cuando el servicio reanuda su funcionamiento normal tras una pausa.|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|Indicar qué debe ocurrir justo antes de que el sistema se cierre, en caso de que se esté ejecutando el servicio en ese momento.|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|Indicar qué debe ocurrir cuando el servicio reciba un comando personalizado.  Para obtener más información acerca de los comandos personalizados, consulte MSDN Online.|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|Indicar cómo debe responder el servicio cuando se reciba un evento de administración de energía, por ejemplo, una batería agotada o una operación suspendida.|  
  
> [!NOTE]
>  Estos métodos representan los estados a través de los cuales se mueve el servicio a lo largo de su duración, es decir, las transiciones del servicio de un estado al siguiente.  Por ejemplo, no podrá hacer que el servicio responda a un comando <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> antes de llamar a <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.  
  
 Hay otras propiedades y métodos de interés.  Incluyen los siguientes:  
  
-   El método <xref:System.ServiceProcess.ServiceBase.Run%2A> en la clase <xref:System.ServiceProcess.ServiceBase>.  Este es el punto de entrada principal al servicio.  Al crear un servicio mediante la plantilla de servicios de Windows, se inserta código en el método `Main` de la aplicación para ejecutar el servicio.  Este código tiene el siguiente aspecto:  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  Estos ejemplos utilizan una matriz de tipo <xref:System.ServiceProcess.ServiceBase>, a la que puede agregarse cada uno de los servicios que contiene la aplicación para que todos los servicios se puedan ejecutar en conjunto.  No obstante, si sólo va a crear un único servicio, puede elegir no utilizar la matriz y declarar simplemente un nuevo objeto que se herede de <xref:System.ServiceProcess.ServiceBase> y, a continuación, ejecutarlo.  Para obtener un ejemplo, vea [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).  
  
-   Una serie de propiedades de la clase <xref:System.ServiceProcess.ServiceBase>.  Estas propiedades determinan a qué métodos se puede llamar en el servicio.  Por ejemplo, cuando la propiedad <xref:System.ServiceProcess.ServiceBase.CanStop%2A> se establece en `true`, se puede llamar al método <xref:System.ServiceProcess.ServiceBase.OnStop%2A> en su servicio.  Cuando la propiedad <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> se establece en `true`, se puede llamar a los métodos <xref:System.ServiceProcess.ServiceBase.OnPause%2A> y <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>.  Cuando establezca una de estas propiedades en `true`, es recomendable reemplazar y definir los procesos para los métodos asociados.  
  
    > [!NOTE]
    >  Su servicio debe reemplazar al menos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A> para ser útil.  
  
 También puede utilizar un componente denominado <xref:System.ServiceProcess.ServiceController> para comunicarse y controlar el comportamiento de un servicio existente.  
  
## Vea también  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)
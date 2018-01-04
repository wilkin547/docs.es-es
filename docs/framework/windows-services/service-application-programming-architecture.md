---
title: "Arquitectura de programación de aplicaciones de servicio"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 2d44ee323040346437261b51fddb707a30d1de6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="service-application-programming-architecture"></a><span data-ttu-id="e6459-102">Arquitectura de programación de aplicaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="e6459-102">Service Application Programming Architecture</span></span>
<span data-ttu-id="e6459-103">Las aplicaciones de servicio de Windows se basan en una clase que hereda de la <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="e6459-103">Windows Service applications are based on a class that inherits from the <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="e6459-104">Reemplace los métodos de esta clase y definir la funcionalidad de ellos determinar cómo se comporta el servicio.</span><span class="sxs-lookup"><span data-stu-id="e6459-104">You override methods from this class and define functionality for them to determine how your service behaves.</span></span>  
  
 <span data-ttu-id="e6459-105">Las clases principales implicados en la creación de servicios son:</span><span class="sxs-lookup"><span data-stu-id="e6459-105">The main classes involved in service creation are:</span></span>  
  
-   <span data-ttu-id="e6459-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>: Reemplaza métodos desde la <xref:System.ServiceProcess.ServiceBase> clase al crear un servicio y defina el código para determinar cómo funciona el servicio en esta clase heredada.</span><span class="sxs-lookup"><span data-stu-id="e6459-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> — You override methods from the <xref:System.ServiceProcess.ServiceBase> class when creating a service and define the code to determine how your service functions in this inherited class.</span></span>  
  
-   <span data-ttu-id="e6459-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType>y <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> : use estas clases para instalar y desinstalar el servicio.</span><span class="sxs-lookup"><span data-stu-id="e6459-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType> and <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> —You use these classes to install and uninstall your service.</span></span>  
  
 <span data-ttu-id="e6459-108">Además, una clase denominada <xref:System.ServiceProcess.ServiceController> puede utilizarse para manipular el propio servicio.</span><span class="sxs-lookup"><span data-stu-id="e6459-108">In addition, a class named <xref:System.ServiceProcess.ServiceController> can be used to manipulate the service itself.</span></span> <span data-ttu-id="e6459-109">Esta clase no está implicada en la creación de un servicio, pero puede utilizarse para iniciar y detener el servicio, pasarle comandos y devolver una serie de enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="e6459-109">This class is not involved in the creation of a service, but can be used to start and stop the service, pass commands to it, and return a series of enumerations.</span></span>  
  
## <a name="defining-your-services-behavior"></a><span data-ttu-id="e6459-110">Definir el comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="e6459-110">Defining Your Service's Behavior</span></span>  
 <span data-ttu-id="e6459-111">En la clase de servicio, reemplace las funciones de clase base que determinan lo que sucede cuando el estado del servicio se cambia en el Administrador de Control de servicios.</span><span class="sxs-lookup"><span data-stu-id="e6459-111">In your service class, you override base class functions that determine what happens when the state of your service is changed in the Services Control Manager.</span></span> <span data-ttu-id="e6459-112">La <xref:System.ServiceProcess.ServiceBase> clase expone los métodos siguientes, que se pueden invalidar para agregar comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="e6459-112">The <xref:System.ServiceProcess.ServiceBase> class exposes the following methods, which you can override to add custom behavior.</span></span>  
  
|<span data-ttu-id="e6459-113">Método</span><span class="sxs-lookup"><span data-stu-id="e6459-113">Method</span></span>|<span data-ttu-id="e6459-114">Invalidar para</span><span class="sxs-lookup"><span data-stu-id="e6459-114">Override to</span></span>|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|<span data-ttu-id="e6459-115">Indicar qué acciones deben ejecutarse cuando el servicio comienza a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="e6459-115">Indicate what actions should be taken when your service starts running.</span></span> <span data-ttu-id="e6459-116">Debe escribir código en este procedimiento para el servicio realizar trabajo útil.</span><span class="sxs-lookup"><span data-stu-id="e6459-116">You must write code in this procedure for your service to perform useful work.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|<span data-ttu-id="e6459-117">Indicar qué debe ocurrir cuando el servicio está en pausa.</span><span class="sxs-lookup"><span data-stu-id="e6459-117">Indicate what should happen when your service is paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|<span data-ttu-id="e6459-118">Indicar qué debe ocurrir cuando el servicio deja de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="e6459-118">Indicate what should happen when your service stops running.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|<span data-ttu-id="e6459-119">Indicar qué debe ocurrir cuando el servicio reanuda el funcionamiento normal después de una pausa.</span><span class="sxs-lookup"><span data-stu-id="e6459-119">Indicate what should happen when your service resumes normal functioning after being paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|<span data-ttu-id="e6459-120">Indicar qué debe ocurrir justo antes de su sistema cerrando, si el servicio se está ejecutando en ese momento.</span><span class="sxs-lookup"><span data-stu-id="e6459-120">Indicate what should happen just prior to your system shutting down, if your service is running at that time.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|<span data-ttu-id="e6459-121">Indicar qué debe ocurrir cuando el servicio recibe un comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="e6459-121">Indicate what should happen when your service receives a custom command.</span></span> <span data-ttu-id="e6459-122">Para obtener más información sobre los comandos personalizados, consulte MSDN online.</span><span class="sxs-lookup"><span data-stu-id="e6459-122">For more information on custom commands, see MSDN online.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|<span data-ttu-id="e6459-123">Indica cómo debe responder el servicio cuando se recibe un evento de administración de energía, como una operación de suspensión o de batería baja.</span><span class="sxs-lookup"><span data-stu-id="e6459-123">Indicate how the service should respond when a power management event is received, such as a low battery or suspended operation.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="e6459-124">Estos métodos representan los Estados que el servicio se mueve a través de su duración; el servicio realice la transición de un estado al siguiente.</span><span class="sxs-lookup"><span data-stu-id="e6459-124">These methods represent states that the service moves through in its lifetime; the service transitions from one state to the next.</span></span> <span data-ttu-id="e6459-125">Por ejemplo, nunca obtendrán el servicio responda a un <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> comando antes de <xref:System.ServiceProcess.ServiceBase.OnStart%2A> se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="e6459-125">For example, you will never get the service to respond to an <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> command before <xref:System.ServiceProcess.ServiceBase.OnStart%2A> has been called.</span></span>  
  
 <span data-ttu-id="e6459-126">Hay varias otras propiedades y métodos que son de interés.</span><span class="sxs-lookup"><span data-stu-id="e6459-126">There are several other properties and methods that are of interest.</span></span> <span data-ttu-id="e6459-127">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6459-127">These include:</span></span>  
  
-   <span data-ttu-id="e6459-128">El <xref:System.ServiceProcess.ServiceBase.Run%2A> método en la <xref:System.ServiceProcess.ServiceBase> clase.</span><span class="sxs-lookup"><span data-stu-id="e6459-128">The <xref:System.ServiceProcess.ServiceBase.Run%2A> method on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="e6459-129">Éste es el punto de entrada principal para el servicio.</span><span class="sxs-lookup"><span data-stu-id="e6459-129">This is the main entry point for the service.</span></span> <span data-ttu-id="e6459-130">Cuando se crea un servicio mediante la plantilla de servicio de Windows, el código se inserta en la aplicación `Main` método para ejecutar el servicio.</span><span class="sxs-lookup"><span data-stu-id="e6459-130">When you create a service using the Windows Service template, code is inserted in your application's `Main` method to run the service.</span></span> <span data-ttu-id="e6459-131">Este código tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="e6459-131">This code looks like this:</span></span>  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  <span data-ttu-id="e6459-132">Estos ejemplos utilizan una matriz de tipo <xref:System.ServiceProcess.ServiceBase>, en la que se puede agregar cada servicio que contenga la aplicación y, a continuación, todos los servicios pueden ejecutar juntos.</span><span class="sxs-lookup"><span data-stu-id="e6459-132">These examples use an array of type <xref:System.ServiceProcess.ServiceBase>, into which each service your application contains can be added, and then all of the services can be run together.</span></span> <span data-ttu-id="e6459-133">Si sólo va a crear un único servicio, sin embargo, puede elegir no usar la matriz y declarar simplemente un nuevo objeto heredar <xref:System.ServiceProcess.ServiceBase> y, a continuación, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="e6459-133">If you are only creating a single service, however, you might choose not to use the array and simply declare a new object inheriting from <xref:System.ServiceProcess.ServiceBase> and then run it.</span></span> <span data-ttu-id="e6459-134">Para obtener un ejemplo, vea [Cómo: escribir servicios mediante programación](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="e6459-134">For an example, see [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span></span>  
  
-   <span data-ttu-id="e6459-135">Una serie de propiedades de la <xref:System.ServiceProcess.ServiceBase> clase.</span><span class="sxs-lookup"><span data-stu-id="e6459-135">A series of properties on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="e6459-136">Determinan qué métodos se pueden llamar en el servicio.</span><span class="sxs-lookup"><span data-stu-id="e6459-136">These determine what methods can be called on your service.</span></span> <span data-ttu-id="e6459-137">Por ejemplo, cuando la <xref:System.ServiceProcess.ServiceBase.CanStop%2A> propiedad está establecida en `true`, el <xref:System.ServiceProcess.ServiceBase.OnStop%2A> se puede llamar el método en su servicio.</span><span class="sxs-lookup"><span data-stu-id="e6459-137">For example, when the <xref:System.ServiceProcess.ServiceBase.CanStop%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method on your service can be called.</span></span> <span data-ttu-id="e6459-138">Cuando el <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> propiedad está establecida en `true`, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> y <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> puede llamar a métodos.</span><span class="sxs-lookup"><span data-stu-id="e6459-138">When the <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnPause%2A> and <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> methods can be called.</span></span> <span data-ttu-id="e6459-139">Al establecer una de estas propiedades para `true`, a continuación, se debe invalidar y definir los procesos para los métodos asociados.</span><span class="sxs-lookup"><span data-stu-id="e6459-139">When you set one of these properties to `true`, you should then override and define processing for the associated methods.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e6459-140">El servicio debe reemplazar al menos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A> para ser útil.</span><span class="sxs-lookup"><span data-stu-id="e6459-140">Your service must override at least <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> to be useful.</span></span>  
  
 <span data-ttu-id="e6459-141">También puede utilizar un componente denominado el <xref:System.ServiceProcess.ServiceController> comunicarse y controlar el comportamiento de un servicio existente.</span><span class="sxs-lookup"><span data-stu-id="e6459-141">You can also use a component called the <xref:System.ServiceProcess.ServiceController> to communicate with and control the behavior of an existing service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6459-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6459-142">See Also</span></span>  
 [<span data-ttu-id="e6459-143">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="e6459-143">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="e6459-144">Creación de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="e6459-144">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)

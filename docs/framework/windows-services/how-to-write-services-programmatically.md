---
title: "Cómo: Crear servicios mediante programación"
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
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
caps.latest.revision: "21"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 1721417b8d1fc799e6af5d09762ee852d9fbfb03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-services-programmatically"></a><span data-ttu-id="ababc-102">Cómo: Crear servicios mediante programación</span><span class="sxs-lookup"><span data-stu-id="ababc-102">How to: Write Services Programmatically</span></span>
<span data-ttu-id="ababc-103">Si decide no usar la plantilla de proyecto de servicio de Windows, puede escribir sus propios servicios mediante el establecimiento de la herencia y otros elementos de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="ababc-103">If you choose not to use the Windows Service project template, you can write your own services by setting up the inheritance and other infrastructure elements yourself.</span></span> <span data-ttu-id="ababc-104">Cuando se crea un servicio mediante programación, debe realizar varios pasos que la plantilla en caso contrario, se controlan por usted:</span><span class="sxs-lookup"><span data-stu-id="ababc-104">When you create a service programmatically, you must perform several steps that the template would otherwise handle for you:</span></span>  
  
-   <span data-ttu-id="ababc-105">Debe configurar la clase de servicio para que herede de la <xref:System.ServiceProcess.ServiceBase> clase.</span><span class="sxs-lookup"><span data-stu-id="ababc-105">You must set up your service class to inherit from the <xref:System.ServiceProcess.ServiceBase> class.</span></span>  
  
-   <span data-ttu-id="ababc-106">Debe crear un `Main` método para el proyecto de servicio que define los servicios que se va a ejecutar y llamadas el <xref:System.ServiceProcess.ServiceBase.Run%2A> método en ellas.</span><span class="sxs-lookup"><span data-stu-id="ababc-106">You must create a `Main` method for your service project that defines the services to run and calls the <xref:System.ServiceProcess.ServiceBase.Run%2A> method on them.</span></span>  
  
-   <span data-ttu-id="ababc-107">Es necesario reemplazar el <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedimientos y relleno en cualquier código que desee que se ejecuten.</span><span class="sxs-lookup"><span data-stu-id="ababc-107">You must override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures and fill in any code you want them to run.</span></span>  
  
### <a name="to-write-a-service-programmatically"></a><span data-ttu-id="ababc-108">Escribir un servicio mediante programación</span><span class="sxs-lookup"><span data-stu-id="ababc-108">To write a service programmatically</span></span>  
  
1.  <span data-ttu-id="ababc-109">Crear un proyecto vacío y cree una referencia a los espacios de nombres necesarios siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ababc-109">Create an empty project and create a reference to the necessary namespaces by following these steps:</span></span>  
  
    1.  <span data-ttu-id="ababc-110">En **el Explorador de soluciones**, haga clic en el **referencias** nodo y haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="ababc-110">In **Solution Explorer**, right-click the **References** node and click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="ababc-111">En el **.NET Framework** ficha, desplácese a **System.dll** y haga clic en **seleccione**.</span><span class="sxs-lookup"><span data-stu-id="ababc-111">On the **.NET Framework** tab, scroll to **System.dll** and click **Select**.</span></span>  
  
    3.  <span data-ttu-id="ababc-112">Desplácese a **System.ServiceProcess.dll** y haga clic en **seleccione**.</span><span class="sxs-lookup"><span data-stu-id="ababc-112">Scroll to **System.ServiceProcess.dll** and click **Select**.</span></span>  
  
    4.  <span data-ttu-id="ababc-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ababc-113">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="ababc-114">Agregue una clase y configurarlo de modo que heredan de <xref:System.ServiceProcess.ServiceBase>:</span><span class="sxs-lookup"><span data-stu-id="ababc-114">Add a class and configure it to inherit from <xref:System.ServiceProcess.ServiceBase>:</span></span>  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  <span data-ttu-id="ababc-115">Agregue el código siguiente para configurar la clase de servicio:</span><span class="sxs-lookup"><span data-stu-id="ababc-115">Add the following code to configure your service class:</span></span>  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  <span data-ttu-id="ababc-116">Crear un `Main` método para la clase y usarla para definir el servicio que contendrá la clase; `userService1` es el nombre de la clase:</span><span class="sxs-lookup"><span data-stu-id="ababc-116">Create a `Main` method for your class, and use it to define the service your class will contain; `userService1` is the name of the class:</span></span>  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  <span data-ttu-id="ababc-117">Invalidar el <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método y defina los procesos que desea que suceda cuando se inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="ababc-117">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and define any processing you want to occur when your service is started.</span></span>  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  <span data-ttu-id="ababc-118">Reemplazar los otros métodos que desea definir procesos personalizados y escribir código para determinar las acciones que realizará el servicio en cada caso.</span><span class="sxs-lookup"><span data-stu-id="ababc-118">Override any other methods you want to define custom processing for, and write code to determine the actions the service should take in each case.</span></span>  
  
7.  <span data-ttu-id="ababc-119">Agregar los instaladores necesarios para su aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="ababc-119">Add the necessary installers for your service application.</span></span> <span data-ttu-id="ababc-120">Para obtener más información, consulte [Cómo: agregar instaladores a la aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="ababc-120">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
8.  <span data-ttu-id="ababc-121">Compilar el proyecto seleccionando **generar solución** desde el **generar** menú.</span><span class="sxs-lookup"><span data-stu-id="ababc-121">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ababc-122">No presione F5 para ejecutar el proyecto: no se puede ejecutar un proyecto de servicio de esta manera.</span><span class="sxs-lookup"><span data-stu-id="ababc-122">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
9. <span data-ttu-id="ababc-123">Crear un proyecto de instalación y las acciones personalizadas para instalar el servicio.</span><span class="sxs-lookup"><span data-stu-id="ababc-123">Create a setup project and the custom actions to install your service.</span></span> <span data-ttu-id="ababc-124">Para obtener un ejemplo, vea [Tutorial: crear una aplicación de servicio de Windows en el Diseñador de componentes](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="ababc-124">For an example, see [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
10. <span data-ttu-id="ababc-125">Instale el servicio.</span><span class="sxs-lookup"><span data-stu-id="ababc-125">Install the service.</span></span> <span data-ttu-id="ababc-126">Para obtener más información, consulta [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="ababc-126">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ababc-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ababc-127">See Also</span></span>  
 [<span data-ttu-id="ababc-128">Introducción a las aplicaciones de servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="ababc-128">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="ababc-129">Cómo: crear servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="ababc-129">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="ababc-130">Cómo: agregar instaladores a la aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="ababc-130">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="ababc-131">Cómo: registrar información sobre servicios</span><span class="sxs-lookup"><span data-stu-id="ababc-131">How to: Log Information About Services</span></span>](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [<span data-ttu-id="ababc-132">Tutorial: Crear una aplicación de servicio de Windows en el Diseñador de componentes</span><span class="sxs-lookup"><span data-stu-id="ababc-132">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)

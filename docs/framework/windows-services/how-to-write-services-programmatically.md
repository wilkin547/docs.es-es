---
title: Procedimiento para escribir servicios mediante programación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
author: ghogen
ms.openlocfilehash: 5637d569ad5261bff6865af4ab2ed8b7631d2d38
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053559"
---
# <a name="how-to-write-services-programmatically"></a><span data-ttu-id="55700-102">Procedimiento para escribir servicios mediante programación</span><span class="sxs-lookup"><span data-stu-id="55700-102">How to: Write Services Programmatically</span></span>
<span data-ttu-id="55700-103">Si decide no utilizar la plantilla de proyecto de servicio de Windows, puede escribir sus propios servicios configurando la herencia y otros elementos de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="55700-103">If you choose not to use the Windows Service project template, you can write your own services by setting up the inheritance and other infrastructure elements yourself.</span></span> <span data-ttu-id="55700-104">Al crear un servicio mediante programación, debe realizar varios pasos que, de lo contrario, la plantilla los controlaría:</span><span class="sxs-lookup"><span data-stu-id="55700-104">When you create a service programmatically, you must perform several steps that the template would otherwise handle for you:</span></span>  
  
- <span data-ttu-id="55700-105">Debe configurar la clase de servicio para que herede de la clase <xref:System.ServiceProcess.ServiceBase>.</span><span class="sxs-lookup"><span data-stu-id="55700-105">You must set up your service class to inherit from the <xref:System.ServiceProcess.ServiceBase> class.</span></span>  
  
- <span data-ttu-id="55700-106">Debe crear un método `Main` para el proyecto de servicio que defina los servicios que se ejecutarán y llame al método <xref:System.ServiceProcess.ServiceBase.Run%2A> en ellos.</span><span class="sxs-lookup"><span data-stu-id="55700-106">You must create a `Main` method for your service project that defines the services to run and calls the <xref:System.ServiceProcess.ServiceBase.Run%2A> method on them.</span></span>  
  
- <span data-ttu-id="55700-107">Debe reemplazar los procedimientos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A>, y rellenar cualquier código que desee que se ejecute.</span><span class="sxs-lookup"><span data-stu-id="55700-107">You must override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures and fill in any code you want them to run.</span></span>  
  
### <a name="to-write-a-service-programmatically"></a><span data-ttu-id="55700-108">Para escribir un servicio mediante programación</span><span class="sxs-lookup"><span data-stu-id="55700-108">To write a service programmatically</span></span>  
  
1. <span data-ttu-id="55700-109">Cree un proyecto vacío y cree una referencia a los espacios de nombres necesarios mediante estos pasos:</span><span class="sxs-lookup"><span data-stu-id="55700-109">Create an empty project and create a reference to the necessary namespaces by following these steps:</span></span>  
  
    1. <span data-ttu-id="55700-110">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Referencias** y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="55700-110">In **Solution Explorer**, right-click the **References** node and click **Add Reference**.</span></span>  
  
    2. <span data-ttu-id="55700-111">En la pestaña **.NET Framework**, desplácese a **System.dll** y haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="55700-111">On the **.NET Framework** tab, scroll to **System.dll** and click **Select**.</span></span>  
  
    3. <span data-ttu-id="55700-112">Desplácese a even**System.ServiceProcess.dll**  y haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="55700-112">Scroll to **System.ServiceProcess.dll** and click **Select**.</span></span>  
  
    4. <span data-ttu-id="55700-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="55700-113">Click **OK**.</span></span>  
  
2. <span data-ttu-id="55700-114">Agregue una clase y configúrela para que herede de <xref:System.ServiceProcess.ServiceBase>:</span><span class="sxs-lookup"><span data-stu-id="55700-114">Add a class and configure it to inherit from <xref:System.ServiceProcess.ServiceBase>:</span></span>  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3. <span data-ttu-id="55700-115">Agregue el código siguiente para configurar la clase de servicio:</span><span class="sxs-lookup"><span data-stu-id="55700-115">Add the following code to configure your service class:</span></span>  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4. <span data-ttu-id="55700-116">Cree un método `Main` para la clase y utilícelo para definir el servicio que contendrá su clase; `userService1` es el nombre de la clase:</span><span class="sxs-lookup"><span data-stu-id="55700-116">Create a `Main` method for your class, and use it to define the service your class will contain; `userService1` is the name of the class:</span></span>  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5. <span data-ttu-id="55700-117">Reemplace el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y defina cualquier procesamiento que desee que ocurra cuando se inicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="55700-117">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and define any processing you want to occur when your service is started.</span></span>  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6. <span data-ttu-id="55700-118">Reemplace cualquier otro método para el que desee definir un procesamiento personalizado y escriba código para determinar las acciones que debe realizar el servicio en cada caso.</span><span class="sxs-lookup"><span data-stu-id="55700-118">Override any other methods you want to define custom processing for, and write code to determine the actions the service should take in each case.</span></span>  
  
7. <span data-ttu-id="55700-119">Agregar los instaladores necesarios para su aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="55700-119">Add the necessary installers for your service application.</span></span> <span data-ttu-id="55700-120">Para obtener más información, vea [Cómo: Agregar instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="55700-120">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>  
  
8. <span data-ttu-id="55700-121">En el menú **Compilar**, seleccione **Compilar solución** para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="55700-121">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="55700-122">No presione F5 para ejecutar el proyecto: no se puede ejecutar un proyecto de servicio de esta manera.</span><span class="sxs-lookup"><span data-stu-id="55700-122">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
9. <span data-ttu-id="55700-123">Cree un proyecto de instalación y las acciones personalizadas para instalar el servicio.</span><span class="sxs-lookup"><span data-stu-id="55700-123">Create a setup project and the custom actions to install your service.</span></span> <span data-ttu-id="55700-124">Para obtener un ejemplo, vea [Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="55700-124">For an example, see [Walkthrough: Creating a Windows Service Application in the Component Designer](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
10. <span data-ttu-id="55700-125">Instale el servicio.</span><span class="sxs-lookup"><span data-stu-id="55700-125">Install the service.</span></span> <span data-ttu-id="55700-126">Para obtener más información, vea [Cómo: Instalar y desinstalar servicios](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="55700-126">For more information, see [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55700-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="55700-127">See also</span></span>

- [<span data-ttu-id="55700-128">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="55700-128">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="55700-129">Cómo: Creación de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="55700-129">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)
- [<span data-ttu-id="55700-130">Cómo: Adición de instaladores a una aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="55700-130">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="55700-131">Cómo: Registrar información sobre servicios</span><span class="sxs-lookup"><span data-stu-id="55700-131">How to: Log Information About Services</span></span>](how-to-log-information-about-services.md)
- [<span data-ttu-id="55700-132">Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes</span><span class="sxs-lookup"><span data-stu-id="55700-132">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)

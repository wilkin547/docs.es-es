---
title: "How to: Write Services Programmatically | Microsoft Docs"
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
  - "services, creating"
  - "Windows Service applications, creating"
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
caps.latest.revision: 21
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 21
---
# How to: Write Services Programmatically
Si elige no utilizar la plantilla de proyecto Servicio de Windows, puede escribir sus propios servicios configurando la herencia y otros elementos de infraestructura personalmente.  Cuando cree un servicio mediante programación, deberá ejecutar varios pasos que, de no ser así, la plantilla controlaría en su lugar:  
  
-   Debe configurar la clase de servicio para heredar de la clase <xref:System.ServiceProcess.ServiceBase>.  
  
-   Debe crear un método `Main` para el proyecto de servicio que defina los servicios que se van a ejecutar y llame al método <xref:System.ServiceProcess.ServiceBase.Run%2A> de éstos.  
  
-   Debe reemplazar los procedimientos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A> y escribir en ellos el código que desea que ejecuten.  
  
### Para escribir un servicio mediante programación  
  
1.  Cree un proyecto vacío y cree una referencia a los espacios de nombres necesarios siguiendo estos pasos:  
  
    1.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en el nodo **Referencias** y haga clic en **Agregar referencia**.  
  
    2.  En la ficha **.NET Framework**, desplácese a **System.dll** y haga clic en **Seleccionar**.  
  
    3.  Desplácese a **System.ServiceProcess.dll** y haga clic en **Seleccionar**.  
  
    4.  Haga clic en **Aceptar**.  
  
2.  Agregue una clase y configúrela para que herede de <xref:System.ServiceProcess.ServiceBase>:  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  Agregue el código siguiente para configurar la clase de servicio:  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  Cree un método `Main` para su clase y utilícelo para definir el servicio que contendrá la clase; `userService1` es el nombre de la clase:  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  Reemplace el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y defina los procesos que desea que se produzcan cuando se inicie el servicio.  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  Reemplace los demás métodos para los que desea definir procesos personalizados y escriba código para determinar las acciones que el servicio deberá ejecutar en cada caso.  
  
7.  Agregar los instaladores necesarios para su aplicación de servicio.  Para obtener más información, vea [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
8.  Compile el proyecto seleccionando **Compilar solución** en el menú **Compilar**.  
  
    > [!NOTE]
    >  No presione F5 para ejecutar el proyecto; no es posible ejecutar de esta forma un proyecto de servicio.  
  
9. Cree un proyecto de instalación y las acciones personalizadas para instalar el servicio.  Para obtener un ejemplo, vea [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
10. Instale el servicio.  Para obtener más información, vea [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
## Vea también  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)   
 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)   
 [How to: Log Information About Services](../../../docs/framework/windows-services/how-to-log-information-about-services.md)   
 [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
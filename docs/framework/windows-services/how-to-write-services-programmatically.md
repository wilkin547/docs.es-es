---
title: Procedimiento para escribir servicios mediante programación
description: Vea cómo escribir servicios mediante programación a través de la configuración manual de la herencia y otros elementos de infraestructura.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
author: ghogen
ms.openlocfilehash: 9693e3d387f38319519ab04211d8219fe1e5dda1
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925714"
---
# <a name="how-to-write-services-programmatically"></a>Procedimiento para escribir servicios mediante programación
Si decide no utilizar la plantilla de proyecto de servicio de Windows, puede escribir sus propios servicios configurando la herencia y otros elementos de infraestructura. Al crear un servicio mediante programación, debe realizar varios pasos que, de lo contrario, la plantilla los controlaría:  
  
- Debe configurar la clase de servicio para que herede de la clase <xref:System.ServiceProcess.ServiceBase>.  
  
- Debe crear un método `Main` para el proyecto de servicio que defina los servicios que se ejecutarán y llame al método <xref:System.ServiceProcess.ServiceBase.Run%2A> en ellos.  
  
- Debe reemplazar los procedimientos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A>, y rellenar cualquier código que desee que se ejecute.  
  
### <a name="to-write-a-service-programmatically"></a>Para escribir un servicio mediante programación  
  
1. Cree un proyecto vacío y cree una referencia a los espacios de nombres necesarios mediante estos pasos:  
  
    1. En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Referencias** y seleccione **Agregar referencia**.  
  
    2. En la pestaña **.NET Framework**, desplácese a **System.dll** y haga clic en **Seleccionar**.  
  
    3. Desplácese a even**System.ServiceProcess.dll**  y haga clic en **Seleccionar**.  
  
    4. Haga clic en **Aceptar**.  
  
2. Agregue una clase y configúrela para que herede de <xref:System.ServiceProcess.ServiceBase>:  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3. Agregue el código siguiente para configurar la clase de servicio:  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4. Cree un método `Main` para la clase y utilícelo para definir el servicio que contendrá su clase; `userService1` es el nombre de la clase:  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5. Reemplace el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y defina cualquier procesamiento que desee que ocurra cuando se inicie el servicio.  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6. Reemplace cualquier otro método para el que desee definir un procesamiento personalizado y escriba código para determinar las acciones que debe realizar el servicio en cada caso.  
  
7. Agregar los instaladores necesarios para su aplicación de servicio. Para obtener más información, vea [Cómo: Agregar instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md).  
  
8. En el menú **Compilar**, seleccione **Compilar solución** para compilar el proyecto.  
  
    > [!NOTE]
    > No presione F5 para ejecutar el proyecto: no se puede ejecutar un proyecto de servicio de esta manera.  
  
9. Cree un proyecto de instalación y las acciones personalizadas para instalar el servicio. Para obtener un ejemplo, vea [Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
10. Instale el servicio. Para obtener más información, vea [Cómo: Instalar y desinstalar servicios](how-to-install-and-uninstall-services.md).  
  
## <a name="see-also"></a>Vea también

- [Introducción a las aplicaciones de servicios de Windows](introduction-to-windows-service-applications.md)
- [Cómo: Creación de servicios de Windows](how-to-create-windows-services.md)
- [Cómo: Adición de instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md)
- [Cómo: Registrar información sobre servicios](how-to-log-information-about-services.md)
- [Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)

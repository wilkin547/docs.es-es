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
ms.workload: dotnet
ms.openlocfilehash: cdb9c7bba564b71bfba86076218e48610cf73076
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-write-services-programmatically"></a>Cómo: Crear servicios mediante programación
Si decide no usar la plantilla de proyecto de servicio de Windows, puede escribir sus propios servicios mediante el establecimiento de la herencia y otros elementos de la infraestructura. Cuando se crea un servicio mediante programación, debe realizar varios pasos que la plantilla en caso contrario, se controlan por usted:  
  
-   Debe configurar la clase de servicio para que herede de la <xref:System.ServiceProcess.ServiceBase> clase.  
  
-   Debe crear un `Main` método para el proyecto de servicio que define los servicios que se va a ejecutar y llamadas el <xref:System.ServiceProcess.ServiceBase.Run%2A> método en ellas.  
  
-   Es necesario reemplazar el <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedimientos y relleno en cualquier código que desee que se ejecuten.  
  
### <a name="to-write-a-service-programmatically"></a>Escribir un servicio mediante programación  
  
1.  Crear un proyecto vacío y cree una referencia a los espacios de nombres necesarios siguiendo estos pasos:  
  
    1.  En **el Explorador de soluciones**, haga clic en el **referencias** nodo y haga clic en **Agregar referencia**.  
  
    2.  En el **.NET Framework** ficha, desplácese a **System.dll** y haga clic en **seleccione**.  
  
    3.  Desplácese a **System.ServiceProcess.dll** y haga clic en **seleccione**.  
  
    4.  Haga clic en **Aceptar**.  
  
2.  Agregue una clase y configurarlo de modo que heredan de <xref:System.ServiceProcess.ServiceBase>:  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  Agregue el código siguiente para configurar la clase de servicio:  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  Crear un `Main` método para la clase y usarla para definir el servicio que contendrá la clase; `userService1` es el nombre de la clase:  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  Invalidar el <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método y defina los procesos que desea que suceda cuando se inicia el servicio.  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  Reemplazar los otros métodos que desea definir procesos personalizados y escribir código para determinar las acciones que realizará el servicio en cada caso.  
  
7.  Agregar los instaladores necesarios para su aplicación de servicio. Para obtener más información, consulte [Cómo: agregar instaladores a la aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
8.  Compilar el proyecto seleccionando **generar solución** desde el **generar** menú.  
  
    > [!NOTE]
    >  No presione F5 para ejecutar el proyecto: no se puede ejecutar un proyecto de servicio de esta manera.  
  
9. Crear un proyecto de instalación y las acciones personalizadas para instalar el servicio. Para obtener un ejemplo, vea [Tutorial: crear una aplicación de servicio de Windows en el Diseñador de componentes](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
10. Instale el servicio. Para obtener más información, consulta [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las aplicaciones de servicios de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Creación de servicios de Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Adición de instaladores a una aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Registro de información sobre servicios](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)

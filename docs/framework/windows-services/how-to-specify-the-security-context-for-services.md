---
title: "How to: Specify the Security Context for Services | Microsoft Docs"
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
  - "Windows Service applications, security"
  - "security [Visual Studio], contexts"
  - "contexts, Visual Studio security"
  - "security [Visual Studio], service applications"
  - "ServiceProcessInstaller class, security context"
  - "services, security"
  - "ServiceInstaller class, security context"
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 10
---
# How to: Specify the Security Context for Services
De forma predeterminada, los servicios se ejecutan en un contexto de seguridad diferente del contexto del usuario que inició la sesión.  Los servicios se ejecutan en el contexto de la cuenta predeterminada del sistema, denominada `LocalSystem`, que otorga distintos privilegios de acceso a los recursos del sistema que la de usuario.  Puede cambiar este comportamiento para especificar una cuenta de usuario diferente bajo la que deberá ejecutarse el servicio.  
  
 Para establecer el contexto de seguridad manipule la propiedad <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> para el proceso dentro del cual se ejecuta el servicio.  Esta propiedad permite establecer el servicio en uno de estos cuatro tipos de cuenta:  
  
-   `User`, que hace que el sistema solicite un nombre de usuario y contraseña válidos cuando el servicio está instalado y se ejecuta en el contexto de una cuenta especificada por un único usuario de la red;  
  
-   `LocalService`, que se ejecuta en el contexto de una cuenta que actúa como un usuario sin privilegios en el equipo local y presenta credenciales anónimas a cualquier servidor remoto;  
  
-   `LocalSystem`, que se ejecuta en el contexto de una cuenta que proporciona amplios privilegios locales, y muestra las credenciales del equipo a cualquier servidor remoto;  
  
-   `NetworkService`, que se ejecuta en el contexto de una cuenta que actúa como un usuario sin privilegios en el equipo local y presenta credenciales del equipo a cualquier servidor remoto;  
  
 Para obtener más información, vea la enumeración <xref:System.ServiceProcess.ServiceAccount>.  
  
### Para especificar el contexto de seguridad para un servicio  
  
1.  Después de crear el servicio, agregue los instaladores necesarios para él.  Para obtener más información, vea [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
2.  En el diseñador, vaya a la clase `ProjectInstaller` y haga clic en el instalador de proceso de servicio para el servicio con el que está trabajando.  
  
    > [!NOTE]
    >  Para cada aplicación de servicio, hay al menos dos componentes de instalación en la clase `ProjectInstaller`: uno que instala los procesos para todos los servicios del proyecto y otro, para cada servicio que contenga la aplicación.  En esta instancia, desea seleccionar <xref:System.ServiceProcess.ServiceProcessInstaller>.  
  
3.  En la ventana **Propiedades**, establezca la <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> en el valor adecuado.  
  
## Vea también  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)   
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)
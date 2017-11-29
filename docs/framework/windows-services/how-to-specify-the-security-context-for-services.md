---
title: "Cómo: Especificar el contexto de seguridad de los servicios"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 50a9c6ff7f02cda4475aa5390181fa5d410af161
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-security-context-for-services"></a>Cómo: Especificar el contexto de seguridad de los servicios
De forma predeterminada, los servicios se ejecutan en un contexto de seguridad diferente que el usuario ha iniciado la sesión. Se ejecutan en el contexto de la cuenta de sistema de forma predeterminada, los servicios denominado `LocalSystem`, lo que les permitirá diferentes privilegios de acceso a recursos del sistema que el usuario. Puede cambiar este comportamiento para especificar una cuenta de usuario diferente bajo el que debe ejecutarse el servicio.  
  
 Para establecer el contexto de seguridad mediante la manipulación del <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> propiedad para el proceso en el que se ejecuta el servicio. Esta propiedad le permite establecer el servicio en uno de cuatro tipos de cuenta:  
  
-   `User`, que hace que el sistema solicite un nombre de usuario válido y una contraseña cuando el servicio está instalado y se ejecuta en el contexto de una cuenta especificada por un único usuario de la red;  
  
-   `LocalService`, que se ejecuta en el contexto de una cuenta que actúa como un usuario sin privilegios en el equipo local y presenta credenciales anónimas a cualquier servidor remoto;  
  
-   `LocalSystem`, que se ejecuta en el contexto de una cuenta que proporciona amplios privilegios locales y presenta las credenciales del equipo a cualquier servidor remoto;  
  
-   `NetworkService`, que se ejecuta en el contexto de una cuenta que actúa como un usuario sin privilegios en el equipo local y presenta las credenciales del equipo a cualquier servidor remoto.  
  
 Para obtener más información, vea la enumeración <xref:System.ServiceProcess.ServiceAccount>.  
  
### <a name="to-specify-the-security-context-for-a-service"></a>Para especificar el contexto de seguridad para un servicio  
  
1.  Después de crear el servicio, agregar a los instaladores necesarios para él. Para obtener más información, consulte [Cómo: agregar instaladores a la aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
2.  En el diseñador, tener acceso a la `ProjectInstaller` clase y haga clic en el instalador de proceso de servicio para el servicio que está trabajando.  
  
    > [!NOTE]
    >  Para cada aplicación de servicio, hay al menos dos componentes de instalación en la `ProjectInstaller` clase: uno que instala los procesos para todos los servicios en el proyecto y un instalador para cada servicio que contenga la aplicación. En este caso, desea seleccionar <xref:System.ServiceProcess.ServiceProcessInstaller>.  
  
3.  En el **propiedades** ventana, establezca el <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> en el valor adecuado.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las aplicaciones de servicio de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Cómo: agregar instaladores a la aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Cómo: crear servicios de Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)

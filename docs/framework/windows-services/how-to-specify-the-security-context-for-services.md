---
title: Procedimiento para especificar el contexto de seguridad de los servicios
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
author: ghogen
ms.openlocfilehash: dd2a9c4485e151d4cb1c9d5ae3a95a69fcc416d4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053581"
---
# <a name="how-to-specify-the-security-context-for-services"></a>Procedimiento para especificar el contexto de seguridad de los servicios
De forma predeterminada, los servicios se ejecutan en un contexto de seguridad diferente al del usuario que ha iniciado sesión. Los servicios se ejecutan en el contexto de la cuenta del sistema predeterminado, llamada `LocalSystem`, que les da diferentes privilegios de acceso a los recursos del sistema que el usuario. Puede cambiar este comportamiento para especificar una cuenta de usuario diferente bajo la cual se debe ejecutar el servicio.  
  
 Se establece el contexto de seguridad mediante la manipulación de la propiedad <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> para el proceso dentro del cual se ejecuta el servicio. Esta propiedad le permite establecer el servicio en uno de los cuatro tipos de cuenta:  
  
- `User`, lo que hace que el sistema solicite un nombre de usuario y una contraseña válidos cuando el servicio está instalado y se ejecuta en el contexto de una cuenta especificada por un único usuario en la red;  
  
- `LocalService`, que se ejecuta en el contexto de una cuenta que actúa como usuario sin privilegios en el equipo local y presenta credenciales anónimas a cualquier servidor remoto;  
  
- `LocalSystem`, que se ejecuta en el contexto de una cuenta que proporciona amplios privilegios locales y presenta las credenciales del equipo a cualquier servidor remoto;  
  
- Para otras tareas, considere la posibilidad de usar la cuenta `NetworkService`, que actúa como un usuario sin privilegios en el equipo local y presenta credenciales del equipo a cualquier servidor remoto.  
  
 Para obtener más información, vea la enumeración <xref:System.ServiceProcess.ServiceAccount>.  
  
### <a name="to-specify-the-security-context-for-a-service"></a>Para especificar el contexto de seguridad de un servicio  
  
1. Después de crear su servicio, agregue los instaladores necesarios para ello. Para obtener más información, vea [Cómo: Agregar instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md).  
  
2. En el diseñador, acceda a la clase `ProjectInstaller` y haga clic en el instalador del proceso de servicio para el servicio con el que está trabajando.  
  
    > [!NOTE]
    > Para cada aplicación de servicio, hay al menos dos componentes de instalación en la clase `ProjectInstaller`: uno que instala los procesos para todos los servicios del proyecto y un instalador para cada servicio que contiene la aplicación. En este caso, desea seleccionar <xref:System.ServiceProcess.ServiceProcessInstaller>.  
  
3. En la ventana **Propiedades**, establezca <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> al valor adecuado.  
  
## <a name="see-also"></a>Vea también

- [Introducción a las aplicaciones de servicios de Windows](introduction-to-windows-service-applications.md)
- [Cómo: Adición de instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md)
- [Cómo: Creación de servicios de Windows](how-to-create-windows-services.md)

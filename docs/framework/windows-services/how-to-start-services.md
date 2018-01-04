---
title: "Cómo: Iniciar servicios"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 8352edaa9386adc1fbf3057c6e98f5a9cf9ce4a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-start-services"></a>Cómo: Iniciar servicios
Después de instala un servicio, debe estar iniciado. A partir de las llamadas del <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método en la clase de servicio. Por lo general, la <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método define el trabajo útil que realizará el servicio. Una vez iniciado un servicio, permanece activo hasta que se está pausado o detenido manualmente.  
  
 Los servicios se pueden configurar para iniciar automática o manualmente. Se iniciará un servicio que se inicia automáticamente cuando se reinicia el equipo en el que está instalado o se activa por primera vez. Un usuario debe iniciar un servicio que inicia de forma manual.  
  
> [!NOTE]
>  De forma predeterminada, los servicios creados con [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] están configurados para iniciarse manualmente.  
  
 Puede iniciar manualmente un servicio de varias maneras: desde **Explorador de servidores**, desde el **Administrador de Control de servicios**, o desde el código mediante un componente denominado el <xref:System.ServiceProcess.ServiceController>.  
  
 Establece el <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> propiedad en la <xref:System.ServiceProcess.ServiceInstaller> clase para determinar si se debería iniciar un servicio de forma manual o automática.  
  
### <a name="to-specify-how-a-service-should-start"></a>Para especificar cómo debe iniciar un servicio  
  
1.  Después de crear el servicio, agregar a los instaladores necesarios para él. Para obtener más información, consulte [Cómo: agregar instaladores a la aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
2.  En el diseñador, haga clic en el instalador del servicio para el servicio que está trabajando.  
  
3.  En el **propiedades** ventana, establezca el <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> propiedad en uno de los siguientes:  
  
    |Para hacer que el servicio instale|Establezca este valor|  
    |----------------------------------|--------------------|  
    |Cuando se reinicia el equipo|**Automático**|  
    |Cuando el servicio inicia una acción explícita del usuario|**Manual**|  
  
    > [!TIP]
    >  Para evitar que el servicio que se inicia en absoluto, puede establecer la <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> propiedad **deshabilitado**. Podría hacer esto si va a reiniciar un servidor varias veces y desea ahorrar tiempo al impedir que los servicios que normalmente se iniciaría impedir que se inicie.  
  
    > [!NOTE]
    >  Estas y otras propiedades se pueden cambiar después de instala el servicio.  
  
     Hay varias formas de iniciar un servicio que tenga su <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> proceso definida en **Manual** : de **Explorador de servidores**, desde la **Administrador de Control de servicios de Windows**, o desde el código. Es importante tener en cuenta que no todos estos métodos inician realmente el servicio en el contexto de la **Administrador de Control de servicios**; **Explorador de servidores** y métodos de programación de inicio del servicio manipulan realmente el controlador.  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a>Para iniciar manualmente un servicio desde el Explorador de servidores  
  
1.  En **Explorador de servidores**, agregue el servidor que desea si no aparece en la lista. Para obtener más información, vea Cómo: acceso e inicializar el Explorador de explorador de bases de datos de servidor.  
  
2.  Expanda el **servicios** nodo y, a continuación, busque el servicio que desea iniciar.  
  
3.  Haga clic en el nombre del servicio y haga clic en **iniciar**.  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a>Para iniciar manualmente un servicio desde el Administrador de Control de servicios  
  
1.  Abra la **Administrador de Control de servicios** llevando a cabo una de las siguientes acciones:  
  
    -   En Windows XP y 2000 Professional, haga clic en **Mi PC** en el escritorio y, a continuación, haga clic en **administrar**. En el cuadro de diálogo que aparece, expanda el **servicios y aplicaciones** nodo.  
  
         \- o -  
  
    -   En Windows Server 2003 y Windows 2000 Server, haga clic en **iniciar**, seleccione **programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **Services**.  
  
        > [!NOTE]
        >  En Windows NT versión 4.0, puede abrir este cuadro de diálogo de **el Panel de Control**.  
  
     Ahora debería ver su servicio incluidos en el **servicios** sección de la ventana.  
  
2.  Seleccione su servicio en la lista, haga clic en él y, a continuación, haga clic en **iniciar**.  
  
### <a name="to-manually-start-a-service-from-code"></a>Para iniciar manualmente un servicio desde el código  
  
1.  Cree una instancia de la <xref:System.ServiceProcess.ServiceController> clase y configurarlo para que interactúe con el servicio que desea administrar.  
  
2.  Llame al método <xref:System.ServiceProcess.ServiceController.Start%2A> para iniciar el servicio.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las aplicaciones de servicios de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Creación de servicios de Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Adición de instaladores a una aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)

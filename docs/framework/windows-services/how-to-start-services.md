---
title: Procedimiento para iniciar servicios
description: Aprenda varias formas de iniciar servicios. Después de instalar un servicio, debe iniciarse. Al iniciarse, llama al método OnStart en la clase de servicio.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
author: ghogen
ms.openlocfilehash: 4a2f9b291e60b12b1465fbb6bbbd1604572359a7
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925727"
---
# <a name="how-to-start-services"></a>Procedimiento para iniciar servicios

Después de instalar un servicio, debe iniciarse. Al iniciarse, llama al método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> en la clase de servicio. Normalmente, el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> define el trabajo útil que realizará el servicio. Después de que se inicia un servicio, este permanece activo hasta que se pausa o se detiene manualmente.

Los servicios se pueden configurar para que se inicien automática o manualmente. Un servicio que se inicia automáticamente se iniciará cuando se reinicie o encienda por primera vez el equipo en el que está instalado. El usuario debe iniciar un servicio que se inicia manualmente.

> [!NOTE]
> De forma predeterminada, los servicios creados con Visual Studio se inician manualmente.

Hay varias maneras de iniciar un servicio manualmente: desde el **Explorador de servidores**, desde el **Administrador de control de servicios** o desde el código con un componente llamado <xref:System.ServiceProcess.ServiceController>.

Establece la propiedad <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> en la clase <xref:System.ServiceProcess.ServiceInstaller> para determinar si un servicio debe iniciarse manual o automáticamente.

### <a name="to-specify-how-a-service-should-start"></a>Para especificar cómo debe iniciarse un servicio

1. Después de crear su servicio, agregue los instaladores necesarios para ello. Para obtener más información, vea [Cómo: Agregar instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md).

2. En el diseñador, haga clic en el instalador del servicio para el servicio con el que está trabajando.

3. En la ventana **Propiedades**, establezca la propiedad <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> en blanco:

    |Para que el servicio se instale|Establezca ese valor|
    |----------------------------------|--------------------|
    |Cuando se reinicia el equipo|**Automático**|
    |Cuando una acción explícita del usuario inicia el servicio|**Manual**|

    > [!TIP]
    > Para evitar que se inicie el servicio, puede establecer la propiedad <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> en **Deshabilitado**. Puede hacer esto si va a reiniciar un servidor varias veces y quiere ahorrar tiempo evitando que se inicien los servicios que normalmente se iniciarían.

    > [!NOTE]
    > Estas y otras propiedades se pueden cambiar después de instalar el servicio.

    Hay varias formas de iniciar un servicio que tiene el proceso <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> establecido en **Manual**: desde el **Explorador de servidores**, desde el **Administrador de control de servicios**, o desde el código. Es importante indicar que no todos estos métodos inician realmente el servicio en el contexto del **Administrador de control de servicios**, **Explorador de servidores** y los métodos mediante programación para iniciar el servicio manipulan realmente el controlador.

### <a name="to-manually-start-a-service-from-server-explorer"></a>Para iniciar manualmente un servicio desde el Explorador de servidores

1. En el **Explorador de servidores**, agregue el servidor que desea si no aparece en la lista. Para obtener más información, vea el artículo sobre cómo acceder al Explorador de servidores y al Explorador de bases de datos e inicializarlos.

2. Expanda el nodo **Servicios** y, después, busque el servicio que desea iniciar.

3. Haga clic con el botón derecho en el servicio y, después, haga clic en **Detener**.

### <a name="to-manually-start-a-service-from-services-control-manager"></a>Para iniciar manualmente un servicio desde el Administrador de control de servicios

1. Abra el **Administrador de control de servicios** llevando a cabo una de las siguientes acciones:

    - En Windows XP y 2000 Professional, haga clic en **Mi PC** en el escritorio y, después, haga clic en **Administrar**. En el cuadro de diálogo que aparece, expanda el nodo **Servicios y aplicaciones**.

      \- o -

    - En Windows Server 2003 y Windows 2000 Server, haga clic en **Iniciar**, seleccione **Programas**, haga clic en **Herramientas administrativas** y, a continuación, haga clic en **Servicios**.

      > [!NOTE]
      > En Windows NT versión 4.0, puede abrir este cuadro de diálogo desde el **Panel de control**.

    Podrá ver su servicio en la lista de la sección **Servicios** de la ventana.

2. Seleccione su servicio en la lista, haga clic en él con el botón secundario y luego haga clic en **Iniciar**.

### <a name="to-manually-start-a-service-from-code"></a>Para iniciar manualmente un servicio desde el código

1. Cree una instancia de la clase <xref:System.ServiceProcess.ServiceController> y configúrela para que interactúe con el servicio que desea administrar.

2. Llame al método <xref:System.ServiceProcess.ServiceController.Start%2A> para iniciar el servicio.

## <a name="see-also"></a>Vea también

- [Introducción a las aplicaciones de servicios de Windows](introduction-to-windows-service-applications.md)
- [Cómo: Creación de servicios de Windows](how-to-create-windows-services.md)
- [Cómo: Adición de instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md)

---
title: Plantillas de Visual Studio para WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a608575-3535-4190-89da-911e24c8374f
caps.latest.revision: "31"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a659fa3801d52da4fa4837b7df4fea9e4ac6cf5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="wcf-visual-studio-templates"></a>Plantillas de Visual Studio para WCF
Las plantillas para [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] son plantillas de proyecto y de elemento predefinidas que pueden utilizarse en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para generar rápidamente servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y las aplicaciones relacionadas.  
  
## <a name="using-the-wcf-templates"></a>Utilización de las plantillas de WCF  
 Las plantillas para [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] proporcionan una estructura de clases básica para el desarrollo de servicios. En concreto, estas plantillas proporcionan las definiciones básicas para el contrato de servicios y el contrato de datos, así como la implementación y configuración del servicio. Puede utilizar estas plantillas para crear un servicio simple con una interacción de código mínima, además de una unidad de creación para servicios más avanzados.  
  
### <a name="wcf-service-library-project-template"></a>Plantilla de proyecto de biblioteca de servicio WCF  
 El [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] plantilla de proyecto Biblioteca de servicio está disponible en el cuadro de diálogo nuevo proyecto bajo **Visual C# \WCF** y **Visual Basic\WCF**.  
  
 Cuando se crea un nuevo proyecto mediante el **servicio WCF** plantilla, el nuevo proyecto incluye automáticamente los tres archivos siguientes:  
  
-   Archivo de contrato de servicio (IService1.cs o IService1.vb). El archivo de contrato de servicio es una interfaz a la que se aplican los atributos de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Este archivo proporciona una definición de un servicio simple que muestra cómo definir los servicios, e incluye operaciones basadas en parámetros y un ejemplo de contrato de datos simple. Éste es el archivo predeterminado mostrado en el editor de código después de crear un proyecto de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   Archivo de implementación de servicio (Service1.cs o Service1.vb). El archivo de implementación de servicio implementa el contrato definido en el archivo de contrato de servicio.  
  
-   Archivo de configuración de la aplicación (App.config). El archivo de configuración proporciona los elementos básicos de un modelo de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] con un enlace HTTP seguro. Además incluye un punto de conexión para el servicio y habilita el intercambio de metadatos.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]se configura para reconocer el archivo App.config como el archivo de configuración para el proyecto cuando se ejecuta con la [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md), que es la configuración predeterminada. Si hospeda la biblioteca de servicios en un ejecutable, sitúe el código de configuración en el archivo de configuración del ejecutable, ya que los archivos de configuración para DLL no son válidos.  
  
### <a name="wcf-service-application-template"></a>Plantilla Aplicación del servicio de WCF  
 El [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] plantilla de aplicación de servicio está disponible en el cuadro de diálogo nuevo proyecto en **Visual C# \WCF** y **Visual Basic\WCF**.  
  
 Cuando se crea un nuevo proyecto mediante el **servicio de aplicación Web de WCF** plantilla, el proyecto incluye los cuatro archivos siguientes:  
  
-   Archivo de host del servicio (service1.svc).  
  
-   Archivo de contrato de servicio (IService1.cs o IService1.vb).  
  
-   Archivo de implementación de servicio (Service1.cs o Service1.vb).  
  
-   Archivo de configuración web (Web.config).  
  
 La plantilla crea automáticamente un sitio web (que se implementará en un directorio virtual), y hospeda un servicio en él.  
  
### <a name="wcf-web-site-template"></a>Plantilla de sitio web de WCF  
 El [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] plantilla de sitio Web está disponible en el cuadro de diálogo nuevo proyecto en **Visual C# \Web Site\WCF servicio** y **Visual basic\sitio Web\servicio WCF**. Esto crea los mismos archivos que la plantilla Aplicación del servicio de WCF pero los organiza como si fuera un sitio web ASP.NET. Se crean las carpetas App_Code y App_Data.  
  
### <a name="wcf-service-item-template"></a>Plantilla de elementos de servicio WCF  
 La plantilla de elementos de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] es una plantilla personalizada que proporciona una manera rápida de agregar servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] a los proyectos [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] existentes.  
  
 Para usar esta plantilla, vaya a la **el Explorador de soluciones** panel, haga clic en el nombre del proyecto, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento** para iniciar el **Agregar nuevo Elemento** cuadro de diálogo.  
  
 La interfaz de servicio y los archivos de implementación están situados en la carpeta raíz del proyecto.  
  
 La plantilla intenta combinar la sección de configuración del nuevo servicio con el archivo de configuración existente, si sus tipos son compatibles.  
  
 Si el proyecto existente es un proyecto web, también se crea un archivo de host de servicio (service1.svc).  
  
### <a name="wcf-wf-service-project-and-item-template"></a>Plantilla de proyectos y elementos WF del servicio WCF.  
 Estas plantillas crean servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] que hospedan un servicio de flujo de trabajo, que es un flujo de trabajo al que se puede obtener acceso como a un servicio web. Existen plantillas independientes para XAML o modelos de programación imperativos. Con las plantillas, puede crear un flujo de trabajo de equipo secuencial o de estado. Para obtener más información sobre estos tipos de flujo de trabajo, consulte [tutoriales de Windows Workflow Foundation](http://msdn.microsoft.com/en-us/e9705654-bd96-4b56-8d98-f1f118112d97). [!INCLUDE[crabout](../../../includes/crabout-md.md)]crear proyectos de flujo de trabajo, consulte [crear proyectos de flujo de trabajo heredado](/visualstudio/workflow-designer/creating-legacy-workflow-projects).  
  
 El diseñador [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] es más sensible si se utilizan flujos de trabajo de tipo XOML en lugar de los flujos basados en código. El flujo de trabajo de XOML es el tipo de flujo predeterminado que se crea.  
  
### <a name="wcf-syndication-service-library-template"></a>Plantilla Biblioteca de servicio de distribución de WCF  
 Esta plantilla permite exponer la fuente con el formato RSS o ATOM como un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Para obtener más información, consulte [sindicación en WCF](../../../docs/framework/wcf/feature-details/wcf-syndication.md).  
  
#### <a name="changing-the-address-of-the-feed"></a>Cambiar la dirección o la fuente  
 La plantilla de distribución utiliza Internet Explorer durante la ejecución. Cuando hace doble clic en el proyecto en **el Explorador de soluciones** en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], seleccione **propiedades**, a continuación, seleccione la **depurar** ficha y se puede ver la dirección predeterminada de la plantilla. Internet Explorer intenta abrir la fuente en esta dirección.  
  
 Si cambia la dirección de su fuente, también debe cambiar la dirección en la **depurar** ficha. Si no lo hace, Internet Explorer intenta abrir la fuente en la dirección predeterminada y no lo consigue.  
  
### <a name="ajax-enabled-wcf-service-item-template"></a>Plantilla de elementos de servicio WCF con AJAX habilitado  
 Esta plantilla expone un control AJAX como un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Para obtener más información sobre controles de AJAX, consulte el [documentación de control de AJAX](http://go.microsoft.com/fwlink/?LinkId=96717).  
  
### <a name="silverlight-enabled-wcf-service-item-template"></a>Plantilla de elementos de servicio WCF habilitado para Silverlight  
 Esta plantilla crea un servicio web que proporciona datos a un cliente o front-end de Silverlight. La plantilla se puede agregar a un sitio web o proyecto de aplicación web para crear un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], que incluye la configuración y el código del servicio que permiten comunicar con un cliente de Silverlight. A continuación, puede usar **Agregar referencia de servicio** para agregar un proxy de cliente del servicio al cliente e intercambiar datos entre el cliente de Silverlight y el servicio WCF habilitado para Silverlight.  
  
 Para obtener acceso a esta plantilla, haga clic en un proyecto de aplicación Web o sitio Web en **el Explorador de soluciones**, haga clic en **agregar un nuevo elemento**y haga clic en **servicio WCF habilitado para Silverlight**.  
  
> [!NOTE]
>  El servicio WCF habilitado para Silverlight expone un extremo `basicHttpBinding` sin habilitar ninguna configuración de seguridad. Por lo tanto, todos los clientes que se conectan a este servicio pueden obtener información sobre el mismo. Los mensajes que se intercambian entre el servicio y el cliente tampoco están firmados ni cifrados. Para proteger el punto de conexión correctamente, debería usar la autenticación de ASP.NET, HTTPS u otros mecanismos.  
  
## <a name="see-also"></a>Vea también  
 [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [Cliente de prueba de WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)

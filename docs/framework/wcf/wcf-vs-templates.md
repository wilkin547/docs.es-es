---
description: 'Más información sobre: plantillas de Visual Studio para WCF'
title: Plantillas de Visual Studio para WCF
ms.date: 03/30/2017
ms.assetid: 6a608575-3535-4190-89da-911e24c8374f
ms.openlocfilehash: 95d320b2a425ddef7e48f915c8f66d759702ccce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99676370"
---
# <a name="wcf-visual-studio-templates"></a>Plantillas de Visual Studio para WCF

Las plantillas de Windows Communication Foundation (WCF) de Visual Studio son plantillas de proyecto y elemento predefinidas que puede usar en Visual Studio para compilar rápidamente servicios WCF y aplicaciones circundantes.  
  
## <a name="using-the-wcf-templates"></a>Utilización de las plantillas de WCF  

 Las plantillas para WCF de Visual Studio proporcionan una estructura de clases básica para el desarrollo de servicios. En concreto, estas plantillas proporcionan las definiciones básicas para el contrato de servicios y el contrato de datos, así como la implementación y configuración del servicio. Puede utilizar estas plantillas para crear un servicio simple con una interacción de código mínima, además de una unidad de creación para servicios más avanzados.  
  
### <a name="wcf-service-library-project-template"></a>Plantilla de proyecto de biblioteca de servicio WCF  

 La plantilla de proyecto Biblioteca de servicios WCF está disponible en el cuadro de diálogo nuevo proyecto en **Visual C# \WCF** y **Visual Basic\WCF**.  
  
 Al crear un nuevo proyecto con la plantilla de **servicio WCF** , el nuevo proyecto incluye automáticamente los tres archivos siguientes:  
  
- Archivo de contrato de servicio (IService1.cs o IService1.vb). El archivo de contrato de servicio es una interfaz que tiene aplicados los atributos de servicio WCF. Este archivo proporciona una definición de un servicio simple que muestra cómo definir los servicios, e incluye operaciones basadas en parámetros y un ejemplo de contrato de datos simple. Este es el archivo predeterminado que se muestra en el editor de código después de crear un proyecto de servicio WCF.  
  
- Archivo de implementación de servicio (Service1.cs o Service1.vb). El archivo de implementación de servicio implementa el contrato definido en el archivo de contrato de servicio.  
  
- Archivo de configuración de la aplicación (App.config). El archivo de configuración proporciona los elementos básicos de un modelo de servicio WCF con un enlace HTTP seguro. Además incluye un punto de conexión para el servicio y habilita el intercambio de metadatos.  
  
> [!NOTE]
> Visual Studio está configurado para reconocer el archivo App.config como el archivo de configuración para el proyecto cuando se ejecuta mediante el [host de servicio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md), que es la configuración predeterminada. Si hospeda la biblioteca de servicios en un ejecutable, sitúe el código de configuración en el archivo de configuración del ejecutable, ya que los archivos de configuración para DLL no son válidos.  
  
### <a name="wcf-service-application-template"></a>Plantilla Aplicación del servicio de WCF  

 La plantilla aplicación de servicio WCF está disponible en el cuadro de diálogo nuevo proyecto en **Visual C# \WCF** y **Visual Basic\WCF**.  
  
 Al crear un nuevo proyecto con la plantilla de **servicio de aplicación Web de WCF** , el proyecto incluye los cuatro archivos siguientes:  
  
- Archivo de host del servicio (service1.svc).  
  
- Archivo de contrato de servicio (IService1.cs o IService1.vb).  
  
- Archivo de implementación de servicio (Service1.cs o Service1.vb).  
  
- Archivo de configuración web (Web.config).  
  
 La plantilla crea automáticamente un sitio web (que se implementará en un directorio virtual), y hospeda un servicio en él.  
  
### <a name="wcf-web-site-template"></a>Plantilla de sitio web de WCF  

 La plantilla sitio web de WCF está disponible en el cuadro de diálogo nuevo proyecto en **Visual C# \Servicio Web\servicio WCF Service** y **Visual Basic\Web web\servicio WCF Service**. Esto crea los mismos archivos que la plantilla Aplicación del servicio de WCF pero los organiza como si fuera un sitio web ASP.NET. Se crean las carpetas App_Code y App_Data.  
  
### <a name="wcf-service-item-template"></a>Plantilla de elementos de servicio WCF  

 La plantilla de elementos de servicio WCF es una plantilla personalizada que proporciona una manera rápida de agregar servicios WCF a los proyectos de Visual Studio existentes.  
  
 Para usar esta plantilla, vaya al panel **Explorador de soluciones** , haga clic con el botón secundario en el nombre del proyecto, elija **Agregar** y, a continuación, haga clic en **nuevo elemento** para abrir el cuadro de diálogo **Agregar nuevo elemento** .  
  
 La interfaz de servicio y los archivos de implementación están situados en la carpeta raíz del proyecto.  
  
 La plantilla intenta fusionar mediante combinación la sección de configuración del nuevo servicio con el archivo de configuración existente, si sus tipos son compatibles.  
  
 Si el proyecto existente es un proyecto web, también se crea un archivo de host de servicio (service1.svc).  
  
### <a name="wcf-wf-service-project-and-item-template"></a>Plantilla de proyectos y elementos WF del servicio WCF.  

 Estas plantillas crean servicios WCF que hospedan un servicio de flujo de trabajo, que es un flujo de trabajo al que se puede tener acceso como un servicio Web. Existen plantillas independientes para XAML o modelos de programación imperativos. Con las plantillas, puede crear un flujo de trabajo de equipo secuencial o de estado. Para obtener más información sobre estos tipos de flujo de trabajo, consulte [Cómo: crear un flujo de trabajo](../windows-workflow-foundation/how-to-create-a-workflow.md). Para obtener más información sobre la creación de proyectos de flujo de trabajo, vea [crear proyectos de flujo de trabajo heredados](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer).  
  
 El diseñador de Visual Studio tiene mayor capacidad de respuesta cuando se usan flujos de trabajo de tipo XOML en lugar de códigos basados en código. El flujo de trabajo de XOML es el tipo de flujo predeterminado que se crea.  
  
### <a name="wcf-syndication-service-library-template"></a>Plantilla Biblioteca de servicio de distribución de WCF  

 Esta plantilla le permite exponer la fuente en el formato RSS o ATOM como un servicio WCF. Para obtener más información, vea [sindicación de WCF](./feature-details/wcf-syndication.md).  
  
#### <a name="changing-the-address-of-the-feed"></a>Cambiar la dirección o la fuente  

 La plantilla de distribución utiliza Internet Explorer durante la ejecución. Al hacer clic con el botón derecho en el proyecto en el **Explorador de soluciones** de Visual Studio, seleccione **propiedades**, seleccione la pestaña **depurar** y podrá ver la dirección predeterminada de la plantilla. Internet Explorer intenta abrir la fuente en esta dirección.  
  
 Si cambia la dirección de la fuente, también debe cambiar la dirección en la pestaña **depurar** . Si no lo hace, Internet Explorer intenta abrir la fuente en la dirección predeterminada y se produce un error.  
  
### <a name="ajax-enabled-wcf-service-item-template"></a>Plantilla de elementos de servicio WCF con AJAX habilitado  

 Esta plantilla expone un control AJAX como un servicio WCF. Para obtener más información sobre los controles AJAX, consulte la [documentación de control Ajax](/aspnet/ajax/).  
  
### <a name="silverlight-enabled-wcf-service-item-template"></a>Plantilla de elementos de servicio WCF habilitado para Silverlight  

 Esta plantilla crea un servicio web que proporciona datos a un cliente o front-end de Silverlight. La plantilla se puede Agregar a un sitio web o proyecto de aplicación web para crear un servicio WCF, que incluye el código de servicio y la configuración que admiten la comunicación con un cliente de Silverlight. A continuación, puede usar **Agregar referencia de servicio** para agregar un proxy de cliente del servicio al cliente e intercambiar datos entre el cliente de Silverlight y el servicio WCF habilitado para Silverlight.  
  
 Para obtener acceso a esta plantilla, haga clic con el botón secundario en un sitio web o proyecto de aplicación web en **Explorador de soluciones**, haga clic en **Agregar un nuevo elemento** y haga clic en **servicio WCF habilitado para Silverlight**.  
  
> [!NOTE]
> El servicio WCF habilitado para Silverlight expone un punto de conexión `basicHttpBinding` sin habilitar ninguna configuración de seguridad. Por lo tanto, todos los clientes que se conectan a este servicio pueden obtener información sobre el mismo. Los mensajes que se intercambian entre el servicio y el cliente tampoco están firmados ni cifrados. Para proteger el punto de conexión correctamente, debería usar la autenticación de ASP.NET, HTTPS u otros mecanismos.  
  
## <a name="see-also"></a>Vea también

- [Host de servicio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [Cliente de prueba de WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)

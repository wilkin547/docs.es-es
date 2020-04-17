---
title: Plantillas de Visual Studio para WCF
ms.date: 03/30/2017
ms.assetid: 6a608575-3535-4190-89da-911e24c8374f
ms.openlocfilehash: 13183ad5f05350c34eebd025eca3faa7d97644f8
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "81608028"
---
# <a name="wcf-visual-studio-templates"></a>Plantillas de Visual Studio para WCF
Plantillas de Visual Studio de Windows Communication Foundation (WCF) son plantillas de proyecto y elemento predefinidas que puede usar en Visual Studio para compilar rápidamente servicios WCF y aplicaciones circundantes.  
  
## <a name="using-the-wcf-templates"></a>Utilización de las plantillas de WCF  
 Plantillas de WCF Visual Studio proporcionan una estructura de clase básica para el desarrollo de servicios. En concreto, estas plantillas proporcionan las definiciones básicas para el contrato de servicios y el contrato de datos, así como la implementación y configuración del servicio. Puede utilizar estas plantillas para crear un servicio simple con una interacción de código mínima, además de una unidad de creación para servicios más avanzados.  
  
### <a name="wcf-service-library-project-template"></a>Plantilla de proyecto de biblioteca de servicio WCF  
 La plantilla de proyecto de la biblioteca de servicios WCF está disponible en el nuevo cuadro de diálogo del proyecto en **Visual C -WCF** y **Visual Basic-WCF**.  
  
 Al crear un nuevo proyecto mediante la plantilla **de servicio WCF,** el nuevo proyecto incluye automáticamente los tres archivos siguientes:  
  
- Archivo de contrato de servicio (IService1.cs o IService1.vb). El archivo de contrato de servicio es una interfaz que tiene atributos de servicio WCF aplicados. Este archivo proporciona una definición de un servicio simple que muestra cómo definir los servicios, e incluye operaciones basadas en parámetros y un ejemplo de contrato de datos simple. Este es el archivo predeterminado que se muestra en el editor de código después de crear un proyecto de servicio WCF.  
  
- Archivo de implementación de servicio (Service1.cs o Service1.vb). El archivo de implementación de servicio implementa el contrato definido en el archivo de contrato de servicio.  
  
- Archivo de configuración de la aplicación (App.config). El archivo de configuración proporciona los elementos básicos de un modelo de servicio WCF con un enlace HTTP seguro. Además incluye un punto de conexión para el servicio y habilita el intercambio de metadatos.  
  
> [!NOTE]
> Visual Studio está configurado para reconocer el archivo App.config como el archivo de configuración para el proyecto cuando se ejecuta mediante el host de [servicio WCF (WcfSvcHost.exe),](wcf-service-host-wcfsvchost-exe.md)que es la configuración predeterminada. Si hospeda la biblioteca de servicios en un ejecutable, sitúe el código de configuración en el archivo de configuración del ejecutable, ya que los archivos de configuración para DLL no son válidos.  
  
### <a name="wcf-service-application-template"></a>Plantilla Aplicación del servicio de WCF  
 La plantilla de aplicación de servicio WCF está disponible en el cuadro de diálogo Nuevo proyecto en **Visual C -WCF** y **Visual Basic-WCF**.  
  
 Al crear un nuevo proyecto mediante la plantilla de servicio de **aplicación web WCF,** el proyecto incluye los cuatro archivos siguientes:  
  
- Archivo de host del servicio (service1.svc).  
  
- Archivo de contrato de servicio (IService1.cs o IService1.vb).  
  
- Archivo de implementación de servicio (Service1.cs o Service1.vb).  
  
- Archivo de configuración web (Web.config).  
  
 La plantilla crea automáticamente un sitio web (que se implementará en un directorio virtual), y hospeda un servicio en él.  
  
### <a name="wcf-web-site-template"></a>Plantilla de sitio web de WCF  
 La plantilla de sitio Web de WCF está disponible en el cuadro **Visual Basic\Web Site\WCF Service**de diálogo Nuevo proyecto en **Visual C.** Esto crea los mismos archivos que la plantilla Aplicación del servicio de WCF pero los organiza como si fuera un sitio web ASP.NET. Se crean las carpetas App_Code y App_Data.  
  
### <a name="wcf-service-item-template"></a>Plantilla de elementos de servicio WCF  
 La plantilla de elemento de servicio WCF es una plantilla personalizada que proporciona una forma rápida de agregar servicios WCF a los proyectos de Visual Studio existentes.  
  
 Para usar esta plantilla, vaya al **panel Explorador** de soluciones, haga clic con el botón secundario en el nombre del proyecto, seleccione **Agregar**y, a continuación, haga clic en **Nuevo elemento** para iniciar el cuadro de diálogo Agregar **nuevo elemento.**  
  
 La interfaz de servicio y los archivos de implementación están situados en la carpeta raíz del proyecto.  
  
 La plantilla intenta fusionar mediante combinación la sección de configuración del nuevo servicio con el archivo de configuración existente, si sus tipos son compatibles.  
  
 Si el proyecto existente es un proyecto web, también se crea un archivo de host de servicio (service1.svc).  
  
### <a name="wcf-wf-service-project-and-item-template"></a>Plantilla de proyectos y elementos WF del servicio WCF.  
 Estas plantillas crean servicios WCF que hospedan un servicio de flujo de trabajo, que es un flujo de trabajo al que se puede tener acceso como un servicio web. Existen plantillas independientes para XAML o modelos de programación imperativos. Con las plantillas, puede crear un flujo de trabajo de equipo secuencial o de estado. Para obtener más información sobre estos tipos de flujo de trabajo, vea [Cómo: crear un flujo](../windows-workflow-foundation/how-to-create-a-workflow.md)de trabajo . Para obtener más información sobre la creación de proyectos de flujo de trabajo, vea Creación de proyectos de flujo de [trabajo heredados](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer).  
  
 El diseñador de Visual Studio es más sensible cuando se usan flujos de trabajo de tipo XOML en lugar de los basados en código. El flujo de trabajo de XOML es el tipo de flujo predeterminado que se crea.  
  
### <a name="wcf-syndication-service-library-template"></a>Plantilla Biblioteca de servicio de distribución de WCF  
 Esta plantilla le permite exponer la fuente en el formato RSS o ATOM como un servicio WCF. Para obtener más información, vea [Sindicación de WCF](./feature-details/wcf-syndication.md).  
  
#### <a name="changing-the-address-of-the-feed"></a>Cambiar la dirección o la fuente  
 La plantilla de distribución utiliza Internet Explorer durante la ejecución. Al hacer clic con el botón secundario en el proyecto en el Explorador de **soluciones** en Visual Studio, seleccione **Propiedades**y, a continuación, seleccione la pestaña **Depurar** y podrá ver la dirección predeterminada de la plantilla. Internet Explorer intenta abrir la fuente en esta dirección.  
  
 Si cambia la dirección de la fuente, también debe cambiar la dirección en la pestaña **Depurar.** Si no lo hace, Internet Explorer intenta abrir la fuente en la dirección predeterminada y falla.  
  
### <a name="ajax-enabled-wcf-service-item-template"></a>Plantilla de elementos de servicio WCF con AJAX habilitado  
 Esta plantilla expone un control AJAX como un servicio WCF. Para obtener más información sobre los controles AJAX, consulte la documentación del [control AJAX.](/aspnet/ajax/)  
  
### <a name="silverlight-enabled-wcf-service-item-template"></a>Plantilla de elementos de servicio WCF habilitado para Silverlight  
 Esta plantilla crea un servicio web que proporciona datos a un cliente o front-end de Silverlight. La plantilla se puede agregar a un sitio Web o proyecto de aplicación web para crear un servicio WCF, que incluye código de servicio y configuración que admiten la comunicación con un cliente de Silverlight. A continuación, puede usar **Agregar referencia** de servicio para agregar un proxy de cliente del servicio al cliente e intercambiar datos entre el cliente de Silverlight y el servicio WCF habilitado para Silverlight.  
  
 Para tener acceso a esta plantilla, haga clic con el botón secundario en un sitio Web o un proyecto de aplicación web en el **Explorador**de soluciones , haga clic en **Agregar un nuevo elemento**y haga clic en Servicio WCF habilitado para **Silverlight**.  
  
> [!NOTE]
> El servicio WCF habilitado para Silverlight expone un punto de conexión `basicHttpBinding` sin habilitar ninguna configuración de seguridad. Por lo tanto, todos los clientes que se conectan a este servicio pueden obtener información sobre el mismo. Los mensajes que se intercambian entre el servicio y el cliente tampoco están firmados ni cifrados. Para proteger el punto de conexión correctamente, debería usar la autenticación de ASP.NET, HTTPS u otros mecanismos.  
  
## <a name="see-also"></a>Vea también

- [Host de servicio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [Cliente de prueba de WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)

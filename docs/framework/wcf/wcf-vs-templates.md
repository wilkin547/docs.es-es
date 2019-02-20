---
title: Plantillas de Visual Studio para WCF
ms.date: 03/30/2017
ms.assetid: 6a608575-3535-4190-89da-911e24c8374f
ms.openlocfilehash: 72239f9e0e6d7882e6a29222c0b68f3bfd5d89d5
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2019
ms.locfileid: "56443242"
---
# <a name="wcf-visual-studio-templates"></a>Plantillas de Visual Studio para WCF
Las plantillas de Visual Studio de Windows Communication Foundation (WCF) son predefinida proyecto y plantillas de elemento que puede usar en Visual Studio para compilar rápidamente servicios WCF y aplicaciones que lo rodea.  
  
## <a name="using-the-wcf-templates"></a>Utilización de las plantillas de WCF  
 Plantillas de Visual Studio de WCF proporcionan una estructura de clase básica para el desarrollo del servicio. En concreto, estas plantillas proporcionan las definiciones básicas para el contrato de servicios y el contrato de datos, así como la implementación y configuración del servicio. Puede utilizar estas plantillas para crear un servicio simple con una interacción de código mínima, además de una unidad de creación para servicios más avanzados.  
  
### <a name="wcf-service-library-project-template"></a>Plantilla de proyecto de biblioteca de servicio WCF  
 La plantilla de proyecto de biblioteca de servicio WCF está disponible en el cuadro de diálogo nuevo proyecto en **Visual C# \WCF** y **Visual Basic\WCF**.  
  
 Cuando se crea un nuevo proyecto con el **servicio WCF** plantilla, el nuevo proyecto incluye automáticamente los tres archivos siguientes:  
  
-   Archivo de contrato de servicio (IService1.cs o IService1.vb). El archivo de contrato de servicio es una interfaz que tiene los atributos de servicio WCF aplicados. Este archivo proporciona una definición de un servicio simple que muestra cómo definir los servicios, e incluye operaciones basadas en parámetros y un ejemplo de contrato de datos simple. Este es el archivo predeterminado mostrado en el editor de código después de crear un proyecto de servicio WCF.  
  
-   Archivo de implementación de servicio (Service1.cs o Service1.vb). El archivo de implementación de servicio implementa el contrato definido en el archivo de contrato de servicio.  
  
-   Archivo de configuración de la aplicación (App.config). El archivo de configuración proporciona los elementos básicos de un modelo de servicio WCF con un enlace HTTP seguro. Además incluye un punto de conexión para el servicio y habilita el intercambio de metadatos.  
  
> [!NOTE]
>  Visual Studio está configurado para reconocer el archivo App.config como archivo de configuración para el proyecto cuando se ejecuta mediante el [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md), que es la configuración predeterminada. Si hospeda la biblioteca de servicios en un ejecutable, sitúe el código de configuración en el archivo de configuración del ejecutable, ya que los archivos de configuración para DLL no son válidos.  
  
### <a name="wcf-service-application-template"></a>Plantilla Aplicación del servicio de WCF  
 La plantilla de aplicación de servicio WCF está disponible en el cuadro de diálogo nuevo proyecto en **Visual C# \WCF** y **Visual Basic\WCF**.  
  
 Cuando se crea un nuevo proyecto con el **servicio de aplicación Web de WCF** plantilla, el proyecto incluye los cuatro archivos siguientes:  
  
-   Archivo de host del servicio (service1.svc).  
  
-   Archivo de contrato de servicio (IService1.cs o IService1.vb).  
  
-   Archivo de implementación de servicio (Service1.cs o Service1.vb).  
  
-   Archivo de configuración web (Web.config).  
  
 La plantilla crea automáticamente un sitio web (que se implementará en un directorio virtual), y hospeda un servicio en él.  
  
### <a name="wcf-web-site-template"></a>Plantilla de sitio web de WCF  
 La plantilla del sitio Web de WCF está disponible en el cuadro de diálogo nuevo proyecto en **Visual C# \Web Site\WCF servicio** y **Visual basic\sitio Web\servicio WCF**. Esto crea los mismos archivos que la plantilla Aplicación del servicio de WCF pero los organiza como si fuera un sitio web ASP.NET. Se crean las carpetas App_Code y App_Data.  
  
### <a name="wcf-service-item-template"></a>Plantilla de elementos de servicio WCF  
 La plantilla de elemento de servicio de WCF es una plantilla personalizada que proporciona una forma rápida de agregar servicios WCF a los proyectos existentes de Visual Studio.  
  
 Para usar esta plantilla, vaya a la **el Explorador de soluciones** panel, haga clic en el nombre del proyecto, elija **agregar**y, a continuación, haga clic en **nuevo elemento** para iniciar el **Agregar nuevo Elemento** cuadro de diálogo.  
  
 La interfaz de servicio y los archivos de implementación están situados en la carpeta raíz del proyecto.  
  
 La plantilla intenta fusionar mediante combinación la sección de configuración del nuevo servicio con el archivo de configuración existente, si sus tipos son compatibles.  
  
 Si el proyecto existente es un proyecto web, también se crea un archivo de host de servicio (service1.svc).  
  
### <a name="wcf-wf-service-project-and-item-template"></a>Plantilla de proyectos y elementos WF del servicio WCF.  
 Estas plantillas crean servicios WCF que hospedan un servicio de flujo de trabajo, que es un flujo de trabajo que se puede tener acceso como un servicio web. Existen plantillas independientes para XAML o modelos de programación imperativos. Con las plantillas, puede crear un flujo de trabajo de equipo secuencial o de estado. Para obtener más información sobre estos tipos de flujo de trabajo, vea [Cómo: crear un flujo de trabajo](../windows-workflow-foundation/how-to-create-a-workflow.md). Para obtener más información sobre cómo crear proyectos de flujo de trabajo, consulte [crear proyectos de flujo de trabajo heredado](/visualstudio/workflow-designer/creating-legacy-workflow-projects).  
  
 Diseñador de Visual Studio es más sensible si tipo XOML flujos de trabajo se usan en su lugar de código basados en. El flujo de trabajo de XOML es el tipo de flujo predeterminado que se crea.  
  
### <a name="wcf-syndication-service-library-template"></a>Plantilla Biblioteca de servicio de distribución de WCF  
 Esta plantilla permite exponer la fuente con el formato RSS o ATOM como un servicio WCF. Para obtener más información, consulte [redifusión en WCF](../../../docs/framework/wcf/feature-details/wcf-syndication.md).  
  
#### <a name="changing-the-address-of-the-feed"></a>Cambiar la dirección o la fuente  
 La plantilla de distribución utiliza Internet Explorer durante la ejecución. Cuando haga clic en el proyecto en **el Explorador de soluciones** en Visual Studio, seleccione **propiedades**, a continuación, seleccione el **depurar** pestaña y puede ver la dirección predeterminada de la plantilla. Internet Explorer intenta abrir la fuente en esta dirección.  
  
 Si cambia la dirección de su fuente, también debe cambiar la dirección en la **depurar** ficha. Si no lo hace, Internet Explorer intenta abrir la fuente en la dirección predeterminada y no lo consigue.  
  
### <a name="ajax-enabled-wcf-service-item-template"></a>Plantilla de elementos de servicio WCF con AJAX habilitado  
 Esta plantilla expone un control AJAX como un servicio WCF. Para obtener más información sobre los controles AJAX, vea el [documentación del control de AJAX](https://go.microsoft.com/fwlink/?LinkId=96717).  
  
### <a name="silverlight-enabled-wcf-service-item-template"></a>Plantilla de elementos de servicio WCF habilitado para Silverlight  
 Esta plantilla crea un servicio web que proporciona datos a un cliente o front-end de Silverlight. La plantilla se puede agregar a un proyecto de aplicación Web o sitio Web para crear un servicio WCF, que incluye código de servicio y la configuración que admite la comunicación con un cliente de Silverlight. A continuación, puede usar **Add Service Reference** para agregar un proxy de cliente del servicio al cliente e intercambiar datos entre el cliente de Silverlight y el servicio WCF habilitado para Silverlight.  
  
 Para obtener acceso a esta plantilla, haga clic en un proyecto de aplicación Web o sitio Web en **el Explorador de soluciones**, haga clic en **agregar un nuevo elemento**y haga clic en **servicio WCF habilitado para Silverlight**.  
  
> [!NOTE]
>  El servicio WCF habilitado para Silverlight expone un punto de conexión `basicHttpBinding` sin habilitar ninguna configuración de seguridad. Por lo tanto, todos los clientes que se conectan a este servicio pueden obtener información sobre el mismo. Los mensajes que se intercambian entre el servicio y el cliente tampoco están firmados ni cifrados. Para proteger el punto de conexión correctamente, debería usar la autenticación de ASP.NET, HTTPS u otros mecanismos.  
  
## <a name="see-also"></a>Vea también
- [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
- [Cliente de prueba de WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)

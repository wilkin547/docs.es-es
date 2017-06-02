---
title: "Informaci&#243;n general sobre las aplicaciones de explorador XAML de WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "aplicaciones hospedadas en explorador [WPF]"
  - "aplicaciones de explorador XAML de WPF (XBAP)"
  - "aplicaciones de explorador XAML (XBAP)"
  - "XBAP, aplicación de explorador XAML"
ms.assetid: 3a7a86a8-75d5-4898-96b9-73da151e5e16
caps.latest.revision: 47
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 47
---
# Informaci&#243;n general sobre las aplicaciones de explorador XAML de WPF
<a name="introduction"></a> Las [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] combinan las características de aplicaciones web y aplicaciones cliente enriquecidas.  Al igual que las aplicaciones web, las aplicaciones XBAP se pueden implementar en un servidor web e iniciarse desde Internet Explorer o Firefox.  Al igual que las aplicaciones cliente enriquecidas, las aplicaciones XBAP pueden aprovechar las capacidades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  El desarrollo de aplicaciones XBAP también es similar al desarrollo de aplicaciones cliente enriquecidas.  En este tema se proporciona una introducción simple, de alto nivel, al desarrollo de aplicaciones XBAP y se describen las diferencias entre el desarrollo de aplicaciones XBAP y el desarrollo de aplicaciones cliente enriquecidas estándar.  
  
 Este tema contiene las siguientes secciones:  
  
-   [Crear una nueva aplicación de explorador XAML \(XBAP\)](#creating_a_new_xaml_browser_application_xbap)  
  
-   [Implementar una aplicación XBAP](#deploying_a_xbap)  
  
-   [Comunicar con la página web del host](#communicating_with_the_host_web_page)  
  
-   [Consideraciones de seguridad sobre XBAP](#xbap_security_considerations)  
  
-   [Consideraciones sobre el rendimiento del tiempo de inicio de una XBAP](#xbap_start_time_performance_considerations)  
  
<a name="creating_a_new_xaml_browser_application_xbap"></a>   
## Crear una nueva aplicación de explorador XAML \(XBAP\)  
 La manera más sencilla de crear un nuevo proyecto de XBAP es con [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)].  Al crear un nuevo proyecto, seleccione **Aplicación de explorador WPF** en la lista de plantillas.  Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de explorador de WPF](http://msdn.microsoft.com/es-es/72ef4d90-e163-42a1-8df0-ea7ccfd1901f).  
  
 Al ejecutar el proyecto de XBAP, se abre en una ventana del explorador en lugar de en una ventana independiente.  Cuando depura la aplicación XBAP desde [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], la aplicación se ejecuta con permisos de zona de Internet y, por tanto, inicia excepciones de seguridad si se superan esos permisos.  Para obtener más información, vea [Seguridad](../../../../docs/framework/wpf/security-wpf.md) y [Seguridad de confianza parcial de WPF](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
> [!NOTE]
>  Si no está desarrollando con [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] o desea obtener más información sobre los archivos de proyecto, vea [Compilar una aplicación de WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
<a name="deploying_a_xbap"></a>   
## Implementar una aplicación XBAP  
 Al compilar una aplicación XBAP, el resultado incluye los tres archivos siguientes:  
  
|Archivo|Descripción|  
|-------------|-----------------|  
|Ejecutable \(.exe\)|Contiene el código compilado y tiene la extensión .exe.|  
|Manifiesto de aplicación \(.manifest\)|Contiene los metadatos asociados a la aplicación y tiene la extensión .manifest.|  
|Manifiesto de implementación \(.xbap\)|Este archivo contiene la información que [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] emplea para implementar la aplicación y tiene la extensión .xbap.|  
  
 La implementación de aplicaciones XBAP se realiza en un servidor web, por ejemplo [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)]o versiones posteriores.  No es necesario instalar [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] en el servidor web, pero sí tiene que registrar las extensiones de nombre de archivo y los tipos [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Para obtener más información, vea [Configurar IIS 5.0 e IIS 6.0 para implementar aplicaciones de WPF](../../../../docs/framework/wpf/app-development/how-to-configure-iis-5-0-and-iis-6-0-to-deploy-wpf-applications.md).  
  
 Para preparar la aplicación XBAP para la implementación, copie el archivo .exe y los manifiestos asociados al servidor web.  Cree una página HTML que contenga un hipervínculo para abrir el manifiesto de implementación, que es el archivo que tiene la extensión .xbap.  Cuando el usuario haga clic en el vínculo al archivo .xbap, [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] administrará automáticamente los mecanismos de descarga e inicio de la aplicación.  En el código de ejemplo siguiente se muestra una página HTML que contiene un hipervínculo que señala a una aplicación XBAP.  
  
```  
<html>   
  <head></head>  
  <body>   
    <a href="XbapEx.xbap">Click this link to launch the application</a>  
  </body>   
</html>  
  
```  
  
 También puede hospedar una aplicación XBAP en el marco de una página web.  Cree una página web con uno o más marcos.  Establezca la propiedad de origen de un marco en el archivo de manifiesto de implementación.  Si desea usar el mecanismo integrado para la comunicación entre la página web de hospedaje y la aplicación XBAP, debe hospedar la aplicación en un marco.  En el código de ejemplo siguiente se muestra una página HTML con dos marcos; el origen del segundo marco está establecido en una aplicación XBAP.  
  
```  
<html>   
  <head>A page with frames.</head>  
    <frameset cols="50%,50%">   
      <frame src="introduction.htm" >   
      <frame src="XbapEx.xbap" >   
  </frameset>   
</html>  
```  
  
### Borrar aplicaciones XBAP almacenadas en memoria caché  
 En algunas situaciones, después de recompilar e iniciar una aplicación XBAP, puede descubrir que se abre una versión anterior de dicha aplicación XBAP.  Por ejemplo, este comportamiento puede producirse cuando el número de versión del ensamblado de la aplicación XBAP es estático e inicia dicha aplicación desde la línea de comandos.  En este caso, puesto que el número de versión entre la versión almacenada en memoria caché \(la versión que se inició previamente\) y la nueva versión sigue siendo el mismo, no se descarga la nueva versión de la aplicación XBAP.  En su lugar, se carga la versión almacenada en memoria caché.  
  
 En estas situaciones, puede quitar la versión almacenada en memoria caché usando el comando **Mage** \(se instala con Visual Studio o [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)]\) desde el símbolo del sistema.  El siguiente comando borra la memoria caché de la aplicación.  
  
 `Mage.exe -cc`  
  
 Este comando garantiza que se iniciará la versión más reciente de la aplicación XBAP.  Al depurar la aplicación en [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], se debe iniciar la versión más reciente de la aplicación XBAP. En general, se recomienda actualizar el número de versión de implementación con cada compilación.  Para obtener más información sobre Mage, vea [Mage.exe \(Herramienta de generación y edición de manifiestos\)](../../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md).  
  
<a name="communicating_with_the_host_web_page"></a>   
## Comunicar con la página web del host  
 Cuando la aplicación está hospedada en un marco HTML, puede comunicarse con la página web que contiene la aplicación XBAP.  Para ello, debe recuperar la propiedad <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> del objeto <xref:System.Windows.Interop.BrowserInteropHelper>.  Esta propiedad devuelve un objeto de script que representa la ventana HTML.  A continuación, puede tener acceso a las propiedades, métodos y eventos del [objeto de ventana](http://go.microsoft.com/fwlink/?LinkId=160274) usando la sintaxis de punto normal.  También puede tener acceso a métodos de script y a variables globales.  En el ejemplo siguiente se muestra cómo recuperar el objeto de script y cerrar el explorador.  
  
 [!code-csharp[XbapBrowserInterop#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/xbapbrowserinterop/cs/page1.xaml.cs#10)]
 [!code-vb[XbapBrowserInterop#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/xbapbrowserinterop/vb/page1.xaml.vb#10)]  
  
### Depurar aplicaciones XBAP que usan HostScript  
 Si la aplicación XBAP usa el objeto <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> para comunicarse con la ventana HTML, debe especificar dos configuraciones para ejecutar y depurar la aplicación en [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].  La aplicación debe tener acceso a su sitio de origen y debe iniciar la aplicación con la página HTML que contiene la aplicación XBAP.  En los pasos siguientes se describe cómo comprobar estos dos valores:  
  
1.  En Visual Studio, abra las propiedades del proyecto.  
  
2.  En la pestaña **Seguridad**, haga clic en **Opciones avanzadas**.  
  
     Aparecerá el cuadro de diálogo Configuración de seguridad avanzada.  
  
3.  Asegúrese de que la casilla **Conceder acceso a la aplicación al sitio de origen** esté activada y haga clic en **Aceptar**.  
  
4.  En la pestaña **Depurar**, seleccione la opción **Iniciar explorador con la dirección URL** y especifique la dirección URL para la página HTML que contiene la aplicación XBAP.  
  
5.  En Internet Explorer, haga clic en el botón **Herramientas** y seleccione **Opciones de Internet**.  
  
     Aparecerá el cuadro de diálogo Opciones de Internet.  
  
6.  Haga clic en la ficha **Opciones avanzadas**.  
  
7.  En la lista **Configuración** de **Seguridad**, active la casilla **Permitir que el contenido activo se ejecute en los archivos de Mi PC**.  
  
8.  Haga clic en **Aceptar**.  
  
     Los cambios surtirán efecto cuando reinicie Internet Explorer.  
  
> [!CAUTION]
>  Al habilitar el contenido activo en Internet Explorer, se puede poner en riesgo el equipo.  Para obtener más información, vea [Características de seguridad y privacidad de Internet Explorer](http://go.microsoft.com/fwlink/?LinkId=179286).  Si no desea cambiar la configuración de seguridad de Internet Explorer, puede iniciar la página HTML desde un servidor y adjuntar el depurador de [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] al proceso.  
  
<a name="xbap_security_considerations"></a>   
## Consideraciones de seguridad sobre XBAP  
 Las aplicaciones XBAP suelen ejecutarse en un recinto de seguridad de confianza parcial que esté restringido al conjunto de permisos de la zona de Internet.  Por tanto, la implementación debe admitir el subconjunto de elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que se admiten en la zona de Internet o debe elevar los permisos de la aplicación.  Para obtener más información, vea [Seguridad](../../../../docs/framework/wpf/security-wpf.md).  
  
 Cuando usa un control <xref:System.Windows.Controls.WebBrowser> en la aplicación, WPF crea internamente instancias del control ActiveX WebBrowser nativo.  Cuando se trata de una aplicación XBAP de confianza parcial que se ejecuta en Internet Explorer, el control ActiveX se ejecuta en un subproceso dedicado del proceso de Internet Explorer.  Por tanto, se aplican las limitaciones siguientes:  
  
-   El control <xref:System.Windows.Controls.WebBrowser> debe proporcionar un comportamiento similar al del explorador del host, incluyendo las restricciones de seguridad.  Algunas de estas restricciones de seguridad se pueden controlar mediante la configuración de seguridad de Internet Explorer.  Para obtener más información, vea [Seguridad](../../../../docs/framework/wpf/security-wpf.md).  
  
-   Se produce una excepción cuando una aplicación XBAP se carga entre dominios en una página HTML.  
  
-   La entrada está en un subproceso independiente del <xref:System.Windows.Controls.WebBrowser> de WPF, por lo que no se pueden interceptar las acciones del teclado y no se comparte el estado del IME.  
  
-   El control de tiempo o el orden de navegación pueden ser diferentes porque el control ActiveX se ejecuta en otro subproceso.  Por ejemplo, la navegación hasta una página no siempre se cancela iniciando otra solicitud de navegación.  
  
-   Un control ActiveX personalizado puede tener dificultades con la comunicación porque la aplicación WPF se está ejecutando en un subproceso independiente.  
  
-   No se genera el evento <xref:System.Windows.Interop.HwndHost.MessageHook> porque <xref:System.Windows.Interop.HwndHost> no puede crear subclases de ninguna ventana que se ejecuta en otro subproceso o proceso.  
  
### Crear una aplicación XBAP de plena confianza  
 Si la aplicación XBAP necesita plena confianza, puede cambiar el proyecto para habilitar este permiso.  En los pasos siguientes se describe cómo habilitar la plena confianza:  
  
1.  En Visual Studio, abra las propiedades del proyecto.  
  
2.  En la pestaña **Seguridad**, seleccione la opción **Aplicación de plena confianza**.  
  
 Este valor realiza las modificaciones siguientes:  
  
-   En el archivo del proyecto, el valor del elemento `<TargetZone>` se cambia a `Custom`.  
  
-   En el manifiesto de aplicación \(app.manifest\), se agrega un atributo `Unrestricted="true"` al elemento `PermissionSet`.  
  
    ```  
    <PermissionSet class="System.Security.PermissionSet"   
        version="1"   
        ID="Custom"   
        SameSite="site"   
        Unrestricted="true"   
    />  
    ```  
  
### Implementar una aplicación XBAP de plena confianza  
 Al implementar una aplicación XBAP de plena confianza que no sigue el modelo de implementación de confianza de ClickOnce, el comportamiento cuando el usuario ejecute la aplicación dependerá de la zona de seguridad.  En algunos casos, el usuario recibirá una advertencia cuando intente instalarla.  El usuario puede continuar o cancelar la instalación.  En la tabla siguiente se describe el comportamiento de la aplicación para cada zona de seguridad y lo que tiene que hacer para que la aplicación reciba plena confianza.  
  
|Zona de seguridad|Comportamiento|Obtener plena confianza|  
|-----------------------|--------------------|-----------------------------|  
|Equipo local|Plena confianza automática|No se requiere ninguna acción.|  
|Intranet y sitios de confianza|Solicitar plena confianza|Firmar la aplicación XBAP con un certificado para que el usuario vea el origen en el indicador.|  
|Internet|Se produce un error "Confianza no concedida"|Firmar la aplicación XBAP con un certificado.|  
  
> [!NOTE]
>  El comportamiento descrito en la tabla anterior es para las aplicaciones XBAP de plena confianza que no siguen el modelo de implementación de confianza de ClickOnce.  
  
 Se recomienda emplear el modelo de implementación de confianza de ClickOnce para implementar una aplicación XBAP de plena confianza.  Este modelo le permite conceder automáticamente plena confianza a la aplicación XBAP, cualquiera que sea la zona de seguridad, por lo que no se pregunta al usuario.  Como parte de este modelo, debe firmar la aplicación con un certificado de un publicador de confianza.  Para obtener más información, vea [Información general sobre la implementación de aplicaciones de confianza](../Topic/Trusted%20Application%20Deployment%20Overview.md) e [Introducción a la firma de código](http://go.microsoft.com/fwlink/?LinkId=166327).  
  
<a name="xbap_start_time_performance_considerations"></a>   
## Consideraciones sobre el rendimiento del tiempo de inicio de una XBAP  
 Un aspecto importante del rendimiento de una aplicación XBAP es su tiempo de inicio.  Si una aplicación XBAP es la primera aplicación de WPF que se carga, el tiempo de *inicio en frío* puede ser de diez segundos o más.  Esto se debe a que WPF representa la página de progreso, y es preciso iniciar en frío tanto CLR como WPF para mostrar la aplicación.  
  
 A partir de [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], el tiempo de inicio en frío de una aplicación XBAP se reduce mostrando una página de progreso no administrada al principio del ciclo de implementación. La página de progreso se muestra casi en el momento de iniciar la aplicación, porque la muestra el código de hospedaje nativo y se representa en HTML.  
  
 Además, la simultaneidad mejorada de la secuencia de descarga de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] reduce el tiempo de inicio en hasta un diez por ciento.  Una vez que se ha efectuado la descarga y validación de manifiestos de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], se inicia la descarga de la aplicación y la barra de progreso empieza a actualizarse.  
  
## Vea también  
 [Configurar Visual Studio para depurar una aplicación de explorador XAML y llamar a un servicio Web](../../../../docs/framework/wpf/app-development/configure-vs-to-debug-a-xaml-browser-to-call-a-web-service.md)   
 [Implementar una aplicación de WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)
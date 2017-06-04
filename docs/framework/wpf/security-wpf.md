---
title: "Seguridad (WPF) | Microsoft Docs"
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
  - "seguridad de aplicaciones [WPF]"
  - "seguridad de aplicaciones hospedadas en explorador [WPF]"
  - "controles de característica [WPF], seguridad"
  - "configuración de seguridad de Internet Explorer [WPF]"
  - "archivos XAML separados [WPF], comportamiento de espacio aislado"
  - "seguridad de navegación [WPF]"
  - "WebBrowser (control) [WPF], seguridad"
  - "seguridad de WPF"
  - "archivos XAML [WPF], comportamiento de espacio aislado"
  - "seguridad de XBAP [WPF]"
ms.assetid: ee1baea0-3611-4e36-9ad6-fcd5205376fb
caps.latest.revision: 38
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Seguridad (WPF)
<a name="introduction"></a> Al desarrollar aplicaciones de [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] independientes y hospedadas en explorador, debe considerar el modelo de seguridad. Las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] independientes se ejecutan con permisos no restringidos \(conjunto de permisos [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] **FullTrust**\), si se implementaron con Windows Installer \(.msi\), XCopy o [!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)].  No se admite la implementación de confianza parcial de aplicaciones WPF independientes con ClickOnce.  Sin embargo, una aplicación host de plena confianza puede crear un <xref:System.AppDomain> de confianza parcial mediante el modelo de complementos de .NET Framework.  Para obtener más información, vea [Información general sobre los complementos de WPF](../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 Las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] hospedadas en explorador se hospedan en [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)] o Firefox y pueden ser [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)] o documentos de [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] independientes. Para obtener más información, vea [Información general sobre las aplicaciones de explorador XAML de WPF](../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
 De manera predeterminada, las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] hospedadas en explorador se ejecutan dentro de un recinto de seguridad de confianza parcial, que se limita al conjunto de permisos de zona **Internet** de [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] predeterminado.  Con ello, las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] hospedadas en explorador se aíslan de manera eficaz del equipo cliente, del mismo modo que cabría esperar que se aíslen las aplicaciones web típicas.  Un XBAP puede elevar los privilegios hasta Plena confianza dependiendo de la zona de seguridad de la dirección URL de implementación y la configuración de seguridad del cliente.  Para obtener más información, vea [Seguridad de confianza parcial de WPF](../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
 En este tema se describe el modelo de seguridad para aplicaciones de [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] independientes y hospedadas por explorador.  
  
 Este tema contiene las siguientes secciones:  
  
-   [Navegación segura](#SafeTopLevelNavigation)  
  
-   [Configuración de seguridad del software de exploración web](#InternetExplorerSecuritySettings)  
  
-   [Controles de características y control WebBrowser](#webbrowser_control_and_feature_controls)  
  
-   [Deshabilitar los ensamblados APTCA para las aplicaciones cliente de confianza parcial](#APTCA)  
  
-   [Comportamiento en espacio aislado de archivos XAML independientes](#LooseContentSandboxing)  
  
-   [Recursos para desarrollar aplicaciones WPF que promueven la seguridad](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>   
## Navegación segura  
 Para las [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)], en [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] se distingue entre dos tipos de navegación: de aplicación y de explorador.  
  
 La *navegación de aplicación* es el desplazamiento por los elementos de contenido dentro de una aplicación hospedada en un explorador.  La *navegación de explorador* es el desplazamiento que cambia el contenido y dirección URL de un explorador.  La relación entre la navegación de la aplicación \(normalmente XAML\) y la navegación del explorador \(normalmente HTML\) se muestra en la siguiente ilustración:  
  
 ![Diagrama de navegación](../../../docs/framework/wpf/media/safetoplevelnavigationfigure.png "SafeTopLevelNavigationFigure")  
  
 El tipo de contenido que se considera seguro para que una [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] pueda navegar a él se determina principalmente en función de si se usa la navegación de aplicación o de explorador.  
  
<a name="Application_Navigation_Security"></a>   
### Seguridad de la navegación de aplicación  
 La navegación de aplicación se considera segura si se puede identificar mediante un pack [!INCLUDE[TLA2#tla_uri](../../../includes/tla2sharptla-uri-md.md)], que admite cuatro tipos de contenido:  
  
|Tipo de contenido|Descripción|Ejemplo de URI|  
|-----------------------|-----------------|--------------------|  
|Recurso|Archivos que se agregan a un proyecto con un tipo de compilación de **Recurso**.|`pack://application:,,,/MyResourceFile.xaml`|  
|Content|Archivos que se agregan a un proyecto con un tipo de compilación de **Contenido**.|`pack://application:,,,/MyContentFile.xaml`|  
|Sitio de origen|Archivos que se agregan a un proyecto con un tipo de compilación de **Ninguno**.|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|Código de aplicación|Recursos de XAML que tienen código compilado subyacente.<br /><br /> O bien<br /><br /> Archivos XAML que se agregan a un proyecto con un tipo de compilación de **Página**.|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
>  Para obtener más información sobre los archivos de datos de aplicación y los pack [!INCLUDE[TLA2#tla_uri#plural](../../../includes/tla2sharptla-urisharpplural-md.md)], consulte [Archivos de recursos, contenido y datos de aplicaciones de WPF](../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).  
  
 A los archivos de estos tipos de contenido puede navegar el usuario o mediante programación:  
  
-   **Navegación por parte del usuario**.  El usuario navega haciendo clic en un elemento <xref:System.Windows.Documents.Hyperlink>.  
  
-   **Navegación mediante programación**.  La aplicación navega sin comprometer al usuario, por ejemplo, estableciendo la propiedad <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=fullName>.  
  
<a name="Browser_Navigation_Security"></a>   
### Seguridad de la navegación de explorador  
 La navegación de explorador únicamente se considera segura en las condiciones siguientes:  
  
-   **Navegación por parte del usuario**.  El usuario navega haciendo clic en un elemento <xref:System.Windows.Documents.Hyperlink> que está dentro del <xref:System.Windows.Navigation.NavigationWindow> principal, no en un <xref:System.Windows.Controls.Frame> anidado.  
  
-   **Zona**.  El contenido al que se navega se encuentra en Internet o en la intranet local.  
  
-   **Protocolo**.  El protocolo que se usa es **http**, **https**, **file** o **mailto**.  
  
 Si una [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] intenta navegar hasta el contenido de una manera que no cumple estas condiciones, se produce una excepción <xref:System.Security.SecurityException>.  
  
<a name="InternetExplorerSecuritySettings"></a>   
## Configuración de seguridad del software de exploración web  
 La configuración de seguridad de su equipo determina el acceso que se permite a cualquier software de exploración web.  El software de exploración web incluye cualquier aplicación o componente que use [WinINet](http://msdn.microsoft.com/es-es/library/aa385331\(vs.85\).aspx) o [UrlMon](http://msdn.microsoft.com/es-es/library/aa767916\(vs.85\).aspx), incluidos Internet Explorer y PresentationHost.exe.  
  
 [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] proporciona un mecanismo que permite configurar las funciones que se pueden ejecutar desde [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] o por él, lo que incluye:  
  
-   Componentes que dependen de [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)]  
  
-   Controles ActiveX y complementos  
  
-   Descargas  
  
-   Scripting  
  
-   Autenticación de usuario  
  
 La colección de funciones que se pueden proteger de esta manera se configura individualmente para cada una de las zonas, a saber, **Internet**, **Intranet**, **Sitios de confianza** y **Sitios restringidos**.  Los siguientes pasos describen cómo configurar la configuración de seguridad:  
  
1.  Abra el **Panel de control**.  
  
2.  Haga clic en **Red e Internet** y, a continuación, en **Opciones de Internet**.  
  
     Aparecerá el cuadro de diálogo Opciones de Internet.  
  
3.  En la pestaña **Seguridad**, seleccione la zona para la que se configura la configuración de seguridad.  
  
4.  Haga clic en el botón **Nivel personalizado**.  
  
     Se abrirá el cuadro de diálogo **Configuración de seguridad**, donde puede configurar los valores de seguridad de la zona seleccionada.  
  
     ![Cuadro de diálogo Configuración de seguridad](../../../docs/framework/wpf/media/wpfsecurityfigure1.PNG "WPFSecurityFigure1")  
  
> [!NOTE]
>  También puede ir al cuadro de diálogo Opciones de Internet de Internet Explorer.  Haga clic en **Herramientas** y, a continuación, haga clic en **Opciones de Internet**.  
  
 A partir de [!INCLUDE[TLA#tla_ie7](../../../includes/tlasharptla-ie7-md.md)], la siguiente configuración de seguridad está incluida específicamente para [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)]:  
  
-   **XAML dinámico**.  Controla si [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] puede navegar hasta archivos de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] dinámico y ejecutarlos  \(opciones: Habilitar, Deshabilitar y Pedir datos\).  
  
-   **Aplicaciones XAML del explorador** Controla si [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] puede navegar hasta [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] y ejecutarlas  \(opciones: Habilitar, Deshabilitar y Pedir datos\).  
  
 De manera predeterminada, todos estos valores están habilitados para las zonas **Internet**, **Intranet local** y **Sitios de confianza**, y deshabilitados para la zona **Sitios restringidos**.  
  
<a name="Security_Settings_for_IE6_and_Below"></a>   
### Valores del Registro de WPF relacionados con la seguridad  
 Además de la configuración de seguridad disponible a través de Opciones de Internet, los siguientes valores del Registro están disponibles para bloquear selectivamente varias características de WPF que afectan a la seguridad.  Los valores se definen bajo la siguiente clave:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\Windows Presentation Foundation\Features`  
  
 La siguiente tabla contiene los valores que se pueden establecer.  
  
|Nombre del valor|Tipo de valor|Datos del valor|  
|----------------------|-------------------|---------------------|  
|XBAPDisallow|REG\_DWORD|1 para no permitir; 0 para permitir.|  
|LooseXamlDisallow|REG\_DWORD|1 para no permitir; 0 para permitir.|  
|WebBrowserDisallow|REG\_DWORD|1 para no permitir; 0 para permitir.|  
|MediaAudioDisallow|REG\_DWORD|1 para no permitir; 0 para permitir.|  
|MediaImageDisallow|REG\_DWORD|1 para no permitir; 0 para permitir.|  
|MediaVideoDisallow|REG\_DWORD|1 para no permitir; 0 para permitir.|  
|ScriptInteropDisallow|REG\_DWORD|1 para no permitir; 0 para permitir.|  
  
<a name="webbrowser_control_and_feature_controls"></a>   
## Controles de características y control WebBrowser  
 El control de WPF <xref:System.Windows.Controls.WebBrowser> se puede utilizar para hospedar el contenido web.  El control de WPF <xref:System.Windows.Controls.WebBrowser> ajusta el control ActiveX de WebBrowser subyacente.  WPF proporciona alguna compatibilidad para proteger la aplicación cuando se usa el control de WPF <xref:System.Windows.Controls.WebBrowser> para hospedar contenido web que no es de confianza.  Sin embargo, algunas características de seguridad deben aplicarse directamente por las aplicaciones mediante el control <xref:System.Windows.Controls.WebBrowser>.  Para obtener más información sobre el control ActiveX de WebBrowser, vea [Información general y tutoriales para WebBrowser](http://msdn.microsoft.com/es-es/library/aa752041\(vs.85\).aspx).  
  
> [!NOTE]
>  Esta sección también se aplica al control <xref:System.Windows.Controls.Frame> ya que utiliza <xref:System.Windows.Controls.WebBrowser> para navegar hasta el contenido HTML.  
  
 Si el control de WPF <xref:System.Windows.Controls.WebBrowser> se utiliza para hospedar contenido web que no es de confianza, la aplicación debería utilizar <xref:System.AppDomain> de confianza parcial para ayudar a aislar el código de aplicación del código de script HTML potencialmente malintencionado.  Esto es especialmente cierto si la aplicación está interactuando con el script hospedado utilizando el método <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> y la propiedad <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A>.  Para obtener más información, vea [Información general sobre los complementos de WPF](../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 Si la aplicación utiliza el control de WPF <xref:System.Windows.Controls.WebBrowser>, otra manera de aumentar la seguridad y mitigar los ataques es habilitar controles de característica de Internet Explorer.  Los controles de característica son adiciones hechas a Internet Explorer que permiten a los administradores y a desarrolladores de software configurar características de Internet Explorer y aplicaciones que hospedan el control ActiveX de WebBrowser, que envuelve el control de WPF <xref:System.Windows.Controls.WebBrowser>.  Los controles de característica se pueden configurar utilizando la función [CoInternetSetFeatureEnabled](http://msdn.microsoft.com/es-es/library/ms537168\(vs.85\).aspx) o cambiando los valores del Registro.  Para obtener más información sobre los controles de característica, vea [Introducción a los controles de características](http://msdn.microsoft.com/es-es/library/ms537184\(vs.85\).aspx) y [Controles de característica de Internet](http://msdn.microsoft.com/es-es/library/ee330720\(vs.85\).aspx).  
  
 Si está desarrollando una aplicación WPF independiente que utiliza el control de WPF <xref:System.Windows.Controls.WebBrowser>, WPF habilita automáticamente los siguientes controles de característica para la aplicación.  
  
|Control de característica|  
|-------------------------------|  
|FEATURE\_MIME\_HANDLING|  
|FEATURE\_MIME\_SNIFFING|  
|FEATURE\_OBJECT\_CACHING|  
|FEATURE\_SAFE\_BINDTOOBJECT|  
|FEATURE\_WINDOW\_RESTRICTIONS|  
|FEATURE\_ZONE\_ELEVATION|  
|FEATURE\_RESTRICT\_FILEDOWNLOAD|  
|FEATURE\_RESTRICT\_ACTIVEXINSTALL|  
|FEATURE\_ADDON\_MANAGEMENT|  
|FEATURE\_HTTP\_USERNAME\_PASSWORD\_DISABLE|  
|FEATURE\_SECURITYBAND|  
|FEATURE\_UNC\_SAVEDFILECHECK|  
|FEATURE\_VALIDATE\_NAVIGATE\_URL|  
|FEATURE\_DISABLE\_TELNET\_PROTOCOL|  
|FEATURE\_WEBOC\_POPUPMANAGEMENT|  
|FEATURE\_DISABLE\_LEGACY\_COMPRESSION|  
|FEATURE\_SSLUX|  
  
 Puesto que estos controles de característica están habilitados incondicionalmente, podrían dañar una aplicación de plena confianza.  En este caso, si no hay riesgo para la seguridad de la aplicación concreta y el contenido que hospeda, el control de característica correspondiente puede deshabilitarse.  
  
 El proceso que crea instancias del objeto ActiveX de WebBrowser aplica los controles de característica.  Por consiguiente, si está creando una aplicación independiente que puede navegar hasta contenido que no es de confianza, debe considerar seriamente habilitar controles de característica adicionales.  
  
> [!NOTE]
>  Esta recomendación está basada en recomendaciones generales para seguridad host MSHTML y SHDOCVW.  Para obtener más información, vea [The MSHTML Host Security FAQ: Part I of II](http://go.microsoft.com/fwlink/?LinkId=179396) y [The MSHTML Host Security FAQ: Part II of II](http://go.microsoft.com/fwlink/?LinkId=179415).  
  
 Para una aplicación ejecutable, considere habilitar los siguientes controles de característica estableciendo el valor del Registro en 1.  
  
|Control de característica|  
|-------------------------------|  
|FEATURE\_ACTIVEX\_REPURPOSEDETECTION|  
|FEATURE\_BLOCK\_LMZ\_IMG|  
|FEATURE\_BLOCK\_LMZ\_OBJECT|  
|FEATURE\_BLOCK\_LMZ\_SCRIPT|  
|FEATURE\_RESTRICT\_RES\_TO\_LMZ|  
|FEATURE\_RESTRICT\_ABOUT\_PROTOCOL\_IE7|  
|FEATURE\_SHOW\_APP\_PROTOCOL\_WARN\_DIALOG|  
|FEATURE\_LOCALMACHINE\_LOCKDOWN|  
|FEATURE\_FORCE\_ADDR\_AND\_STATUS|  
|FEATURE\_RESTRICTED\_ZONE\_WHEN\_FILE\_NOT\_FOUND|  
  
 Para una aplicación ejecutable, considere deshabilitar el siguiente control de característica estableciendo el valor del Registro en 0.  
  
|Control de característica|  
|-------------------------------|  
|FEATURE\_ENABLE\_SCRIPT\_PASTE\_URLACTION\_IF\_PROMPT|  
  
 Si ejecuta una [!INCLUDE[TLA#tla_xbap](../../../includes/tlasharptla-xbap-md.md)] de confianza parcial que incluye un control de WPF <xref:System.Windows.Controls.WebBrowser> en [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)], WPF hospeda el control ActiveX de WebBrowser en el espacio de direcciones del proceso de Internet Explorer.  Puesto que el control ActiveX de WebBrowser se hospeda en el proceso de [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)], todos los controles de característica para Internet Explorer también están habilitados para el control ActiveX de WebBrowser.  
  
 XBAP que se ejecutan en Internet Explorer también obtienen un nivel adicional de seguridad comparado a las aplicaciones independientes normales.  Esta seguridad adicional es porque Internet Explorer y, por consiguiente el control ActiveX de WebBrowser, se ejecuta de forma predeterminada en modo protegido en [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] y [!INCLUDE[win7](../../../includes/win7-md.md)].  Para obtener más información sobre el modo protegido, vea [Comprender y trabajar en modo protegido en Internet Explorer](http://msdn.microsoft.com/es-es/library/bb250462\(vs.85\).aspx).  
  
> [!NOTE]
>  Si intenta ejecutar un XBAP que incluye un control de WPF <xref:System.Windows.Controls.WebBrowser> en Firefox, mientras está en la zona de Internet, se producirá una <xref:System.Security.SecurityException>.  Esto es debido a la directiva de seguridad de WPF.  
  
<a name="APTCA"></a>   
## Deshabilitar los ensamblados APTCA para las aplicaciones cliente de confianza parcial  
 Cuando se instalan ensamblados administrados en [!INCLUDE[TLA#tla_gac](../../../includes/tlasharptla-gac-md.md)], se vuelven de plena confianza porque el usuario debe proporcionar permiso explícito para instalarlos.  Dado que son de plena confianza, únicamente las aplicaciones cliente administradas de plena confianza pueden utilizarlos.  Para permitir que las aplicaciones de confianza parcial los utilicen, se deben marcar con <xref:System.Security.AllowPartiallyTrustedCallersAttribute> \(APTCA\).  Únicamente los ensamblados que han demostrado ser seguros para su ejecución en confianza parcial se deben marcar con este atributo.  
  
 Sin embargo, es posible que un ensamblado APTCA presente un problema de seguridad después de instalarlo en [!INCLUDE[TLA2#tla_gac](../../../includes/tla2sharptla-gac-md.md)].  Cuando se descubre un problema de seguridad, los publicadores de ensamblados pueden compilar una actualización de seguridad para corregir el problema en las instalaciones existentes, así como para proteger contra las instalaciones que se produzcan después de detectar el problema.  Una opción para esta actualización es desinstalar el ensamblado, aunque ello constituya una interrupción para otras aplicaciones cliente de plena confianza que utilizan el ensamblado.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] proporciona un mecanismo por el que un ensamblado APTCA se puede deshabilitar para [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] de confianza parcial, sin desinstalar el ensamblado APTCA.  
  
 Para deshabilitar un ensamblado de APTCA, tiene que crear una clave del Registro especial:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 A continuación se muestra un ejemplo:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 Esta clave establece una entrada para el ensamblado de APTCA.  También tiene que crear un valor en esta clave que habilite o deshabilite el ensamblado.  A continuación se muestran detalles del valor:  
  
-   Nombre del valor: **APTCA\_FLAG**.  
  
-   Tipo de valor: **REG\_DWORD**.  
  
-   Datos del valor: **1** para deshabilitar; **0** para habilitar.  
  
 Si un ensamblado tiene que deshabilitarse para las aplicaciones cliente de confianza parcial, puede escribir una actualización que crear el valor y la clave del Registro.  
  
> [!NOTE]
>  Al deshabilitar los ensamblados básicos de [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)] de este modo, éstos no se ven afectados, puesto que son necesarios para que se ejecuten las aplicaciones administradas.  La compatibilidad para deshabilitar los ensamblados APTCA se destina principalmente a aplicaciones de terceros.  
  
<a name="LooseContentSandboxing"></a>   
## Comportamiento en espacio aislado de archivos XAML independientes  
 Los archivos [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] independientes son archivos XAML solo de marcado que no dependen de código subyacente, controlador de eventos o ensamblado específico de aplicación.  Cuando se navega a archivos independientes de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] directamente desde el explorador, se cargan en un recinto de seguridad basado en el conjunto de permisos de zona de Internet predeterminado.  
  
 Sin embargo, el comportamiento de seguridad es diferente cuando se navega hasta los archivos de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] dinámico desde <xref:System.Windows.Navigation.NavigationWindow> o desde <xref:System.Windows.Controls.Frame> en una aplicación independiente.  
  
 En ambos casos, el archivo de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] dinámico al que se navega hereda los permisos de su aplicación host.  Sin embargo, este comportamiento puede no ser deseable desde una perspectiva de seguridad, en especial si el archivo de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] dinámico lo ha generado una entidad desconocida o que no es de confianza.  Este tipo de contenido se denomina *contenido externo*; tanto <xref:System.Windows.Controls.Frame> como <xref:System.Windows.Navigation.NavigationWindow> se pueden configurar para aislarlo cuando se navega hasta él.  El aislamiento se logra estableciendo la propiedad **SandboxExternalContent** en True, como se muestra en los ejemplos siguientes para <xref:System.Windows.Controls.Frame> y <xref:System.Windows.Navigation.NavigationWindow>:  
  
 [!code-xml[SecurityOverviewSnippets#FrameMARKUP](../../../samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xml[SecurityOverviewSnippets#NavigationWindowMARKUP](../../../samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 Con este valor, el contenido externo se cargará en un proceso que es independiente del proceso en el que se hospeda la aplicación.  Este proceso está restringido al conjunto de permisos de zona de Internet predeterminado, lo que lo aísla de manera eficiente de la aplicación de hospedaje y del equipo cliente.  
  
> [!NOTE]
>  Aunque la navegación a archivos [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] independientes de <xref:System.Windows.Navigation.NavigationWindow> o <xref:System.Windows.Controls.Frame> en una aplicación independiente se implementa en función de la infraestructura de hospedaje del explorador WPF, que incluye el proceso de PresentationHost, el nivel de seguridad es ligeramente inferior a cuando el contenido se carga directamente en Internet Explorer en [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] y [!INCLUDE[win7](../../../includes/win7-md.md)] \(todavía a través de PresentationHost\). Esto se debe a que una aplicación WPF independiente que use un explorador web no proporciona la característica de seguridad adicional del modo protegido de Internet Explorer.  
  
<a name="BestPractices"></a>   
## Recursos para desarrollar aplicaciones WPF que promueven la seguridad  
 A continuación se ofrecen recursos adicionales para ayudar a desarrollar aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] que promueven la seguridad:  
  
|Área|Recurso|  
|----------|-------------|  
|Código administrado|[Patterns and Practices Security Guidance for Applications](http://go.microsoft.com/fwlink/?LinkId=117426)|  
|[!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)]|[Seguridad de acceso del código](../../../docs/framework/misc/code-access-security.md)|  
|[!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)]|[Seguridad e implementación ClickOnce](../Topic/ClickOnce%20Security%20and%20Deployment.md)|  
|[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]|[Seguridad de confianza parcial de WPF](../../../docs/framework/wpf/wpf-partial-trust-security.md)|  
  
## Vea también  
 [Seguridad de confianza parcial de WPF](../../../docs/framework/wpf/wpf-partial-trust-security.md)   
 [Estrategia de seguridad de WPF: Seguridad de plataforma](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)   
 [Estrategia de seguridad de WPF: Ingeniería de seguridad](../../../docs/framework/wpf/wpf-security-strategy-security-engineering.md)   
 [Patterns and Practices Security Guidance for Applications](http://go.microsoft.com/fwlink/?LinkId=117426)   
 [Seguridad de acceso del código](../../../docs/framework/misc/code-access-security.md)   
 [Seguridad e implementación ClickOnce](../Topic/ClickOnce%20Security%20and%20Deployment.md)   
 [Información general sobre XAML \(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
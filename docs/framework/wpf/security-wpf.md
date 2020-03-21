---
title: Seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- XAML files [WPF], sandbox behavior
- browser-hosted application security [WPF]
- application security [WPF]
- navigation security [WPF]
- loose XAML files [WPF], sandbox behavior
- WPF security [WPF]
- WebBrowser control [WPF], security
- feature controls [WPF], security
- XBAP security [WPF]
- Internet Explorer security settings [WPF]
ms.assetid: ee1baea0-3611-4e36-9ad6-fcd5205376fb
ms.openlocfilehash: e0a56dcbf8d151fcb0d4f6271ecba15c0ff955a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174620"
---
# <a name="security-wpf"></a>Seguridad (WPF)
<a name="introduction"></a>Al desarrollar aplicaciones independientes y hospedadas en explorador de Windows Presentation Foundation (WPF), debe tener en cuenta el modelo de seguridad. Las aplicaciones independientes de WPFWPF se ejecutan con permisos sin restricciones (conjunto de permisos CAS**FullTrust),** ya sea implementadas con Windows Installer (.msi), XCopy o ClickOnce. No se admite la implementación de aplicaciones de WPF independientes y de confianza parcial con ClickOnce. Sin embargo, una aplicación host de <xref:System.AppDomain> plena confianza puede crear una confianza parcial mediante el modelo de complemento de .NET Framework. Para obtener más información, vea [Información general sobre complementos](./app-development/wpf-add-ins-overview.md)de WPF .  
  
 Las aplicaciones hospedadas en el explorador WPF están hospedadas por Windows Internet Explorer [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] o Firefox y pueden ser aplicaciones de explorador XAML (XBAP) o documentos sueltos Para obtener más información, vea Información general sobre las aplicaciones del [explorador XAML](./app-development/wpf-xaml-browser-applications-overview.md)de WPF .  
  
 Las aplicaciones hospedadas en el explorador de WPFWPF se ejecutan dentro de un entorno limitado de seguridad de confianza parcial, de forma predeterminada, que se limita al conjunto de permisos de zona de**Internet** CAS predeterminado. Esto aísla eficazmente las aplicaciones hospedadas en el explorador WPFWPF del equipo cliente de la misma manera que se espera que las aplicaciones web típicas se aíslen. XBAP puede elevar los privilegios hasta Plena confianza en función de la zona de seguridad de la dirección URL de implementación y la configuración de seguridad del cliente. Para obtener más información, vea [Seguridad de confianza parcial de WPF](wpf-partial-trust-security.md).  
  
 En este tema se describe el modelo de seguridad para aplicaciones independientes y hospedadas en explorador de Windows Presentation Foundation (WPF).  
  
 Este tema contiene las siguientes secciones:  
  
- [Navegación segura](#SafeTopLevelNavigation)  
  
- [Configuración de seguridad de software de exploración web](#InternetExplorerSecuritySettings)  
  
- [Control WebBrowser y controles de características](#webbrowser_control_and_feature_controls)  
  
- [Deshabilitar ensamblados APTCA para aplicaciones cliente de confianza parcial](#APTCA)  
  
- [Comportamiento de espacio aislado para archivos XAML dinámicos](#LooseContentSandboxing)  
  
- [Recursos para desarrollar aplicaciones de WPF que promueven la seguridad](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>
## <a name="safe-navigation"></a>Navegación segura  
 Para XBAPs, WPFWPF distingue dos tipos de navegación: aplicación y explorador.  
  
 *Navegación de aplicación* es la navegación entre los elementos de contenido dentro de una aplicación hospedada en un explorador. *Navegación de explorador* es la navegación que cambia el contenido y la dirección URL del explorador. La relación entre la navegación de aplicaciones (normalmente XAML) y la navegación del explorador (normalmente HTML) se muestra en la siguiente ilustración:
  
 ![Relación entre la navegación de la aplicación y la navegación del navegador.](./media/security-wpf/application-browser-navigation-relationship.png)  
  
 El tipo de contenido que se considera seguro para que un XBAP navegue se determina principalmente por si se utiliza la navegación de la aplicación o la navegación del explorador.  
  
<a name="Application_Navigation_Security"></a>
### <a name="application-navigation-security"></a>Seguridad de navegación de aplicación  
 La navegación de aplicaciones se considera segura si se puede identificar con un URI de paquete, que admite cuatro tipos de contenido:  
  
|Tipo de contenido|Descripción|Ejemplo de URI|  
|------------------|-----------------|-----------------|  
|Resource|Archivos que se agregan a un proyecto con un tipo de compilación De **recurso**.|`pack://application:,,,/MyResourceFile.xaml`|  
|Contenido|Archivos que se agregan a un proyecto con un tipo de compilación de **Contenido**.|`pack://application:,,,/MyContentFile.xaml`|  
|Sitio de origen|Archivos que se agregan a un proyecto con un tipo de compilación **Ninguno**.|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|Código de aplicación|Recursos XAML que tienen un código compilado subyacente.<br /><br /> O bien<br /><br /> Archivos XAML que se agregan a un proyecto con un tipo **de**compilación Page .|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
> Para obtener más información acerca de los archivos de datos de aplicación y los URI de paquete, vea [WPF Application Resource, Content, and Data Files](./app-development/wpf-application-resource-content-and-data-files.md).  
  
 El usuario puede navegar por los archivos de estos tipos de contenido, aunque también se pueden navegar mediante programación:  
  
- **Navegación de usuario**. El usuario navega haciendo <xref:System.Windows.Documents.Hyperlink> clic en un elemento.  
  
- **Navegación mediante programación**. La aplicación navega sin involucrar al usuario, <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType> por ejemplo, estableciendo la propiedad.  
  
<a name="Browser_Navigation_Security"></a>
### <a name="browser-navigation-security"></a>Seguridad de navegación de explorador  
 La navegación de explorador se considera segura solo en las siguientes condiciones:  
  
- **Navegación de usuario**. El usuario navega haciendo <xref:System.Windows.Documents.Hyperlink> clic en un <xref:System.Windows.Navigation.NavigationWindow>elemento que está <xref:System.Windows.Controls.Frame>dentro del principal, no en un anidado.  
  
- **Zona**. El contenido al que se navega se encuentra en Internet o en la intranet local.  
  
- **Protocolo**. El protocolo que se utiliza es **http**, **https**, **file**o **mailto**.  
  
 Si un XBAP intenta navegar al contenido de una manera <xref:System.Security.SecurityException> que no cumple con estas condiciones, se produce un.  
  
<a name="InternetExplorerSecuritySettings"></a>
## <a name="web-browsing-software-security-settings"></a>Configuración de seguridad de software de exploración web  
 La configuración de seguridad en el equipo determina el acceso que se concede a cualquier software de navegación web. El software de exploración web incluye cualquier aplicación o componente que utilice las API [WinINet](/windows/win32/wininet/portal) o [UrlMon,](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa767916(v=vs.85)) incluidos Internet Explorer y PresentationHost.exe.  
  
 Internet Explorer proporciona un mecanismo mediante el cual puede configurar la funcionalidad que se permite que se ejecute por o desde Internet Explorer, incluidos los siguientes:  
  
- Componentes dependientes de .NET Framework  
  
- Controles y complementos de ActiveX  
  
- Descargas  
  
- Scripting  
  
- Autenticación de usuarios  
  
 La colección de funciones que se pueden proteger de esta manera se configura por zona para las zonas **Internet**, **Intranet**, Sitios de **confianza**y **Sitios restringidos.** En los siguientes pasos se describe cómo establecer la configuración de seguridad:  
  
1. Abra el **Panel de Control**.  
  
2. Haga clic en **Red e Internet** y, a continuación, haga clic en Opciones de **Internet**.  
  
     Aparecerá el cuadro de diálogo Opciones de Internet.  
  
3. En la ficha **Seguridad,** seleccione la zona para la que desea configurar los valores de seguridad.  
  
4. Haga clic en el botón **Nivel personalizado.**  
  
     Aparece el cuadro de diálogo Configuración de **seguridad** y puede configurar los valores de seguridad para la zona seleccionada.  
  
     ![Captura de pantalla que muestra el cuadro de diálogo Configuración de seguridad.](./media/security-wpf/windows-presentation-foundation-security-settings.png)  
  
> [!NOTE]
> También puede abrir el cuadro de diálogo Opciones de Internet desde Internet Explorer. Haga clic en **Herramientas** y, a continuación, en **Opciones de Internet**.  
  
 A partir de Windows Internet Explorer 7, se incluyen las siguientes opciones de seguridad específicas para .NET Framework:  
  
- **XAML dinámico**. Controla si Internet Explorer [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] puede navegar a archivos y perderlos. (Opciones Habilitar, Deshabilitar y Preguntar).  
  
- **Aplicaciones de explorador XAML**. Controla si Internet Explorer puede navegar y ejecutar XBAPs. (Opciones Habilitar, Deshabilitar y Preguntar).  
  
 De forma predeterminada, esta configuración está habilitada para las zonas **Internet,** **Intranet local**y Sitios de **confianza** y está deshabilitada para la zona **Sitios restringidos.**  
  
<a name="Security_Settings_for_IE6_and_Below"></a>
### <a name="security-related-wpf-registry-settings"></a>Configuración del Registro de WPF relacionada con la seguridad  
 Además de la configuración de seguridad disponible mediante Opciones de Internet, los valores del Registro siguientes están disponibles para bloquear selectivamente varias características de WPF de seguridad. Los valores se definen con la siguiente clave:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\Windows Presentation Foundation\Features`  
  
 En la tabla siguiente se muestran los valores que se pueden establecer.  
  
|Nombre del valor|Tipo de valor|Datos del valor|  
|----------------|----------------|----------------|  
|XBAPDisallow|REG_DWORD|1 para no permitir; 0 para permitir.|  
|LooseXamlDisallow|REG_DWORD|1 para no permitir; 0 para permitir.|  
|WebBrowserDisallow|REG_DWORD|1 para no permitir; 0 para permitir.|  
|MediaAudioDisallow|REG_DWORD|1 para no permitir; 0 para permitir.|  
|MediaImageDisallow|REG_DWORD|1 para no permitir; 0 para permitir.|  
|MediaVideoDisallow|REG_DWORD|1 para no permitir; 0 para permitir.|  
|ScriptInteropDisallow|REG_DWORD|1 para no permitir; 0 para permitir.|  
  
<a name="webbrowser_control_and_feature_controls"></a>
## <a name="webbrowser-control-and-feature-controls"></a>Control WebBrowser y controles de características  
 El <xref:System.Windows.Controls.WebBrowser> WPFWPF control se puede usar para hospedar contenido Web. El <xref:System.Windows.Controls.WebBrowser> WPFWPF control ajusta el subyacente WebBrowser control ActiveX. WPFWPF proporciona cierta compatibilidad para proteger la <xref:System.Windows.Controls.WebBrowser> aplicación cuando se usa el WPFWPF control para hospedar contenido Web que no es de confianza. Sin embargo, algunas características de seguridad <xref:System.Windows.Controls.WebBrowser> deben ser aplicadas directamente por las aplicaciones que utilizan el control. Para obtener más información sobre el control ActiveX de WebBrowser, vea [Tutoriales y información](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752041(v=vs.85))sobre webBrowser Control .  
  
> [!NOTE]
> Esta sección también <xref:System.Windows.Controls.Frame> se aplica al <xref:System.Windows.Controls.WebBrowser> control, ya que usa el para navegar al contenido HTML.  
  
 Si el <xref:System.Windows.Controls.WebBrowser> WPFWPF control se usa para hospedar contenido Web <xref:System.AppDomain> que no es de confianza, la aplicación debe usar una confianza parcial para ayudar a aislar el código de la aplicación del código de script HTML potencialmente malintencionado. Esto es especialmente cierto si la aplicación está interactuando con el script hospedado mediante el <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> método y la <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A> propiedad. Para obtener más información, vea [Información general sobre complementos](./app-development/wpf-add-ins-overview.md)de WPF .  
  
 Si la aplicación <xref:System.Windows.Controls.WebBrowser> usa el control WPFWPF, otra forma de aumentar la seguridad y mitigar los ataques es habilitar los controles de características de Internet Explorer. Los controles de características son adiciones a Internet Explorer que permiten a los administradores y desarrolladores configurar características de Internet Explorer y las aplicaciones que hospedan el control ActiveX WebBrowser, que ajusta el control WPFWPF. <xref:System.Windows.Controls.WebBrowser> Los controles de características se pueden configurar mediante la función [CoInternetSetFeatureEnabled](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537168(v=vs.85)) o cambiando los valores del Registro. Para obtener más información acerca de los controles de entidades, consulte [Introducción a](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537184(v=vs.85)) los controles de características y controles de características de [Internet](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/general-info/ee330720(v=vs.85)).  
  
 Si está desarrollando una aplicación WPF <xref:System.Windows.Controls.WebBrowser> independiente que usa el WPFWPF control, WPFWPF habilita automáticamente los siguientes controles de característica para la aplicación.  
  
|Control de característica|  
|---------------------|  
|FEATURE_MIME_HANDLING|  
|FEATURE_MIME_SNIFFING|  
|FEATURE_OBJECT_CACHING|  
|FEATURE_SAFE_BINDTOOBJECT|  
|FEATURE_WINDOW_RESTRICTIONS|  
|FEATURE_ZONE_ELEVATION|  
|FEATURE_RESTRICT_FILEDOWNLOAD|  
|FEATURE_RESTRICT_ACTIVEXINSTALL|  
|FEATURE_ADDON_MANAGEMENT|  
|FEATURE_HTTP_USERNAME_PASSWORD_DISABLE|  
|FEATURE_SECURITYBAND|  
|FEATURE_UNC_SAVEDFILECHECK|  
|FEATURE_VALIDATE_NAVIGATE_URL|  
|FEATURE_DISABLE_TELNET_PROTOCOL|  
|FEATURE_WEBOC_POPUPMANAGEMENT|  
|FEATURE_DISABLE_LEGACY_COMPRESSION|  
|FEATURE_SSLUX|  
  
 Puesto que estos controles de característica están habilitados incondicionalmente, podrían afectar a una aplicación de plena confianza. En este caso, si no hay ningún riesgo de seguridad para la aplicación específica y el contenido que se hospeda, se puede deshabilitar el control de característica correspondiente.  
  
 Los controles de características se aplican mediante el proceso de creación de instancias del objeto ActiveX de WebBrowser. Por lo tanto, si está creando una aplicación independiente que puede navegar a contenido que no es de confianza, debe considerar seriamente la posibilidad de habilitar controles de característica adicionales.  
  
> [!NOTE]
> Esta recomendación se basa en las recomendaciones generales para la seguridad de host MSHTML y SHDOCVW. Para obtener más información, consulte Preguntas frecuentes sobre seguridad de [host MSHTML: Parte I de II](https://msrc-blog.microsoft.com/2009/04/02/the-mshtml-host-security-faq-part-i-of-ii/) y Preguntas frecuentes sobre seguridad de host [MSHTML: Parte II de II](https://msrc-blog.microsoft.com/2009/04/03/the-mshtml-host-security-faq-part-ii-of-ii/).  
  
 Para el archivo ejecutable, considere la posibilidad de habilitar los siguientes controles de característica. Para ello, establezca el valor del Registro en 1.  
  
|Control de característica|  
|---------------------|  
|FEATURE_ACTIVEX_REPURPOSEDETECTION|  
|FEATURE_BLOCK_LMZ_IMG|  
|FEATURE_BLOCK_LMZ_OBJECT|  
|FEATURE_BLOCK_LMZ_SCRIPT|  
|FEATURE_RESTRICT_RES_TO_LMZ|  
|FEATURE_RESTRICT_ABOUT_PROTOCOL_IE7|  
|FEATURE_SHOW_APP_PROTOCOL_WARN_DIALOG|  
|FEATURE_LOCALMACHINE_LOCKDOWN|  
|FEATURE_FORCE_ADDR_AND_STATUS|  
|FEATURE_RESTRICTED_ZONE_WHEN_FILE_NOT_FOUND|  
  
 Para el archivo ejecutable, considere la posibilidad de deshabilitar el siguiente control de característica. Para ello, establezca el valor del Registro en 0.  
  
|Control de característica|  
|---------------------|  
|FEATURE_ENABLE_SCRIPT_PASTE_URLACTION_IF_PROMPT|  
  
 Si ejecuta una aplicación de explorador XAML de confianza parcial <xref:System.Windows.Controls.WebBrowser> (XBAP) que incluye un control WPF en Windows Internet Explorer, WPFWPF hospeda el control ActiveX WebBrowser en el espacio de direcciones del proceso de Internet Explorer. Puesto que el control ActiveX de WebBrowser se hospeda en el proceso de Internet Explorer, todos los controles de característica para Internet Explorer también están habilitados para el control ActiveX de WebBrowser.  
  
 Los objetos XBAP que se ejecutan en Internet Explorer también obtienen un nivel adicional de seguridad en comparación con las aplicaciones independientes normales. Esta seguridad adicional se debe a que Internet Explorer y, por lo tanto, el control ActiveX WebBrowser, se ejecuta en modo protegido de forma predeterminada en Windows Vista y Windows 7. Para obtener más información sobre el modo protegido, consulte [Descripción y trabajo en modo protegido de Internet Explorer](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/).  
  
> [!NOTE]
> Si intenta ejecutar un XBAP que <xref:System.Windows.Controls.WebBrowser> incluye un control WPF en <xref:System.Security.SecurityException> Firefox, mientras que en la zona de Internet, se producirá un. Esto se debe a la directiva de seguridad de WPF.  
  
<a name="APTCA"></a>
## <a name="disabling-aptca-assemblies-for-partially-trusted-client-applications"></a>Deshabilitar ensamblados APTCA para aplicaciones cliente de confianza parcial  
 Cuando los ensamblados administrados se instalan en la caché global de ensamblados (GAC), pasan a ser de plena confianza porque el usuario debe proporcionar permiso explícito para instalarlos. Dado que son de plena confianza, solo las aplicaciones cliente administradas de plena confianza pueden usarlos. Para permitir que las aplicaciones de confianza parcial <xref:System.Security.AllowPartiallyTrustedCallersAttribute> las utilicen, deben estar marcadas con el (APTCA). Solo los ensamblados probados como seguros para la ejecución en confianza parcial se deben marcar con este atributo.  
  
 Sin embargo, es posible que un ensamblado APTCA muestre un defecto de seguridad después de ser instalado en el GAC. Cuando se detecta un error de seguridad, los publicadores de ensamblados pueden producir una actualización de seguridad para corregir el problema en las instalaciones existentes y proteger las instalaciones que se produzcan después de detectar el problema. Una opción para la actualización es desinstalar el ensamblado, aunque eso podría causar que otras aplicaciones cliente de plena confianza que usan el ensamblado dejen de funcionar correctamente.  
  
 WPFWPF proporciona un mecanismo mediante el cual se puede deshabilitar un ensamblado APTCA para XBAP de confianza parcial sin desinstalar el ensamblado APTCA.  
  
 Para deshabilitar un ensamblado APTCA, tiene que crear una clave del Registro especial:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 Se muestra un ejemplo a continuación:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 Esta clave establece una entrada para el ensamblado APTCA. También debe crear un valor en esta clave que habilite o deshabilite el ensamblado. Los siguientes son los detalles del valor:  
  
- Nombre del valor: **APTCA_FLAG**.  
  
- Tipo de valor: **REG_DWORD**.  
  
- Datos de valor: **1** para deshabilitar; **0** para habilitar.  
  
 Si un ensamblado se debe deshabilitar para las aplicaciones cliente de confianza parcial, puede escribir una actualización que cree la clave y el valor del Registro.  
  
> [!NOTE]
> Los ensamblados de Core .NET Framework no se ven afectados al deshabilitarlos de esta manera porque son necesarios para que se ejecuten las aplicaciones administradas. La compatibilidad para deshabilitar ensamblados APTCA está destinada principalmente a aplicaciones de terceros.  
  
<a name="LooseContentSandboxing"></a>
## <a name="sandbox-behavior-for-loose-xaml-files"></a>Comportamiento de espacio aislado para archivos XAML dinámicos  
 Los [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] archivos sueltos son archivos XAML de solo marcado que no dependen de ningún código subyacente, controlador de eventos o ensamblado específico de la aplicación. Cuando [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] los archivos sueltos se navegan directamente desde el explorador, se cargan en un entorno limitado de seguridad basado en el conjunto de permisos de zona de Internet predeterminado.  
  
 Sin embargo, el comportamiento [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] de seguridad es diferente <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame> cuando se navegan archivos sueltos desde una aplicación o desde una aplicación independiente.  
  
 En ambos casos, [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] el archivo suelto al que se navega hereda los permisos de su aplicación host. Sin embargo, este comportamiento puede ser indeseable [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] desde una perspectiva de seguridad, especialmente si un archivo suelto fue producido por una entidad que no es de confianza o desconocido. Este tipo de contenido se conoce <xref:System.Windows.Controls.Frame> como <xref:System.Windows.Navigation.NavigationWindow> *contenido externo*y ambos y se pueden configurar para aislarlo cuando se navega a. El aislamiento se logra estableciendo la propiedad **SandboxExternalContent** en true, como se muestra en los siguientes ejemplos para <xref:System.Windows.Controls.Frame> y: <xref:System.Windows.Navigation.NavigationWindow>  
  
 [!code-xaml[SecurityOverviewSnippets#FrameMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xaml[SecurityOverviewSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 Con esta configuración, el contenido externo se carga en un proceso independiente del proceso que hospeda la aplicación. Este proceso está restringido al conjunto de permisos predeterminado de la zona de Internet y lo aísla de forma eficaz desde la aplicación host y el equipo cliente.  
  
> [!NOTE]
> Aunque la navegación [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] a archivos <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame> sueltos desde una aplicación o en una aplicación independiente se implementa en función de la infraestructura de hospedaje del explorador WPF, que implica el proceso PresentationHost, el nivel de seguridad es ligeramente menor que cuando el contenido se carga directamente en Internet Explorer en Windows Vista y Windows 7 (que seguiría siendo a través de PresentationHost). Esto se debe a que una aplicación de WPF independiente que usa un navegador web no proporciona la característica de seguridad adicional de modo protegido de Internet Explorer.  
  
<a name="BestPractices"></a>
## <a name="resources-for-developing-wpf-applications-that-promote-security"></a>Recursos para desarrollar aplicaciones de WPF que promueven la seguridad  
 A continuación se indican algunos recursos adicionales para ayudar a desarrollar aplicaciones WPF que promueven la seguridad:  
  
|Área|Resource|  
|----------|--------------|  
|Código administrado|[Modelos y prácticas Guía de seguridad para aplicaciones](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))|  
|CAS|[Seguridad de acceso al código](../misc/code-access-security.md)|  
|ClickOnce|[ClickOnce Seguridad e implementación](/visualstudio/deployment/clickonce-security-and-deployment)|  
|WPF|[Seguridad de confianza parcial de WPF](wpf-partial-trust-security.md)|  
  
## <a name="see-also"></a>Consulte también

- [Seguridad de confianza parcial de WPF](wpf-partial-trust-security.md)
- [Estrategia de seguridad de WPF: Seguridad de plataforma](wpf-security-strategy-platform-security.md)
- [Estrategia de seguridad de WPF: Ingeniería de seguridad](wpf-security-strategy-security-engineering.md)
- [Modelos y prácticas Guía de seguridad para aplicaciones](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))
- [Seguridad de acceso al código](../misc/code-access-security.md)
- [ClickOnce Seguridad e implementación](/visualstudio/deployment/clickonce-security-and-deployment)
- [Información general sobre XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)

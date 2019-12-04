---
title: Seguridad (WPF)
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
ms.openlocfilehash: 939c9c6b8a8a8822174f08d5c0b50ef051264ee1
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802084"
---
# <a name="security-wpf"></a>Seguridad (WPF)
<a name="introduction"></a>Al desarrollar aplicaciones independientes y hospedadas en un explorador Windows Presentation Foundation (WPF), debe tener en cuenta el modelo de seguridad. [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] aplicaciones independientes se ejecutan con permisos no restringidos (conjunto de permisos**FullTrust** de CAS), tanto si se implementan con Windows Installer (. msi), xcopy o ClickOnce. No se admite la implementación de aplicaciones de WPF independientes y de confianza parcial con ClickOnce. Sin embargo, una aplicación host de plena confianza puede crear un <xref:System.AppDomain> de confianza parcial mediante el modelo de complemento .NET Framework. Para obtener más información, consulte [Introducción a los complementos de WPF](./app-development/wpf-add-ins-overview.md).  
  
 las aplicaciones hospedadas en el explorador [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] se hospedan en Windows Internet Explorer o Firefox, y pueden ser aplicaciones de explorador XAML (XBAP) o documentos de [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] sueltos para obtener más información, vea [información general sobre las aplicaciones de explorador XAML de WPF](./app-development/wpf-xaml-browser-applications-overview.md).  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] las aplicaciones hospedadas en explorador se ejecutan en un espacio aislado de seguridad de confianza parcial, de forma predeterminada, que está limitado al conjunto de permisos de zona de**Internet** de CAS predeterminado. Esto aísla de forma eficaz las aplicaciones hospedadas en el explorador [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] del equipo cliente de la misma manera que se espera que las aplicaciones web típicas estén aisladas. XBAP puede elevar los privilegios hasta Plena confianza en función de la zona de seguridad de la dirección URL de implementación y la configuración de seguridad del cliente. Para obtener más información, vea [Seguridad de confianza parcial de WPF](wpf-partial-trust-security.md).  
  
 En este tema se describe el modelo de seguridad para las aplicaciones independientes y hospedadas en el explorador de Windows Presentation Foundation (WPF).  
  
 Este tema contiene las siguientes secciones:  
  
- [Navegación segura](#SafeTopLevelNavigation)  
  
- [Configuración de seguridad de software de exploración web](#InternetExplorerSecuritySettings)  
  
- [Control WebBrowser y controles de características](#webbrowser_control_and_feature_controls)  
  
- [Deshabilitar ensamblados APTCA para aplicaciones cliente de confianza parcial](#APTCA)  
  
- [Comportamiento de espacio aislado para archivos XAML dinámicos](#LooseContentSandboxing)  
  
- [Recursos para desarrollar aplicaciones de WPF que promueven la seguridad](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>   
## <a name="safe-navigation"></a>Navegación segura  
 En el caso de XBAP, [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] distingue dos tipos de navegación: aplicación y explorador.  
  
 *Navegación de aplicación* es la navegación entre los elementos de contenido dentro de una aplicación hospedada en un explorador. *Navegación de explorador* es la navegación que cambia el contenido y la dirección URL del explorador. La relación entre la navegación de la aplicación (normalmente XAML) y la navegación del explorador (normalmente HTML) se muestra en la siguiente ilustración:
  
 ![Relación entre la navegación de la aplicación y la navegación del explorador.](./media/security-wpf/application-browser-navigation-relationship.png)  
  
 El tipo de contenido que se considera seguro para que una aplicación XBAP navegue a está determinado principalmente por la navegación de la aplicación o la navegación del explorador.  
  
<a name="Application_Navigation_Security"></a>   
### <a name="application-navigation-security"></a>Seguridad de navegación de aplicación  
 La navegación de la aplicación se considera segura si se puede identificar con un Pack URI, que admite cuatro tipos de contenido:  
  
|Tipo de contenido|Descripción|Ejemplo de URI|  
|------------------|-----------------|-----------------|  
|Recurso|Archivos que se agregan a un proyecto con un tipo de compilación de **recurso**.|`pack://application:,,,/MyResourceFile.xaml`|  
|Contenido|Archivos que se agregan a un proyecto con un tipo de compilación de **contenido**.|`pack://application:,,,/MyContentFile.xaml`|  
|Sitio de origen|Archivos que se agregan a un proyecto con un tipo de compilación de **ninguno**.|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|Código de aplicación|Recursos XAML que tienen un código compilado subyacente.<br /><br /> O bien,<br /><br /> Archivos XAML que se agregan a un proyecto con un tipo de compilación de **Página**.|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
> Para obtener más información sobre los archivos de datos de aplicación y los pack uri, consulte [archivos de recursos, contenido y datos de aplicaciones de WPF](./app-development/wpf-application-resource-content-and-data-files.md).  
  
 El usuario puede navegar por los archivos de estos tipos de contenido, aunque también se pueden navegar mediante programación:  
  
- **Navegación de usuario**. El usuario navega haciendo clic en un elemento de <xref:System.Windows.Documents.Hyperlink>.  
  
- **Navegación mediante programación**. La aplicación navega sin implicar al usuario, por ejemplo, estableciendo la propiedad <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>.  
  
<a name="Browser_Navigation_Security"></a>   
### <a name="browser-navigation-security"></a>Seguridad de navegación de explorador  
 La navegación de explorador se considera segura solo en las siguientes condiciones:  
  
- **Navegación de usuario**. El usuario navega haciendo clic en un elemento <xref:System.Windows.Documents.Hyperlink> que se encuentra dentro del <xref:System.Windows.Navigation.NavigationWindow>principal, no en un <xref:System.Windows.Controls.Frame>anidado.  
  
- **Zona**. El contenido al que se navega se encuentra en Internet o en la intranet local.  
  
- **Protocolo**. El protocolo que se está usando es **http**, **https**, **File**o **mailto**.  
  
 Si una aplicación XBAP intenta navegar hasta el contenido de una manera que no cumple estas condiciones, se produce una <xref:System.Security.SecurityException>.  
  
<a name="InternetExplorerSecuritySettings"></a>   
## <a name="web-browsing-software-security-settings"></a>Configuración de seguridad de software de exploración web  
 La configuración de seguridad en el equipo determina el acceso que se concede a cualquier software de navegación web. El software de exploración web incluye cualquier aplicación o componente que use las API [WinInet](https://go.microsoft.com/fwlink/?LinkId=179379) o [UrlMon](https://go.microsoft.com/fwlink/?LinkId=179383) , como Internet Explorer y PresentationHost. exe.  
  
 Internet Explorer proporciona un mecanismo por el que puede configurar la funcionalidad que puede ser ejecutada por o desde Internet Explorer, incluidas las siguientes:  
  
- Componentes que dependen de .NET Framework  
  
- Controles y complementos de ActiveX  
  
- Descargas  
  
- Secuencias de comandos  
  
- Autenticación de usuario  
  
 La colección de funciones que se pueden proteger de esta manera se configura en cada zona para las zonas de **Internet**, **intranet**, **sitios de confianza**y **sitios restringidos** . En los siguientes pasos se describe cómo establecer la configuración de seguridad:  
  
1. Abra el **Panel de Control**.  
  
2. Haga clic en **red e Internet** y, a continuación, en **Opciones de Internet**.  
  
     Aparecerá el cuadro de diálogo Opciones de Internet.  
  
3. En la pestaña **seguridad** , seleccione la zona para la que desea establecer la configuración de seguridad.  
  
4. Haga clic en el botón **nivel personalizado** .  
  
     Aparece el cuadro de diálogo **configuración de seguridad** y puede configurar las opciones de seguridad para la zona seleccionada.  
  
     ![Captura de pantalla que muestra el cuadro de diálogo Configuración de seguridad.](./media/security-wpf/windows-presentation-foundation-security-settings.png)  
  
> [!NOTE]
> También puede abrir el cuadro de diálogo Opciones de Internet desde Internet Explorer. Haga clic en **herramientas** y, a continuación, en **Opciones de Internet**.  
  
 A partir de Windows Internet Explorer 7, se incluyen las siguientes opciones de configuración de seguridad específicas para .NET Framework:  
  
- **XAML dinámico**. Controla si Internet Explorer puede desplazarse a los archivos de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] y perderlos. (Opciones Habilitar, Deshabilitar y Preguntar).  
  
- **Aplicaciones de explorador XAML**. Controla si Internet Explorer puede navegar y ejecutar XBAP. (Opciones Habilitar, Deshabilitar y Preguntar).  
  
 De forma predeterminada, esta configuración está habilitada para las zonas **Internet**, **Intranet local**y **sitios de confianza** , y deshabilitada para la zona de **sitios restringidos** .  
  
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
 El control de <xref:System.Windows.Controls.WebBrowser> de WPF se puede usar para hospedar contenido Web. El control WPF <xref:System.Windows.Controls.WebBrowser> contiene el control ActiveX WebBrowser subyacente. WPF proporciona compatibilidad para proteger la aplicación cuando se usa el control de <xref:System.Windows.Controls.WebBrowser> de WPF para hospedar contenido web que no es de confianza. Sin embargo, las aplicaciones deben aplicar directamente algunas características de seguridad mediante el control <xref:System.Windows.Controls.WebBrowser>. Para obtener más información sobre el control ActiveX WebBrowser, consulte introducciones [y tutoriales del control WebBrowser](https://go.microsoft.com/fwlink/?LinkId=179388).  
  
> [!NOTE]
> Esta sección también se aplica al control <xref:System.Windows.Controls.Frame>, ya que usa el <xref:System.Windows.Controls.WebBrowser> para navegar hasta el contenido HTML.  
  
 Si el control de <xref:System.Windows.Controls.WebBrowser> de WPF se usa para hospedar contenido web que no es de confianza, la aplicación debe usar un <xref:System.AppDomain> de confianza parcial para ayudar a aislar el código de la aplicación del código de script HTML potencialmente malintencionado. Esto es especialmente cierto si la aplicación interactúa con el script hospedado mediante el método <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> y la propiedad <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A>. Para obtener más información, consulte [Introducción a los complementos de WPF](./app-development/wpf-add-ins-overview.md).  
  
 Si la aplicación usa el control de <xref:System.Windows.Controls.WebBrowser> de WPF, otra manera de aumentar la seguridad y mitigar los ataques consiste en habilitar los controles de características de Internet Explorer. Los controles de características son adiciones a Internet Explorer que permiten a los administradores y desarrolladores configurar características de Internet Explorer y aplicaciones que hospedan el control ActiveX WebBrowser, que el control de WPF <xref:System.Windows.Controls.WebBrowser> ajusta. Los controles de características se pueden configurar mediante la función [CoInternetSetFeatureEnabled](https://go.microsoft.com/fwlink/?LinkId=179394) o cambiando los valores del registro. Para obtener más información sobre los controles de características, vea [Introducción a los](https://go.microsoft.com/fwlink/?LinkId=179390) controles de características y [controles de características de Internet](https://go.microsoft.com/fwlink/?LinkId=179392).  
  
 Si está desarrollando una aplicación WPF independiente que usa el control de <xref:System.Windows.Controls.WebBrowser> de WPF, WPF habilita automáticamente los siguientes controles de características para su aplicación.  
  
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
  
 Los controles de características se aplican mediante el proceso de creación de instancias del objeto ActiveX WebBrowser. Por lo tanto, si está creando una aplicación independiente que puede navegar a contenido que no es de confianza, debe considerar seriamente la posibilidad de habilitar controles de característica adicionales.  
  
> [!NOTE]
> Esta recomendación se basa en las recomendaciones generales para la seguridad de host MSHTML y SHDOCVW. Para obtener más información, consulte [preguntas más frecuentes sobre la seguridad del host de Mshtml: parte I de II](https://go.microsoft.com/fwlink/?LinkId=179396) y [preguntas más frecuentes sobre la seguridad del host MSHTML: parte II de II](https://go.microsoft.com/fwlink/?LinkId=179415).  
  
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
  
 Si ejecuta una aplicación de explorador XAML de confianza parcial (XBAP) que incluye un control de <xref:System.Windows.Controls.WebBrowser> de WPF en Windows Internet Explorer, WPF hospeda el control ActiveX WebBrowser en el espacio de direcciones del proceso de Internet Explorer. Puesto que el control ActiveX WebBrowser se hospeda en el proceso de Internet Explorer, todos los controles de características de Internet Explorer también están habilitados para el control ActiveX WebBrowser.  
  
 Los objetos XBAP que se ejecutan en Internet Explorer también obtienen un nivel adicional de seguridad en comparación con las aplicaciones independientes normales. Esta seguridad adicional se debe a que Internet Explorer y, por tanto, el control ActiveX WebBrowser, se ejecuta en modo protegido de forma predeterminada en Windows Vista y Windows 7. Para obtener más información acerca del modo protegido, consulte [Descripción y funcionamiento en modo protegido de Internet Explorer](https://go.microsoft.com/fwlink/?LinkId=179393).  
  
> [!NOTE]
> Si intenta ejecutar una aplicación XBAP que incluye un control de <xref:System.Windows.Controls.WebBrowser> de WPF en Firefox, mientras esté en la zona de Internet, se iniciará una <xref:System.Security.SecurityException>. Esto se debe a la directiva de seguridad de WPF.  
  
<a name="APTCA"></a>   
## <a name="disabling-aptca-assemblies-for-partially-trusted-client-applications"></a>Deshabilitar ensamblados APTCA para aplicaciones cliente de confianza parcial  
 Cuando los ensamblados administrados se instalan en la caché de ensamblados global (GAC), se vuelven totalmente confiables, ya que el usuario debe proporcionar permiso explícito para instalarlos. Dado que son de plena confianza, solo las aplicaciones cliente administradas de plena confianza pueden usarlos. Para permitir que las aplicaciones de confianza parcial las utilicen, deben marcarse con el <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA). Solo los ensamblados probados como seguros para la ejecución en confianza parcial se deben marcar con este atributo.  
  
 Sin embargo, es posible que un ensamblado APTCA muestre un error de seguridad después de instalarse en la GAC. Cuando se detecta un error de seguridad, los publicadores de ensamblados pueden producir una actualización de seguridad para corregir el problema en las instalaciones existentes y proteger las instalaciones que se produzcan después de detectar el problema. Una opción para la actualización es desinstalar el ensamblado, aunque eso podría causar que otras aplicaciones cliente de plena confianza que usan el ensamblado dejen de funcionar correctamente.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] proporciona un mecanismo por el que se puede deshabilitar un ensamblado APTCA para XBAP de confianza parcial sin desinstalar el ensamblado APTCA.  
  
 Para deshabilitar un ensamblado APTCA, tiene que crear una clave del Registro especial:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 Se muestra un ejemplo a continuación:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 Esta clave establece una entrada para el ensamblado APTCA. También debe crear un valor en esta clave que habilite o deshabilite el ensamblado. Los siguientes son los detalles del valor:  
  
- Nombre del valor: **APTCA_FLAG**.  
  
- Tipo de valor: **REG_DWORD**.  
  
- Datos del valor: **1** para deshabilitar; **0** para habilitar.  
  
 Si un ensamblado se debe deshabilitar para las aplicaciones cliente de confianza parcial, puede escribir una actualización que cree la clave y el valor del Registro.  
  
> [!NOTE]
> Los ensamblados de .NET Framework principales no se ven afectados al deshabilitarlos de esta manera porque son necesarios para que se ejecuten las aplicaciones administradas. La compatibilidad para deshabilitar ensamblados APTCA está destinada principalmente a aplicaciones de terceros.  
  
<a name="LooseContentSandboxing"></a>   
## <a name="sandbox-behavior-for-loose-xaml-files"></a>Comportamiento de espacio aislado para archivos XAML dinámicos  
 Los archivos [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] sueltos son archivos XAML solo de marcado que no dependen de ningún código subyacente, controlador de eventos o ensamblado específico de la aplicación. Cuando se navega a los archivos [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] sueltos directamente desde el explorador, se cargan en un espacio aislado de seguridad basado en el conjunto de permisos predeterminado de la zona de Internet.  
  
 Sin embargo, el comportamiento de seguridad es diferente cuando se navega por [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] archivos sueltos desde un <xref:System.Windows.Navigation.NavigationWindow> o <xref:System.Windows.Controls.Frame> en una aplicación independiente.  
  
 En ambos casos, el archivo [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] dinámico al que se navega hereda los permisos de su aplicación host. Sin embargo, este comportamiento puede no ser deseable desde una perspectiva de seguridad, especialmente si un archivo de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] suelto fue producido por una entidad que no es de confianza o es desconocida. Este tipo de contenido se conoce como *contenido externo*, y tanto <xref:System.Windows.Controls.Frame> como <xref:System.Windows.Navigation.NavigationWindow> se pueden configurar para aislarlos cuando se navega a. El aislamiento se consigue estableciendo la propiedad **SandboxExternalContent** en true, como se muestra en los ejemplos siguientes para <xref:System.Windows.Controls.Frame> y <xref:System.Windows.Navigation.NavigationWindow>:  
  
 [!code-xaml[SecurityOverviewSnippets#FrameMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xaml[SecurityOverviewSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 Con esta configuración, el contenido externo se carga en un proceso independiente del proceso que hospeda la aplicación. Este proceso está restringido al conjunto de permisos predeterminado de la zona de Internet y lo aísla de forma eficaz desde la aplicación host y el equipo cliente.  
  
> [!NOTE]
> Aunque la navegación a archivos [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] sueltos desde un <xref:System.Windows.Navigation.NavigationWindow> o una <xref:System.Windows.Controls.Frame> en una aplicación independiente se implementa en función de la infraestructura de hospedaje del explorador de WPF, en la que se requiere el proceso PresentationHost, el nivel de seguridad es ligeramente menor que cuando el contenido se carga directamente en Internet Explorer en Windows Vista y Windows 7 (que todavía se realiza a través de PresentationHost). Esto se debe a que una aplicación de WPF independiente que usa un navegador web no proporciona la característica de seguridad adicional de modo protegido de Internet Explorer.  
  
<a name="BestPractices"></a>   
## <a name="resources-for-developing-wpf-applications-that-promote-security"></a>Recursos para desarrollar aplicaciones de WPF que promueven la seguridad  
 A continuación se muestran algunos recursos adicionales para ayudar a desarrollar aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] que promuevan la seguridad:  
  
|Área|Recurso|  
|----------|--------------|  
|Código administrado|[Modelos y prácticas Guía de seguridad para aplicaciones](https://go.microsoft.com/fwlink/?LinkId=117426)|  
|CAS|[Seguridad de acceso del código](../misc/code-access-security.md)|  
|ClickOnce|[Seguridad e implementación ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)|  
|[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]|[Seguridad de confianza parcial de WPF](wpf-partial-trust-security.md)|  
  
## <a name="see-also"></a>Vea también

- [Seguridad de confianza parcial de WPF](wpf-partial-trust-security.md)
- [Estrategia de seguridad de WPF: Seguridad de plataforma](wpf-security-strategy-platform-security.md)
- [Estrategia de seguridad de WPF: Ingeniería de seguridad](wpf-security-strategy-security-engineering.md)
- [Modelos y prácticas Guía de seguridad para aplicaciones](https://go.microsoft.com/fwlink/?LinkId=117426)
- [Seguridad de acceso del código](../misc/code-access-security.md)
- [Seguridad e implementación ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)
- [Información general sobre XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)

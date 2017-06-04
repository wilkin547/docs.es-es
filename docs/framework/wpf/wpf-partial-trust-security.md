---
title: "Seguridad de confianza parcial de WPF | Microsoft Docs"
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
  - "depurar aplicaciones de confianza parcial"
  - "detectar permisos"
  - "requisitos de seguridad de características"
  - "administrar permisos"
  - "aplicaciones de confianza parcial, depurar"
  - "seguridad de confianza parcial"
  - "permisos, detectar"
  - "permisos, administrar"
  - "configuración de seguridad para Internet Explorer"
ms.assetid: ef2c0810-1dbf-4511-babd-1fab95b523b5
caps.latest.revision: 40
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 36
---
# Seguridad de confianza parcial de WPF
<a name="introduction"></a> En general, las aplicaciones de Internet deben tener restringido el acceso directo a los recursos del sistema críticos, a fin de evitar los daños malintencionados.  De manera predeterminada, [!INCLUDE[TLA#tla_html](../../../includes/tlasharptla-html-md.md)] y los lenguajes de script de cliente no pueden tener acceso a los recursos del sistema críticos.  Dado que las aplicaciones [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] hospedadas por el explorador se pueden iniciar desde el explorador, deben cumplir un conjunto de restricciones similar.  Para exigir estas restricciones, [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] se basa en [!INCLUDE[TLA#tla_cas](../../../includes/tlasharptla-cas-md.md)] y [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)] \(consulte [Estrategia de seguridad de WPF: Seguridad de plataforma](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)\).  De manera predeterminada, las aplicaciones hospedadas por el explorador solicitan el conjunto de permisos Zona de Internet de [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)], con independencia de si se inician desde Internet, desde la intranet local o desde el equipo local.  Se dice que las aplicaciones que se ejecutan con menos permisos que el conjunto completo de permisos se están ejecutando con confianza parcial.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] proporciona gran variedad de características de compatibilidad para asegurarse de que se pueda utilizar tanta funcionalidad como sea posible sin riesgo alguno en confianza parcial y, junto con [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)], proporciona la compatibilidad adicional para la programación de confianza parcial.  
  
 Este tema contiene las siguientes secciones:  
  
-   [Compatibilidad con la confianza parcial de las características de WPF](#WPF_Feature_Partial_Trust_Support)  
  
-   [Programación de la confianza parcial](#Partial_Trust_Programming)  
  
-   [Administrar permisos](#Managing_Permissions)  
  
<a name="WPF_Feature_Partial_Trust_Support"></a>   
## Compatibilidad con la confianza parcial de las características de WPF  
 En la tabla siguiente se muestra una lista de las características generales de [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] que resulta seguro utilizar dentro de los límites del conjunto de permisos Zona de Internet.  
  
 Tabla 1: Características de WPF seguras con confianza parcial  
  
|Área de la característica|Característica|  
|-------------------------------|--------------------|  
|General|Explorador \(Ventana\)<br /><br /> Acceso al sitio de origen<br /><br /> Almacenamiento aislado \(límite de 512 KB\)<br /><br /> Proveedores de automatización de la IU<br /><br /> Comandos<br /><br /> Editores de métodos de entrada \(IME\)<br /><br /> Lápiz óptico de Tablet PC y entradas de lápiz<br /><br /> Métodos de arrastrar y colocar simulados mediante eventos Capture y Move del mouse.<br /><br /> OpenFileDialog<br /><br /> Deserialización XAML \(mediante XamlReader.Load\)|  
|Integración en web|Cuadro de diálogo de descarga del explorador<br /><br /> Navegación de nivel superior iniciada por el usuario<br /><br /> mailto:links<br /><br /> Parámetros de identificador uniforme de recursos<br /><br /> HTTPWebRequest<br /><br /> Contenido WPF hospedado en IFRAME<br /><br /> Hospedar páginas HTML del mismo sitio mediante Frame<br /><br /> Hospedar páginas HTML del mismo sitio mediante WebBrowser<br /><br /> Servicios Web \(ASMX\)<br /><br /> Servicios Web \(mediante Windows Communication Foundation\)<br /><br /> Scripting<br /><br /> Modelo de objetos de documento|  
|Elementos visuales|2D y 3D<br /><br /> Animación<br /><br /> Multimedia \(sitio de origen y entre dominios\)<br /><br /> Imágenes\/audio\/vídeo|  
|Lectura|Documentos dinámicos<br /><br /> Documentos XPS<br /><br /> Fuentes incrustadas y del sistema<br /><br /> Fuentes CFF y TrueType|  
|Edición|Revisión ortográfica<br /><br /> RichTextBox<br /><br /> Texto simple y compatibilidad de portapapeles de entradas de lápiz<br /><br /> Acción de pegar iniciada por el usuario<br /><br /> Copiar contenido seleccionado|  
|Controles|Controles generales|  
  
 En esta tabla se muestran las características de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] de alto nivel.  Para obtener más información detallada, en [!INCLUDE[TLA#tla_lhsdk](../../../includes/tlasharptla-lhsdk-md.md)] se documentan los permisos que necesita cada miembro en [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)].  Asimismo, las características siguientes ofrecen información más detallada relativa a la ejecución de la confianza parcial, incluidas algunas consideraciones especiales.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] \(consulte [Información general sobre XAML \(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)\).  
  
-   Menús emergentes \(consulte <xref:System.Windows.Controls.Primitives.Popup?displayProperty=fullName>\).  
  
-   Arrastrar y colocar \(consulte [Información general sobre la función de arrastrar y colocar](../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)\).  
  
-   Portapapeles \(consulte <xref:System.Windows.Clipboard?displayProperty=fullName>\).  
  
-   Imágenes \(consulte <xref:System.Windows.Controls.Image?displayProperty=fullName>\).  
  
-   Serialización \(consulte <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=fullName>, <xref:System.Windows.Markup.XamlWriter.Save%2A?displayProperty=fullName>\).  
  
-   Cuadro de diálogo de apertura de archivos \(consulte <xref:Microsoft.Win32.OpenFileDialog?displayProperty=fullName>\).  
  
 En la tabla siguiente se describen las características de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] que no es seguro ejecutar dentro de los límites del conjunto de permisos Zona de Internet.  
  
 Tabla 2: Características de WPF no seguras con confianza parcial  
  
|Área de la característica|Característica|  
|-------------------------------|--------------------|  
|General|Ventana \(ventanas y cuadros de diálogo definidos por la aplicación\)<br /><br /> SaveFileDialog<br /><br /> Sistema de archivos<br /><br /> Acceso al Registro<br /><br /> Arrastrar y colocar<br /><br /> Serialización XAML \(mediante XamlWriter.Save\)<br /><br /> Clientes de automatización de la interfaz de usuario<br /><br /> Acceso a la ventana de origen \(HwndHost\)<br /><br /> Compatibilidad plena con voz<br /><br /> Interoperabilidad con formularios Windows Forms|  
|Elementos visuales|Efectos de imagen<br /><br /> Codificación de imágenes|  
|Edición|Portapapeles de formato de texto enriquecido<br /><br /> Compatibilidad plena con XAML|  
  
<a name="Partial_Trust_Programming"></a>   
## Programación de la confianza parcial  
 Para aplicaciones [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)], el código que supera el conjunto de permisos predeterminado tendrá un comportamiento diferente según la zona de seguridad.  En algunos casos, el usuario recibirá una advertencia cuando intente instalarla.  El usuario puede continuar o cancelar la instalación.  En la tabla siguiente se describe el comportamiento de la aplicación para cada zona de seguridad y lo que tiene que hacer para que la aplicación reciba plena confianza.  
  
|Zona de seguridad|Comportamiento|Obtener plena confianza|  
|-----------------------|--------------------|-----------------------------|  
|Equipo local|Plena confianza automática|No se requiere ninguna acción.|  
|Intranet y sitios de confianza|Solicitar plena confianza|Firmar la aplicación XBAP con un certificado para que el usuario vea el origen en el indicador.|  
|Internet|Se produce un error "Confianza no concedida"|Firmar la aplicación XBAP con un certificado.|  
  
> [!NOTE]
>  El comportamiento descrito en la tabla anterior es para las aplicaciones XBAP de plena confianza que no siguen el modelo de implementación de confianza de ClickOnce.  
  
 En general, es probable que el código que puede superar los permisos concedidos sea código común que se comparte entre las aplicaciones independientes y hospedadas por explorador.  [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] y [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] proporcionan varias técnicas para administrar este escenario.  
  
<a name="Detecting_Permissions_using_CAS"></a>   
### Detectar permisos mediante CAS  
 En algunas situaciones, es posible que el código compartido en los ensamblados de bibliotecas se utilice en aplicaciones independientes y [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)].  En estos casos, el código puede ejecutar funcionalidad que podría requerir más permisos de los permitidos por el conjunto de permisos de la aplicación.  La aplicación puede detectar si tiene un permiso determinado o no mediante la seguridad de [!INCLUDE[TLA#tla_winfx](../../../includes/tlasharptla-winfx-md.md)].  En particular, puede comprobar si tiene un permiso concreto llamando al método <xref:System.Security.CodeAccessPermission.Demand%2A> en la instancia del permiso deseado.  Esto se muestra en el ejemplo siguiente, que contiene código que consulta si tiene la capacidad de guardar un archivo en el disco local:  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode2)]  
  
 Si una aplicación no tiene el permiso deseado, la llamada a <xref:System.Security.CodeAccessPermission.Demand%2A> provocará una excepción de seguridad.  De lo contrario, se ha concedido el permiso.  `IsPermissionGranted` encapsula este comportamiento y devuelve `true` o `false`, según corresponda.  
  
<a name="Graceful_Degradation_of_Functionality"></a>   
### Degradación correcta de la funcionalidad  
 Poder detectar si el código tiene permiso para lo que necesita hacer es interesante para el código que se puede ejecutar desde zonas diferentes.  Aunque detectar la zona es necesario, resulta mucho mejor proporcionar una alternativa al usuario, si es posible.  Por ejemplo, una aplicación de plena confianza suele permitir al usuario crear los archivos que desee en cualquier lugar, mientras que una aplicación de confianza parcial sólo permite crearlos en almacenamiento aislado.  Si el código para crear un archivo existe en un ensamblado compartido por aplicaciones de plena confianza \(independientes\) y de confianza parcial \(hospedadas por explorador\), y ambas aplicaciones desean que los usuarios puedan crear archivos, el código compartido debería detectar si se ejecuta con confianza parcial o plena antes de crear un archivo en la ubicación adecuada.  En el código siguiente se muestran ambas operaciones.  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode2)]  
  
 En muchos casos, debe existir una alternativa de confianza parcial.  
  
 En un entorno controlado, como una intranet, los marcos de trabajo administrados personalizados se pueden instalar en toda la base de clientes en [!INCLUDE[TLA#tla_gac](../../../includes/tlasharptla-gac-md.md)].  Estas bibliotecas pueden ejecutar código que requiere plena confianza y se puede hacer referencia a ellas en las aplicaciones que solo tienen confianza parcial mediante <xref:System.Security.AllowPartiallyTrustedCallersAttribute> \(para obtener más información, vea [Seguridad](../../../docs/framework/wpf/security-wpf.md) y [Estrategia de seguridad de WPF: Seguridad de plataforma](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)\).  
  
<a name="Browser_Host_Detection"></a>   
### Detección del host del explorador  
 Utilizar [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] para comprobar los permisos es una técnica conveniente cuando se necesita comprobar los permisos uno a uno.  Sin embargo, esta técnica depende de que se detecten las excepciones como parte de procesamiento normal, algo que, en general, no se recomienda, y que puede dar lugar a problemas de rendimiento.  En su lugar, si [!INCLUDE[TLA#tla_xbap](../../../includes/tlasharptla-xbap-md.md)] solamente se ejecuta dentro del espacio aislado de la Zona de Internet, puede usar la propiedad <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=fullName>, que devuelve true para [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
> [!NOTE]
>  <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A> únicamente distingue si una aplicación se está ejecutando en un explorador, no detecta con qué conjunto de permisos se está ejecutando.  
  
<a name="Managing_Permissions"></a>   
## Administrar permisos  
 De forma predeterminada, las [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] se ejecutan con confianza parcial \(conjunto de permisos de Zona de Internet predeterminado\).  Sin embargo, dependiendo de los requisitos de la aplicación, es posible cambiar el conjunto de permisos predeterminado.  Por ejemplo, si se inician [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] desde una intranet local, puede aprovechar un conjunto de permisos mayor, que se muestra en la tabla siguiente.  
  
 Tabla 3: Permisos de intranet local y de Internet  
  
|Permiso|Atributo|LocalIntranet|Internet|  
|-------------|--------------|-------------------|--------------|  
|DNS|Tener acceso a los servidores DNS|Sí|No|  
|Variables de entorno|Lectura|Sí|No|  
|Cuadros de diálogo de archivo|Abra .|Sí|Sí|  
|Cuadros de diálogo de archivo|Sin restricciones|Sí|No|  
|Almacenamiento aislado|Aislamiento de ensamblados por usuario|Sí|No|  
|Almacenamiento aislado|Aislamiento desconocido|Sí|Sí|  
|Almacenamiento aislado|Cuota de usuario ilimitada|Sí|No|  
|Multimedia|Audio, vídeo e imágenes seguros|Sí|Sí|  
|Impresión|Impresión predeterminada|Sí|No|  
|Impresión|Impresión segura|Sí|Sí|  
|Reflexión|Emisión|Sí|No|  
|Seguridad|Ejecución de código administrado|Sí|Sí|  
|Seguridad|Declaración de permisos concedidos|Sí|No|  
|Interfaz de usuario|Sin restricciones|Sí|No|  
|Interfaz de usuario|Ventanas de nivel superior seguras|Sí|Sí|  
|Interfaz de usuario|Portapapeles propio|Sí|Sí|  
|Web Browser|Navegación de marcos segura en HTML|Sí|Sí|  
  
> [!NOTE]
>  Solo se permite cortar y pegar en la confianza parcial cuando sea iniciado por el usuario.  
  
 Si necesita aumentar los permisos, es preciso modificar la configuración del proyecto y el manifiesto de la aplicación ClickOnce.  Para obtener más información, vea [Información general sobre las aplicaciones de explorador XAML de WPF](../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  Los siguientes documentos también pueden ser útiles.  
  
-   [Mage.exe \(Herramienta de generación y edición de manifiestos\)](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md).  
  
-   [MageUI.exe \(Herramienta de generación y edición de manifiestos, cliente gráfico\)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).  
  
-   [Proteger las aplicaciones ClickOnce](../Topic/Securing%20ClickOnce%20Applications.md).  
  
 Si [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] requiere plena confianza, puede utilizar las mismas herramientas para aumentar los permisos solicitados,  Aunque una [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] solo recibirá plena confianza si se instala e inicia en el equipo local, la intranet o una dirección URL incluida en la lista de sitios permitidos o de confianza del explorador.  Si la aplicación se instala desde la intranet o un sitio de confianza, el usuario recibirá el mensaje estándar de ClickOnce para notificarle los permisos elevados.  El usuario puede continuar o cancelar la instalación.  
  
 Como alternativa, se puede utilizar el modelo de implementación de confianza de ClickOnce para realizar una implementación de plena confianza desde una zona de seguridad.  Para obtener más información, vea [Información general sobre la implementación de aplicaciones de confianza](../Topic/Trusted%20Application%20Deployment%20Overview.md) y [Seguridad](../../../docs/framework/wpf/security-wpf.md).  
  
## Vea también  
 [Seguridad](../../../docs/framework/wpf/security-wpf.md)   
 [Estrategia de seguridad de WPF: Seguridad de plataforma](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)   
 [Estrategia de seguridad de WPF: Ingeniería de seguridad](../../../docs/framework/wpf/wpf-security-strategy-security-engineering.md)
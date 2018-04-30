---
title: Seguridad de confianza parcial de WPF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- partial trust security [WPF]
- detecting permissions [WPF]
- security settings for Internet Explorer [WPF]
- partial trust applications [WPF], debugging
- permissions [WPF], managing
- debugging partial trust applications [WPF]
- permissions [WPF], detecting
- feature security requirements [WPF]
- managing permissions [WPF]
ms.assetid: ef2c0810-1dbf-4511-babd-1fab95b523b5
caps.latest.revision: 40
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 023de9e20206411f7dd6774553ae39eefaa508a0
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="wpf-partial-trust-security"></a>Seguridad de confianza parcial de WPF
<a name="introduction"></a> En general, deben restringirse las aplicaciones de Internet para que no tengan acceso directo a recursos críticos del sistema y así evitar daños malintencionados. De forma predeterminada, [!INCLUDE[TLA#tla_html](../../../includes/tlasharptla-html-md.md)] y lenguajes de scripting del lado cliente no podrá tener acceso a recursos críticos del sistema. Dado que las aplicaciones hospedadas en Explorador de Windows Presentation Foundation (WPF) se pueden iniciar desde el explorador, deben cumplir un conjunto similar de restricciones. Para aplicar estas restricciones, [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] se basa en ambos [!INCLUDE[TLA#tla_cas](../../../includes/tlasharptla-cas-md.md)] y [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)] (consulte [estrategia de seguridad de WPF: seguridad de la plataforma](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)). De forma predeterminada, las aplicaciones hospedadas en explorador solicitan la zona de Internet [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] conjunto de permisos, independientemente de si se inician desde Internet, intranet local o el equipo local. Las aplicaciones que se ejecutan con menos permisos que el conjunto completo de permisos se dice que se ejecutan con confianza parcial.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Proporciona una amplia variedad de soporte técnico para asegurarse de que puede utilizarse con seguridad tanta funcionalidad como sea posible en confianza parcial y, junto con [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)], proporciona compatibilidad adicional para la programación de confianza parcial.  
  
 Este tema contiene las siguientes secciones:  
  
-   [Compatibilidad de confianza parcial de las características de WPF](#WPF_Feature_Partial_Trust_Support)  
  
-   [Programación de confianza parcial](#Partial_Trust_Programming)  
  
-   [Administrar permisos](#Managing_Permissions)  
  
<a name="WPF_Feature_Partial_Trust_Support"></a>   
## <a name="wpf-feature-partial-trust-support"></a>Compatibilidad de confianza parcial de las características de WPF  
 En la tabla siguiente se enumera las características de alto nivel de Windows Presentation Foundation (WPF) que son seguras para usarse dentro de los límites del conjunto de permisos de zona de Internet.  
  
 Tabla 1: Características de WPF que son seguras en confianza parcial  
  
|Área de características|Característica|  
|------------------|-------------|  
|General|Ventana del explorador<br /><br /> Acceso al sitio de origen<br /><br /> IsolatedStorage (límite de 512 KB)<br /><br /> Proveedores de UIAutomation<br /><br /> Comandos<br /><br /> Editores de métodos de entrada (IMEs)<br /><br /> Lápiz y entrada de lápiz de tableta<br /><br /> Movimiento simulado de arrastrar y colocar con los eventos de captura y movimiento del mouse<br /><br /> OpenFileDialog<br /><br /> Deserialización XAML (mediante XamlReader.Load)|  
|Integración en Internet|Cuadro de diálogo de descarga del explorador<br /><br /> Navegación iniciada por el usuario de nivel superior<br /><br /> mailto:links<br /><br /> Parámetros de identificador de recursos uniforme<br /><br /> HTTPWebRequest<br /><br /> Contenido de WPF hospedado en un IFRAME<br /><br /> Hospedaje de páginas HTML del mismo sitio con marco<br /><br /> Hospedaje de páginas HTML del mismo sitio con WebBrowser<br /><br /> Servicios web (ASMX)<br /><br /> Servicios Web (con Windows Communication Foundation)<br /><br /> Scripting<br /><br /> Modelo de objetos de documento|  
|Objetos visuales|2D y 3D<br /><br /> Animación<br /><br /> Multimedia (sitio de origen y entre dominios)<br /><br /> Creación de imágenes, audio y vídeo|  
|Lectura|FlowDocuments<br /><br /> Documentos XPS<br /><br /> Fuentes insertadas y del sistema<br /><br /> Fuentes CFF y TrueType|  
|Editar|Revisión ortográfica<br /><br /> RichTextBox<br /><br /> Compatibilidad con texto sin formato y portapapeles de entrada de lápiz<br /><br /> Pegado iniciado por el usuario<br /><br /> Copiar contenido seleccionado|  
|Controles|Controles generales|  
  
 Esta tabla se recogen los [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] características en un nivel superior. Para obtener más información, la [!INCLUDE[TLA#tla_lhsdk](../../../includes/tlasharptla-lhsdk-md.md)] documenta los permisos necesarios para cada miembro de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]. Además, las características siguientes ofrecen más información detallada sobre la ejecución de confianza parcial, incluidas algunas consideraciones especiales.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] (consulte [información general sobre XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)).  
  
-   Elementos emergentes (consulte <xref:System.Windows.Controls.Primitives.Popup?displayProperty=nameWithType>).  
  
-   Arrastrar y colocar (consulte [de arrastrar y colocar, información general sobre](../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)).  
  
-   Portapapeles (consulte <xref:System.Windows.Clipboard?displayProperty=nameWithType>).  
  
-   Creación de imágenes (consulte <xref:System.Windows.Controls.Image?displayProperty=nameWithType>).  
  
-   Serialización (vea <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>, <xref:System.Windows.Markup.XamlWriter.Save%2A?displayProperty=nameWithType>).  
  
-   Abra el cuadro de diálogo de archivo (vea <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>).  
  
 La siguiente tabla se describen los [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] conjunto de permisos de la zona de características que no son seguros para que se ejecute dentro de los límites de Internet.  
  
 Tabla 2: Características de WPF que no son seguras en confianza parcial  
  
|Área de características|Característica|  
|------------------|-------------|  
|General|Ventana (ventanas y cuadros de diálogo definidos por la aplicación)<br /><br /> SaveFileDialog<br /><br /> Sistema de archivos<br /><br /> Acceso al Registro<br /><br /> Arrastrar y colocar<br /><br /> Serialización XAML (mediante XamlWriter.Save)<br /><br /> Clientes de UIAutomation<br /><br /> Acceso a la ventana de origen (HwndHost)<br /><br /> Compatibilidad total con Voz<br /><br /> Interoperabilidad de Windows Forms|  
|Objetos visuales|Efectos de imagen<br /><br /> Codificación de imagen|  
|Editar|Portapapeles con formato de texto enriquecido<br /><br /> Compatibilidad total con XAML|  
  
<a name="Partial_Trust_Programming"></a>   
## <a name="partial-trust-programming"></a>Programación de confianza parcial  
 Para [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] de las aplicaciones, el código que supera el conjunto de permisos predeterminado tendrá un comportamiento diferente según la zona de seguridad. En algunos casos, el usuario recibirá una advertencia al intentar instalarla. El usuario puede elegir continuar o cancelar la instalación. En la tabla siguiente se describe el comportamiento de la aplicación para cada zona de seguridad y qué se debe hacer para que la aplicación reciba plena confianza.  
  
|Zona de seguridad|Comportamiento|Obtener plena confianza|  
|-------------------|--------------|------------------------|  
|Equipo local|Plena confianza automática|No es necesario realizar ninguna acción.|  
|Intranet y sitios de confianza|Pedir plena confianza|Firme la aplicación XBAP con un certificado para que el usuario vea el origen en la petición.|  
|Internet|Error: "Confianza no concedida"|Firme XBAP con un certificado.|  
  
> [!NOTE]
>  El comportamiento descrito en la tabla anterior es para XBAP de plena confianza que no siguen el modelo de implementación de confianza ClickOnce.  
  
 En general, el código que puede superar los permisos permitidos es probable que sea código común compartido entre aplicaciones independientes y hospedadas en explorador. [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] y [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] ofrecen varias técnicas para administrar este escenario.  
  
<a name="Detecting_Permissions_using_CAS"></a>   
### <a name="detecting-permissions-using-cas"></a>Detectar permisos con CAS  
 En algunas situaciones, es posible que el código compartido en los ensamblados de biblioteca que va a usar ambas aplicaciones independientes y [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)]. En estos casos, es posible que el código ejecute funcionalidades que podrían necesitar más permisos que los que se incluyen en el conjunto de permisos que concede la aplicación. La aplicación puede detectar si tiene un permiso determinado mediante el uso de seguridad de Microsoft .NET Framework o no. En concreto, puede probar si tiene un permiso específico mediante una llamada a la <xref:System.Security.CodeAccessPermission.Demand%2A> en la instancia del permiso deseado. Esto se muestra en el ejemplo siguiente, que contiene código que consulta si tiene la capacidad de guardar un archivo en el disco local:  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode2)]  
  
 Si una aplicación no tiene el permiso deseado, la llamada a <xref:System.Security.CodeAccessPermission.Demand%2A> se iniciará una excepción de seguridad. De lo contrario, se concedió el permiso. `IsPermissionGranted` encapsula este comportamiento y devuelve `true` o `false` según corresponda.  
  
<a name="Graceful_Degradation_of_Functionality"></a>   
### <a name="graceful-degradation-of-functionality"></a>Degradación correcta de la funcionalidad  
 Poder detectar si el código tiene permiso para lo que necesita hacer es interesante para código que se puede ejecutar desde distintas zonas. Detectar la zona es una cosa, pero es mucho mejor proporcionar una alternativa para el usuario, si es posible. Por ejemplo, una aplicación de plena confianza normalmente permite a los usuarios crear archivos donde quieran, mientras que una aplicación de confianza parcial solo permite crear archivos en almacenamiento aislado. Si el código para crear un archivo existe en un ensamblado que comparten aplicaciones (independientes) de plena confianza y aplicaciones (hospedadas en explorador) de confianza parcial, y ambas aplicaciones quieren que los usuarios puedan crear archivos, el código compartido debe detectar si se ejecuta con confianza plena o parcial antes de crear el archivo en la ubicación adecuada. En el código siguiente se muestran ambas opciones.  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode2)]  
  
 En muchos casos, debería poder encontrar una alternativa de confianza parcial.  
  
 En un entorno controlado, como una intranet, marcos de trabajo administrados personalizados pueden instalarse en el cliente que se base en la [!INCLUDE[TLA#tla_gac](../../../includes/tlasharptla-gac-md.md)]. Estas bibliotecas pueden ejecutar código que requiere plena confianza y puede hacer referencia desde las aplicaciones que solo se permiten la confianza parcial mediante <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (para obtener más información, consulte [seguridad](../../../docs/framework/wpf/security-wpf.md) y [seguridad de WPF Estrategia - seguridad de plataforma](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)).  
  
<a name="Browser_Host_Detection"></a>   
### <a name="browser-host-detection"></a>Detección de host del explorador  
 Usar [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] comprobar los permisos es una técnica conveniente cuando necesite comprobar de forma por cada permiso. Sin embargo, esta técnica depende de la detección de excepciones como parte del procesamiento normal, que, en general, no se recomienda y puede tener problemas de rendimiento. En su lugar, si su [!INCLUDE[TLA#tla_xbap](../../../includes/tlasharptla-xbap-md.md)] sólo se puede ejecutar en el espacio aislado de zona de Internet, puede usar el <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> propiedad, que devuelve true para [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
> [!NOTE]
>  <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A> solo se distingue si una aplicación se ejecuta en un explorador, no el conjunto de permisos de una aplicación se está ejecutando con.  
  
<a name="Managing_Permissions"></a>   
## <a name="managing-permissions"></a>Gestión de permisos  
 De forma predeterminada, [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] ejecuta con confianza parcial (conjunto de permisos de zona de Internet de forma predeterminada). Sin embargo, según los requisitos de la aplicación, es posible cambiar el conjunto de permisos predeterminado. Por ejemplo, si una [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] se inicia desde una intranet local, que puede aprovechar al máximo un aumento del conjunto de permisos, que se muestra en la tabla siguiente.  
  
 Tabla 3: Permisos de LocalIntranet e Internet  
  
|Permiso|Atributo|LocalIntranet|Internet|  
|----------------|---------------|-------------------|--------------|  
|DNS|Servidores DNS de acceso|Sí|No|  
|Variables de entorno|Leer|Sí|No|  
|Cuadros de diálogo de archivo|Abrir|Sí|Sí|  
|Cuadros de diálogo de archivo|Sin restricción|Sí|No|  
|Almacenamiento aislado|Aislamiento de ensamblados por el usuario|Sí|No|  
|Almacenamiento aislado|Aislamiento desconocido|Sí|Sí|  
|Almacenamiento aislado|Cuota de usuario ilimitada|Sí|No|  
|Multimedia|Imágenes, vídeo y audio seguros|Sí|Sí|  
|Impresión|Impresión predeterminada|Sí|No|  
|Impresión|Impresión segura|Sí|Sí|  
|Reflexión|Emitir|Sí|No|  
|Seguridad|Ejecución de código administrado|Sí|Sí|  
|Seguridad|Permisos de aserción concedidos|Sí|No|  
|Interfaz de usuario|Sin restricción|Sí|No|  
|Interfaz de usuario|Ventanas seguras de nivel superior|Sí|Sí|  
|Interfaz de usuario|Portapapeles propio|Sí|Sí|  
|Explorador web|Navegación de marcos segura a HTML|Sí|Sí|  
  
> [!NOTE]
>  Cortar y pegar solo se permite con confianza parcial cuando el usuario inicia la acción.  
  
 Si necesita aumentar los permisos, debe cambiar la configuración del proyecto y el manifiesto de aplicación ClickOnce. Para obtener más información, vea [Información general sobre las aplicaciones de explorador XAML de WPF](../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md). Los siguientes documentos también pueden ser útiles.  
  
-   [Mage.exe (Herramienta de generación y edición de manifiestos)](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md).  
  
-   [MageUI.exe (Herramienta de generación y edición de manifiestos, cliente gráfico)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).  
  
-   [Proteger las aplicaciones ClickOnce](/visualstudio/deployment/securing-clickonce-applications).  
  
 Si su [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] requiere plena confianza, puede utilizar las mismas herramientas para aumentar los permisos solicitados. Aunque un [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] solo recibirá plena confianza si se instala en y se inicia desde el equipo local, la intranet o desde una dirección URL que se muestra en el Explorador de confianza o sitios permitidos. Si la aplicación se instala desde la intranet o un sitio de confianza, el usuario recibirá el mensaje estándar de ClickOnce, que le notificará los permisos elevados. El usuario puede elegir continuar con la instalación o cancelarla.  
  
 Como alternativa, puede usar el modelo de implementación de confianza de ClickOnce para realizar una implementación de plena confianza desde cualquier zona de seguridad. Para obtener más información, consulte [Trusted Application Deployment Overview](/visualstudio/deployment/trusted-application-deployment-overview) y [seguridad](../../../docs/framework/wpf/security-wpf.md).  
  
## <a name="see-also"></a>Vea también  
 [Seguridad](../../../docs/framework/wpf/security-wpf.md)  
 [Estrategia de seguridad de WPF: Seguridad de plataforma](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)  
 [Estrategia de seguridad de WPF: Ingeniería de seguridad](../../../docs/framework/wpf/wpf-security-strategy-security-engineering.md)

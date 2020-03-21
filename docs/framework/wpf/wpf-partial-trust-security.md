---
title: Seguridad de confianza parcial
ms.date: 03/30/2017
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
ms.openlocfilehash: 99c7d9cfae2b137053ca77d9e3d7055b4674ce5b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174581"
---
# <a name="wpf-partial-trust-security"></a>Seguridad de confianza parcial de WPF
<a name="introduction"></a> En general, deben restringirse las aplicaciones de Internet para que no tengan acceso directo a recursos críticos del sistema y así evitar daños malintencionados. De forma predeterminada, los lenguajes de scripting HTML y del lado cliente no pueden acceder a los recursos críticos del sistema. Dado que las aplicaciones hospedadas en el explorador de Windows Presentation Foundation (WPF) se pueden iniciar desde el explorador, deben cumplir un conjunto similar de restricciones. Para aplicar estas restricciones, WPFWPF se basa en seguridad de acceso de código (CAS) y ClickOnce (consulte Estrategia de seguridad de [WPF - Seguridad](wpf-security-strategy-platform-security.md)de plataforma ). De forma predeterminada, las aplicaciones hospedadas en el explorador solicitan el conjunto de permisos CAS de zona de Internet, independientemente de si se inician desde Internet, la intranet local o el equipo local. Las aplicaciones que se ejecutan con menos permisos que el conjunto completo de permisos se dice que se ejecutan con confianza parcial.  
  
 WPFWPF proporciona una amplia variedad de compatibilidad para garantizar que la mayor funcionalidad posible se puede usar de forma segura en confianza parcial y, junto con CAS, proporciona compatibilidad adicional para la programación de confianza parcial.  
  
 Este tema contiene las siguientes secciones:  
  
- [Compatibilidad de confianza parcial de las características de WPF](#WPF_Feature_Partial_Trust_Support)  
  
- [Programación de confianza parcial](#Partial_Trust_Programming)  
  
- [Administrar permisos](#Managing_Permissions)  
  
<a name="WPF_Feature_Partial_Trust_Support"></a>
## <a name="wpf-feature-partial-trust-support"></a>Compatibilidad de confianza parcial de las características de WPF  
 En la tabla siguiente se enumeran las características de alto nivel de Windows Presentation Foundation (WPF) que son seguras de usar dentro de los límites del conjunto de permisos de zona de Internet.  
  
 Tabla 1: Características de WPF que son seguras en confianza parcial  
  
|Área de características|Característica|  
|------------------|-------------|  
|General|Ventana del explorador<br /><br /> Acceso al sitio de origen<br /><br /> IsolatedStorage (límite de 512 KB)<br /><br /> Proveedores de UIAutomation<br /><br /> Comandos<br /><br /> Editores de métodos de entrada (IMEs)<br /><br /> Lápiz y entrada de lápiz de tableta<br /><br /> Movimiento simulado de arrastrar y colocar con los eventos de captura y movimiento del mouse<br /><br /> OpenFileDialog<br /><br /> Deserialización XAML (mediante XamlReader.Load)|  
|Integración en Internet|Cuadro de diálogo de descarga del explorador<br /><br /> Navegación iniciada por el usuario de nivel superior<br /><br /> mailto:links<br /><br /> Parámetros de identificador de recursos uniforme<br /><br /> HTTPWebRequest<br /><br /> Contenido de WPF hospedado en un IFRAME<br /><br /> Hospedaje de páginas HTML del mismo sitio con marco<br /><br /> Hospedaje de páginas HTML del mismo sitio con WebBrowser<br /><br /> Servicios web (ASMX)<br /><br /> Servicios Web (con Windows Communication Foundation)<br /><br /> Scripting<br /><br /> Modelo de objetos de documento|  
|Objetos visuales|2D y 3D<br /><br /> Animación<br /><br /> Multimedia (sitio de origen y entre dominios)<br /><br /> Creación de imágenes, audio y vídeo|  
|Lectura|FlowDocuments<br /><br /> Documentos XPS<br /><br /> Fuentes insertadas y del sistema<br /><br /> Fuentes CFF y TrueType|  
|Editar|Revisión ortográfica<br /><br /> RichTextBox<br /><br /> Compatibilidad con texto sin formato y portapapeles de entrada de lápiz<br /><br /> Pegado iniciado por el usuario<br /><br /> Copiar contenido seleccionado|  
|Controles|Controles generales|  
  
 Esta tabla cubre las características de WPFWPF en un nivel alto. Para obtener información más detallada, el Windows SDK documenta los permisos que requiere cada miembro en WPFWPF. Además, las características siguientes ofrecen más información detallada sobre la ejecución de confianza parcial, incluidas algunas consideraciones especiales.  
  
- [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)](vea [Información general sobre XAML (WPF)).](../../desktop-wpf/fundamentals/xaml.md)  
  
- Ventanas emergentes <xref:System.Windows.Controls.Primitives.Popup?displayProperty=nameWithType>(consulte ).  
  
- Arrastrar y colocar (consulte Información general sobre [arrastrar y colocar](./advanced/drag-and-drop-overview.md)).  
  
- Portapapeles <xref:System.Windows.Clipboard?displayProperty=nameWithType>(consulte ).  
  
- Imágenes <xref:System.Windows.Controls.Image?displayProperty=nameWithType>(ver ).  
  
- Serialización <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>(consulte , <xref:System.Windows.Markup.XamlWriter.Save%2A?displayProperty=nameWithType>).  
  
- Abra el cuadro <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>de diálogo Archivo (consulte ).  
  
 En la tabla siguiente se describen las características de WPFWPF que no son seguras para ejecutarse dentro de los límites del conjunto de permisos de zona de Internet.  
  
 Tabla 2: Características de WPF que no son seguras en confianza parcial  
  
|Área de características|Característica|  
|------------------|-------------|  
|General|Ventana (ventanas y cuadros de diálogo definidos por la aplicación)<br /><br /> SaveFileDialog<br /><br /> Sistema de archivos<br /><br /> Acceso al Registro<br /><br /> Arrastrar y colocar<br /><br /> Serialización XAML (mediante XamlWriter.Save)<br /><br /> Clientes de UIAutomation<br /><br /> Acceso a la ventana de origen (HwndHost)<br /><br /> Compatibilidad total con Voz<br /><br /> Interoperabilidad de Windows Forms|  
|Objetos visuales|Efectos de imagen<br /><br /> Codificación de imagen|  
|Editar|Portapapeles con formato de texto enriquecido<br /><br /> Compatibilidad total con XAML|  
  
<a name="Partial_Trust_Programming"></a>
## <a name="partial-trust-programming"></a>Programación de confianza parcial  
 Para las aplicaciones XBAP, el código que supere el conjunto de permisos predeterminado tendrá un comportamiento diferente en función de la zona de seguridad. En algunos casos, el usuario recibirá una advertencia al intentar instalarlo. El usuario puede elegir continuar con la instalación o cancelarla. En la tabla siguiente se describe el comportamiento de la aplicación para cada zona de seguridad y qué se debe hacer para que la aplicación reciba plena confianza.  
  
|Zona de seguridad|Comportamiento|Obtener plena confianza|  
|-------------------|--------------|------------------------|  
|Equipo local|Plena confianza automática|No se requiere ninguna acción.|  
|Intranet y sitios de confianza|Pedir plena confianza|Firme la aplicación XBAP con un certificado para que el usuario vea el origen en la petición.|  
|Internet|Error: "Confianza no concedida"|Firme la aplicación XBAP con un certificado.|  
  
> [!NOTE]
> El comportamiento descrito en la tabla anterior es para XBAP de plena confianza que no siguen el modelo de implementación de confianza ClickOnce.  
  
 En general, el código que puede superar los permisos permitidos es probable que sea código común compartido entre aplicaciones independientes y hospedadas en explorador. CAS y WPFWPF ofrecen varias técnicas para administrar este escenario.  
  
<a name="Detecting_Permissions_using_CAS"></a>
### <a name="detecting-permissions-using-cas"></a>Detectar permisos con CAS  
 En algunas situaciones, es posible que el código compartido en los ensamblados de biblioteca sea utilizado por aplicaciones independientes y XBAPs. En estos casos, es posible que el código ejecute funcionalidades que podrían necesitar más permisos que los que se incluyen en el conjunto de permisos que concede la aplicación. La aplicación puede detectar si tiene o no un permiso determinado mediante la seguridad de Microsoft .NET Framework. En concreto, puede probar si tiene un <xref:System.Security.CodeAccessPermission.Demand%2A> permiso específico llamando al método en la instancia del permiso deseado. Esto se muestra en el ejemplo siguiente, que contiene código que consulta si tiene la capacidad de guardar un archivo en el disco local:  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode2)]  
  
 Si una aplicación no tiene el permiso <xref:System.Security.CodeAccessPermission.Demand%2A> deseado, la llamada a producirá una excepción de seguridad. De lo contrario, se concedió el permiso. `IsPermissionGranted`encapsula este comportamiento `true` y `false` devuelve o según corresponda.  
  
<a name="Graceful_Degradation_of_Functionality"></a>
### <a name="graceful-degradation-of-functionality"></a>Degradación correcta de la funcionalidad  
 Poder detectar si el código tiene permiso para lo que necesita hacer es interesante para código que se puede ejecutar desde distintas zonas. Detectar la zona es una cosa, pero es mucho mejor proporcionar una alternativa para el usuario, si es posible. Por ejemplo, una aplicación de plena confianza normalmente permite a los usuarios crear archivos donde quieran, mientras que una aplicación de confianza parcial solo permite crear archivos en almacenamiento aislado. Si el código para crear un archivo existe en un ensamblado que comparten aplicaciones (independientes) de plena confianza y aplicaciones (hospedadas en explorador) de confianza parcial, y ambas aplicaciones quieren que los usuarios puedan crear archivos, el código compartido debe detectar si se ejecuta con confianza plena o parcial antes de crear el archivo en la ubicación adecuada. En el código siguiente se muestran ambas opciones.  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode2)]  
  
 En muchos casos, debería poder encontrar una alternativa de confianza parcial.  
  
 En un entorno controlado, como una intranet, se pueden instalar marcos administrados personalizados en toda la base de clientes en la caché global de ensamblados (GAC). Estas bibliotecas pueden ejecutar código que requiere plena confianza y se hace <xref:System.Security.AllowPartiallyTrustedCallersAttribute> referencia a ellas desde aplicaciones a las que solo se permite la confianza parcial mediante el uso (para obtener más información, vea Estrategia de seguridad de [WPF](security-wpf.md) y [seguridad de WPF - Seguridad](wpf-security-strategy-platform-security.md)de plataforma ).  
  
<a name="Browser_Host_Detection"></a>
### <a name="browser-host-detection"></a>Detección de host del explorador  
 El uso de CAS para comprobar los permisos es una técnica adecuada cuando necesita comprobar por permiso. Sin embargo, esta técnica depende de la detección de excepciones como parte del procesamiento normal, que, en general, no se recomienda y puede tener problemas de rendimiento. En su lugar, si la aplicación de explorador XAML (XBAP) <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> solo se ejecuta dentro del entorno limitado de la zona de Internet, puede usar la propiedad, que devuelve true para las aplicaciones de explorador XAML (XBAP).  
  
> [!NOTE]
> <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A>sólo distingue si una aplicación se está ejecutando en un explorador, no con qué conjunto de permisos se ejecuta una aplicación.  
  
<a name="Managing_Permissions"></a>
## <a name="managing-permissions"></a>Administrar permisos  
 De forma predeterminada, los XBAP se ejecutan con confianza parcial (conjunto de permisos de zona de Internet predeterminado). Sin embargo, según los requisitos de la aplicación, es posible cambiar el conjunto de permisos predeterminado. Por ejemplo, si se inicia un XBAP desde una intranet local, puede aprovechar un conjunto de permisos aumentado, que se muestra en la tabla siguiente.  
  
 Tabla 3: Permisos de LocalIntranet e Internet  
  
|Permiso|Atributo|LocalIntranet|Internet|  
|----------------|---------------|-------------------|--------------|  
|DNS|Servidores DNS de acceso|Sí|Sin |  
|Variables de entorno|Lectura|Sí|Sin |  
|Cuadros de diálogo de archivo|Abrir|Sí|Sí|  
|Cuadros de diálogo de archivo|Sin restricciones|Sí|Sin |  
|Almacenamiento aislado|Aislamiento de ensamblados por el usuario|Sí|Sin |  
|Almacenamiento aislado|Aislamiento desconocido|Sí|Sí|  
|Almacenamiento aislado|Cuota de usuario ilimitada|Sí|Sin |  
|Multimedia|Imágenes, vídeo y audio seguros|Sí|Sí|  
|Impresión|Impresión predeterminada|Sí|Sin |  
|Impresión|Impresión segura|Sí|Sí|  
|Reflexión|Emitir|Sí|Sin |  
|Seguridad|Ejecución de código administrado|Sí|Sí|  
|Seguridad|Permisos de aserción concedidos|Sí|Sin |  
|Interfaz de usuario|Sin restricciones|Sí|Sin |  
|Interfaz de usuario|Ventanas seguras de nivel superior|Sí|Sí|  
|Interfaz de usuario|Portapapeles propio|Sí|Sí|  
|Explorador web|Navegación de marcos segura a HTML|Sí|Sí|  
  
> [!NOTE]
> Cortar y pegar solo se permite con confianza parcial cuando el usuario inicia la acción.  
  
 Si necesita aumentar los permisos, debe cambiar la configuración del proyecto y el manifiesto de aplicación ClickOnce. Para obtener más información, vea [Información general sobre las aplicaciones de explorador XAML de WPF](./app-development/wpf-xaml-browser-applications-overview.md). Los siguientes documentos también pueden ser útiles.  
  
- [Mage.exe (Herramienta de generación y edición de manifiestos)](../tools/mage-exe-manifest-generation-and-editing-tool.md).  
  
- [MageUI.exe (Herramienta de generación y edición de manifiestos, cliente gráfico)](../tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).  
  
- [Protección](/visualstudio/deployment/securing-clickonce-applications)de aplicaciones ClickOnce .  
  
 Si su XBAP requiere plena confianza, puede utilizar las mismas herramientas para aumentar los permisos solicitados. Aunque un XBAP solo recibirá plena confianza si está instalado e iniciado desde el equipo local, la intranet o desde una dirección URL que aparece en los sitios de confianza o permitidos del explorador. Si la aplicación se instala desde la intranet o un sitio de confianza, el usuario recibirá el mensaje estándar de ClickOnce, que le notificará los permisos elevados. El usuario puede elegir continuar con la instalación o cancelarla.  
  
 Como alternativa, puede usar el modelo de implementación de confianza de ClickOnce para realizar una implementación de plena confianza desde cualquier zona de seguridad. Para obtener más información, consulte Información general sobre [la implementación](/visualstudio/deployment/trusted-application-deployment-overview) de aplicaciones de confianza y [Seguridad](security-wpf.md).  
  
## <a name="see-also"></a>Consulte también

- [Seguridad](security-wpf.md)
- [Estrategia de seguridad de WPF: Seguridad de plataforma](wpf-security-strategy-platform-security.md)
- [Estrategia de seguridad de WPF: Ingeniería de seguridad](wpf-security-strategy-security-engineering.md)

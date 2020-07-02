---
title: Desarrollo de aplicaciones
description: Obtenga información sobre cómo crear una variedad de aplicaciones con el marco de Windows Presentation Foundation (WPF).
ms.date: 01/26/2018
helpviewer_keywords:
- WPF [WPF], about application development
- application development [WPF], about
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
ms.openlocfilehash: ac4227785f2fc398217b3aa8984176844264bbaa
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613740"
---
# <a name="application-development"></a>Desarrollo de aplicaciones
<a name="introduction"></a>Windows Presentation Foundation (WPF) es un marco de presentación que se puede usar para desarrollar los siguientes tipos de aplicaciones:  
  
- Aplicaciones independientes (aplicaciones Windows de estilo tradicional compiladas como ensamblados ejecutables que se instalan y se ejecutan desde el equipo cliente).  
  
- Aplicaciones de explorador XAML (XBAP) (aplicaciones compuestas de páginas de navegación que se compilan como ensamblados ejecutables y hospedados por exploradores Web, como Microsoft Internet Explorer o Mozilla Firefox).  
  
- Bibliotecas de control personalizadas (ensamblados no ejecutables que contienen controles reutilizables).  
  
- Bibliotecas de clases (ensamblados no ejecutables que contienen clases reutilizables).  
  
> [!NOTE]
> Se recomienda encarecidamente no usar los tipos WPF en un servicio de Windows. Si intenta usar estas características en un servicio de Windows, pueden no funcionar como se esperaba.  
  
 Para compilar este conjunto de aplicaciones, WPF implementa un host de servicios. En este tema se proporciona información general sobre estos servicios y se indica dónde buscar más información.  

<a name="Application_Management"></a>
## <a name="application-management"></a>Administración de aplicaciones  
 Las aplicaciones de WPF ejecutables suelen requerir un conjunto básico de funcionalidades que incluye lo siguiente:  
  
- Crear y administrar la infraestructura de aplicaciones común (lo que incluye crear un método de punto de entrada y un bucle de mensajes de Windows para recibir los mensajes del sistema y de entrada).  
  
- Realizar el seguimiento de la duración de una aplicación e interactuar con ella.  
  
- Recuperar y procesar los parámetros de la línea de comandos.  
  
- Compartir propiedades del ámbito de la aplicación y recursos de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
- Detectar y procesar las excepciones no controladas.  
  
- Devolver códigos de salida.  
  
- Administrar ventanas en las aplicaciones independientes.  
  
- Navegación de seguimiento en aplicaciones de explorador XAML (XBAP) y aplicaciones independientes con ventanas de navegación y marcos.  
  
 Estas funciones se implementan mediante la clase <xref:System.Windows.Application>, que se agrega a las aplicaciones por medio de una *definición de aplicación*.  
  
 Para obtener más información, vea [Información general sobre la administración de aplicaciones](application-management-overview.md).  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>
## <a name="wpf-application-resource-content-and-data-files"></a>Archivos de recursos, contenido y datos de aplicaciones de WPF  
 WPF amplía la compatibilidad básica en el marco de Microsoft .NET para los recursos incrustados con compatibilidad con tres tipos de archivos de datos no ejecutables: recursos, contenido y datos. Para obtener más información, vea [Archivos de recursos, contenido y datos de aplicaciones de WPF](wpf-application-resource-content-and-data-files.md).  
  
 Un componente clave de la compatibilidad con los archivos de datos no ejecutables de WPF es la capacidad de identificarlos y cargarlos mediante un URI único. Para obtener más información, vea [pack uri en WPF](pack-uris-in-wpf.md).  
  
<a name="Windows_and_Dialog_Boxes"></a>
## <a name="windows-and-dialog-boxes"></a>Ventanas y cuadros de diálogo  
 Los usuarios interactúan con las aplicaciones independientes de WPF a través de Windows. El propósito de una ventana es hospedar contenido de la aplicación y exponer la función de la aplicación que suele permitir a los usuarios interactuar con el contenido. En WPF, las ventanas están encapsuladas por la <xref:System.Windows.Window> clase, que admite:  
  
- Crear y mostrar las ventanas.  
  
- Establecer relaciones entre ventanas propietarias y pertenecientes.  
  
- Configurar el aspecto de la ventana (por ejemplo, tamaño, ubicación, iconos, texto de la barra de título, borde).  
  
- Realizar el seguimiento de la duración de una ventana e interactuar con ella.  
  
 Para obtener más información, vea [Información general sobre ventanas de WPF](wpf-windows-overview.md).  
  
 <xref:System.Windows.Window> admite la capacidad de crear un tipo especial de ventana denominado cuadro de diálogo. Se pueden crear los tipos modales y no modales de cuadros de diálogo.  
  
 Para mayor comodidad y las ventajas de la reusabilidad y una experiencia de usuario coherente en todas las aplicaciones, WPF expone tres de los cuadros de diálogo comunes de Windows: <xref:Microsoft.Win32.OpenFileDialog> , <xref:Microsoft.Win32.SaveFileDialog> y <xref:System.Windows.Controls.PrintDialog> .  
  
 Un cuadro de mensaje es un tipo especial de cuadro de diálogo para mostrar información de texto importante a los usuarios y plantear preguntas sencillas de Sí/No/Aceptar/Cancelar. Use la clase <xref:System.Windows.MessageBox> para crear y mostrar cuadros de mensajes.  
  
 Para obtener más información, vea [Información general sobre cuadros de diálogo](dialog-boxes-overview.md).  
  
<a name="Navigation"></a>
## <a name="navigation"></a>Navegación  
 WPF admite la navegación de estilo Web mediante páginas ( <xref:System.Windows.Controls.Page> ) e hipervínculos ( <xref:System.Windows.Documents.Hyperlink> ). La navegación se puede implementar de diversas maneras que incluyen las siguientes:  
  
- Páginas independientes que se hospedan en un explorador web.  
  
- Páginas compiladas en una aplicación XBAP hospedada en un explorador Web.  
  
- Páginas compiladas en una aplicación independiente y hospedadas por una ventana de navegación (<xref:System.Windows.Navigation.NavigationWindow>).  
  
- Páginas hospedadas por un marco ( <xref:System.Windows.Controls.Frame> ), que se pueden hospedar en una página independiente, o una página compilada en una aplicación XBAP o en una aplicación independiente.  
  
 Para facilitar la navegación, WPF implementa lo siguiente:  
  
- <xref:System.Windows.Navigation.NavigationService>, el motor de navegación compartido para procesar solicitudes de navegación utilizadas por <xref:System.Windows.Controls.Frame> , <xref:System.Windows.Navigation.NavigationWindow> y XBAP para admitir la navegación dentro de la aplicación.  
  
- Métodos de navegación para iniciar la navegación.  
  
- Eventos de navegación para realizar el seguimiento de la duración de la navegación e interactuar con ella.  
  
- Uso del diario, que se puede inspeccionar y manipular, para memorizar la navegación hacia delante y hacia atrás.  
  
 Para obtener más información, vea [Información general sobre navegación](navigation-overview.md).  
  
 WPF también admite un tipo especial de navegación que se conoce como navegación estructurada. La navegación estructurada se puede usar para llamar a una o más páginas que devuelven datos de una manera estructurada y previsible, y que es coherente con las funciones de llamada. Esta funcionalidad depende de la clase <xref:System.Windows.Navigation.PageFunction%601>, que se describe más detalladamente en [Información general sobre la navegación estructurada](structured-navigation-overview.md). <xref:System.Windows.Navigation.PageFunction%601> también sirve para simplificar la creación de topologías de navegación complejas, que se describen en [Información general sobre topologías de navegación](navigation-topologies-overview.md).  
  
<a name="Hosting"></a>
## <a name="hosting"></a>Hosting  
 Las XBAP se pueden hospedar en Microsoft Internet Explorer o Firefox. Cada modelo de hospedaje tiene su propio conjunto de consideraciones y restricciones, que se abordan en el tema [Hospedar aplicaciones de WPF](hosting-wpf-applications.md).  
  
<a name="Build_and_Deploy"></a>
## <a name="build-and-deploy"></a>Compilación e implementación  
 Aunque las aplicaciones de WPF simples se pueden crear desde un símbolo del sistema mediante compiladores de línea de comandos, WPF se integra con Visual Studio para proporcionar compatibilidad adicional que simplificó el proceso de desarrollo y compilación. Para obtener más información, vea [Compilar una aplicación de WPF (WPF)](building-a-wpf-application-wpf.md).  
  
 Según el tipo de aplicación que se compile, puede elegir entre una o más opciones de implementación. Para obtener más información, vea [Implementar una aplicación de WPF](deploying-a-wpf-application-wpf.md).  
  
<a name="related_topics"></a>
## <a name="related-topics"></a>Temas relacionados  
  
|Title|Descripción|  
|-----------|-----------------|  
|[Información general sobre la administración de aplicaciones](application-management-overview.md)|Proporciona información general sobre la clase <xref:System.Windows.Application> incluida la administración de la duración de la aplicación, las ventanas, los recursos de la aplicación y la navegación.|  
|[Windows en WPF](windows-in-wpf-applications.md)|Proporciona información detallada sobre la administración de ventanas en la aplicación incluida la forma de usar la clase <xref:System.Windows.Window> y los cuadros de diálogo.|  
|[Información general sobre navegación](navigation-overview.md)|Proporciona información general sobre la administración de la navegación entre las páginas de la aplicación.|  
|[Hospedar aplicaciones de WPF](hosting-wpf-applications.md)|Proporciona información general sobre las aplicaciones de explorador XAML (XBAP).|  
|[Compilación e implementación](building-and-deploying-wpf-applications.md)|Describe cómo compilar e implementar la aplicación de WPF.|  
|[Introducción a WPF en Visual Studio](../getting-started/introduction-to-wpf-in-vs.md)|Describe las características principales de WPF.|  
|[Tutorial: Mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)|Un tutorial que muestra cómo crear una aplicación de WPF mediante la navegación por páginas, diseño, controles, imágenes, estilos y enlaces.|

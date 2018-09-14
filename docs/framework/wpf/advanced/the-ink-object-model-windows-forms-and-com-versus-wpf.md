---
title: 'Modelo de objetos de entrada manuscrita: COM y formularios Windows Forms frente a WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling ink [WPF]
- InkCanvas control [WPF]
- ink object model [WPF]
- tablet pen [WPF], events [WPF]
- ink [WPF], enabling
- events [WPF], tablet pen
ms.assetid: 577835be-b145-4226-8570-1d309e9b3901
ms.openlocfilehash: c351f3d6bf6dbaf94d865fd56e140c44edc20394
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "44757466"
---
# <a name="the-ink-object-model-windows-forms-and-com-versus-wpf"></a>Modelo de objetos de entrada manuscrita: COM y formularios Windows Forms frente a WPF

Hay esencialmente tres plataformas que admiten la entrada de lápiz digital: la plataforma de Tablet PC Windows Forms, la plataforma de Tablet PC COM y la plataforma Windows Presentation Foundation (WPF).  Lo formularios de Windows y COM plataformas recurso compartido de un modelo de objetos similares, pero el objeto de modelo para el [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plataforma es sustancialmente diferente.  Este tema describen las diferencias de alto nivel para que los desarrolladores que han trabajado con un modelo de objetos puedan comprender mejor el otro.  
  
## <a name="enabling-ink-in-an-application"></a>Habilitar la entrada manuscrita en una aplicación  
 Las tres plataformas envíe los objetos y controles que permiten que una aplicación recibir entradas de lápiz de tablet PC.  Las plataformas COM y formularios de Windows que se suministran con [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx), [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx), [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) y [ Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) clases.  [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) y [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx) son controles que se pueden agregar a una aplicación para recopilar entradas de lápiz.  El [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) y [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) pueden asociarse a una ventana existente a windows ink-enable y controles personalizados.  
  
 La plataforma WPF incluye el <xref:System.Windows.Controls.InkCanvas> control.  Puede agregar un <xref:System.Windows.Controls.InkCanvas> a la aplicación y comenzar la recopilación de entradas manuscritas inmediatamente. Con el <xref:System.Windows.Controls.InkCanvas>, el usuario puede copiar, seleccionar y cambiar el tamaño de entrada de lápiz.  Puede agregar otros controles para el <xref:System.Windows.Controls.InkCanvas>, y el usuario puede escribir a mano a través de estos controles, demasiado.  Puede crear un control personalizado habilitado para tinta mediante la adición de un <xref:System.Windows.Controls.InkPresenter> y recopilar sus puntos de lápiz óptico.  
  
 La tabla siguiente muestra dónde obtener más información acerca de cómo habilitar la entrada de lápiz en una aplicación:  
  
|Para hacer esto...|En la plataforma WPF...|En las plataformas de Windows Forms y COM...|  
|-----------------|--------------------------|------------------------------------------|  
|Agregar un control habilitado para tinta a una aplicación|Consulte [introducción con tinta](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md).|Consulte [automáticamente notificaciones forman ejemplo](/windows/desktop/tablet/auto-claims-form-sample)|  
|Habilitar la entrada manuscrita en un control personalizado|Consulte [Control de entrada de creación de una entrada de lápiz](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).|Consulte [ejemplo Portapapeles de entrada manuscrita](/windows/desktop/tablet/ink-clipboard-sample).|  
  
## <a name="ink-data"></a>Datos de entrada de lápiz  
 En los formularios de Windows y plataformas de COM, [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx), [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx), [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx), y [ Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) cada exponen un [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) objeto. El [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) objeto contiene los datos de uno o varios [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx?displayProperty=nameWithType) objetos y expone métodos y propiedades para administrar y manipular esos trazos comunes.  El [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) objeto administra la duración de los trazos que contiene; el [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) objeto crea y elimina los trazos que posee.  Cada [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx) tiene un identificador que es único dentro de su elemento primario [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) objeto.  
  
 En la plataforma WPF, la <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> clase posee y administra su duración. Un grupo de <xref:System.Windows.Ink.Stroke> objetos se pueden recopilar juntos en un <xref:System.Windows.Ink.StrokeCollection>, que proporciona métodos para tinta comunes las operaciones de administración de datos, como las pruebas, borrar, transformar y serializar la tinta de posicionamiento. Un <xref:System.Windows.Ink.Stroke> puede pertenecer a cero, uno o más <xref:System.Windows.Ink.StrokeCollection> de tiempo a los objetos de cualquiera.  En lugar de tener un [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) objeto, el <xref:System.Windows.Controls.InkCanvas> y <xref:System.Windows.Controls.InkPresenter> contienen un <xref:System.Windows.Ink.StrokeCollection?displayProperty=nameWithType>.  
  
 Las dos ilustraciones siguientes comparan los modelos de objetos de datos de entrada de lápiz.  En los formularios de Windows y plataformas de COM, el [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) objeto limita la duración de la [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx?displayProperty=nameWithType) objetos y los paquetes del lápiz óptico pertenecen a los trazos individuales.  Trazos de dos o más pueden hacer referencia a la misma [Microsoft.Ink.DrawingAttributes](https://msdn.microsoft.com/library/ms837931.aspx?displayProperty=nameWithType) de objeto, como se muestra en la siguiente ilustración.  
  
 ![Diagrama del modelo de objetos de entrada manuscrita para COM&#47;Winforms. ](../../../../docs/framework/wpf/advanced/media/ink-inkownsstrokes.png "Ink_InkOwnsStrokes")  
  
 En el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], cada <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> es un objeto de common language runtime que existe siempre que algo tenga una referencia a él.  Cada <xref:System.Windows.Ink.Stroke> referencias una <xref:System.Windows.Input.StylusPointCollection> y <xref:System.Windows.Ink.DrawingAttributes?displayProperty=nameWithType> objeto, que también son objetos common language runtime.  
  
 ![Diagrama del modelo de objetos de entrada manuscrita para WPF. ](../../../../docs/framework/wpf/advanced/media/ink-wpfinkobjectmodel.png "Ink_WPFInkObjectModel")  
  
 En la tabla siguiente compara cómo realizar algunas tareas comunes en el [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plataforma y las plataformas de Windows Forms y COM.  
  
|Tarea|Windows Presentation Foundation|COM y formularios de Windows|  
|----------|-------------------------------------|---------------------------|  
|Guardar la entrada de lápiz|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|[Microsoft.Ink.Ink.Save](https://technet.microsoft.com/library/security/microsoft.ink.ink.save(v=vs.90))|  
|Tinta de carga|Crear un <xref:System.Windows.Ink.StrokeCollection> con el <xref:System.Windows.Ink.StrokeCollection.%23ctor%2A> constructor.|[Microsoft.Ink.Ink.Load](https://msdn.microsoft.com/library/microsoft.ink.ink.load(v=vs.90).aspx)|  
|Prueba de posicionamiento|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|[Microsoft.Ink.Ink.HitTest](https://msdn.microsoft.com/library/aa515934.aspx)|  
|Copie la entrada de lápiz|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|[Microsoft.Ink.Ink.ClipboardCopy](https://msdn.microsoft.com/library/microsoft.ink.ink.clipboardcopy(v=vs.100).aspx)|  
|Pegue la entrada de lápiz|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|[Microsoft.Ink.Ink.ClipboardPaste](https://msdn.microsoft.com/library/microsoft.ink.ink.clipboardpaste(v=vs.100).aspx)|  
|Propiedades personalizadas de acceso en una colección de trazos|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> (las propiedades se almacenan internamente y acceder a través de <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>, <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A>, y <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>)|Use [Microsoft.Ink.Ink.ExtendedProperties](https://msdn.microsoft.com/library/microsoft.ink.ink.extendedproperties(v=vs.100).aspx)|  
  
### <a name="sharing-ink-between-platforms"></a>Uso compartido de tinta entre plataformas  
 Aunque las plataformas tienen diferentes modelos de objetos para los datos de entrada de lápiz, compartir los datos entre las plataformas es muy fácil. Los ejemplos siguientes guardar tinta de una aplicación de Windows Forms y cargan la entrada de lápiz en una aplicación de Windows Presentation Foundation.  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 Los ejemplos siguientes guardar entradas manuscritas desde una aplicación de Windows Presentation Foundation y cargan la entrada de lápiz en una aplicación de Windows Forms.  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]
## <a name="events-from-the-tablet-pen"></a>Eventos de lápiz de Tablet PC  
 El [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx), [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx), y [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) en los formularios de Windows y COM plataformas reciben eventos cuando el usuario entradas de datos con el lápiz.  El [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) o [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) se adjunta a una ventana o un control y puede suscribirse a los eventos generados por los datos de entrada de Tablet PC.  El subproceso en el que se producen estos eventos depende de si se producen los eventos con un lápiz, un mouse, o mediante programación.  Para obtener más información acerca de los subprocesos con respecto a estos eventos, vea [consideraciones generales de subprocesamiento](/windows/desktop/tablet/general-threading-considerations) y [subprocesos en la que se puede desencadenar un evento](/windows/desktop/tablet/threads-on-which-an-event-can-fire).  
  
 En la plataforma Windows Presentation Foundation, la <xref:System.Windows.UIElement> clase tiene eventos para la entrada de lápiz. Esto significa que cada control expone el conjunto completo de eventos de lápiz.  Los eventos de lápiz óptico tienen eventos de tunelización y propagación pares y siempre se producen en el subproceso de la aplicación.  Para obtener más información, consulte [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Se muestra en el diagrama siguiente se comparan los modelos de objetos para las clases que generan eventos de lápiz óptico. El modelo de objetos de Windows Presentation Foundation muestra solo los eventos de propagación, no la tunelización equivalentes de eventos.  
  
 ![Diagrama de los eventos Stylus en WPF frente a formularios Windows Forms. ](../../../../docs/framework/wpf/advanced/media/ink-stylusevents.png "Ink_StylusEvents")  
  
## <a name="pen-data"></a>Datos del lápiz  
 Las tres plataformas proporcionan maneras de interceptar y manipular los datos que proceden de un lápiz de tablet PC.  En las plataformas COM y formularios de Windows, esto se logra mediante la creación de un [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx), adjuntar una ventana o control a la misma y creando una clase que implementa el [ Microsoft.StylusInput.IStylusSyncPlugin](https://msdn.microsoft.com/library/microsoft.stylusinput.istylussyncplugin(v=vs.100).aspx) o [Microsoft.StylusInput.IStylusAsyncPlugin](https://msdn.microsoft.com/library/microsoft.stylusinput.istylusasyncplugin(v=vs.100).aspx) interfaz. El complemento personalizado, a continuación, se agrega a la colección de complementos de la [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx). Para obtener más información sobre este modelo de objetos, consulte [arquitectura de la StylusInput APIs](/windows/desktop/tablet/architecture-of-the-stylusinput-apis).  
  
 En el [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plataforma, el <xref:System.Windows.UIElement> clase expone una colección de complementos, similares en el diseño a la [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx).  Para interceptar los datos del lápiz, cree una clase que hereda de <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> y agregar el objeto a la <xref:System.Windows.UIElement.StylusPlugIns%2A> colección de la <xref:System.Windows.UIElement>. Para obtener más información acerca de esta interacción, vea [interceptar entradas del lápiz óptico](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md).  
  
 En todas las plataformas, un grupo de subprocesos recibe los datos de entrada de lápiz a través de eventos de lápiz y lo envía al subproceso de la aplicación.  Para obtener más información acerca de los subprocesos en las plataformas de Windows y COM, vea [Threading Considerations for the StylusInput APIs](/windows/desktop/tablet/threading-considerations-for-the-stylusinput-apis).  Para obtener más información acerca de los subprocesos en el Software de presentación de Windows, consulte [el modelo de subprocesos de tinta](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md).  
  
 La ilustración siguiente compara los modelos de objetos para las clases que reciben datos del lápiz en el grupo de subprocesos del lápiz.  
  
 ![Diagrama del modelo StylusPlugin en WPF frente a formularios Windows Forms. ](../../../../docs/framework/wpf/advanced/media/ink-stylusplugins.png "Ink_StylusPlugins")

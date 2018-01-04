---
title: 'Modelo de objetos de entrada manuscrita: COM y formularios Windows Forms frente a WPF'
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-wpf
ms.topic: article
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
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 38c7692d433fb91584718984ef2ad81e563517db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="the-ink-object-model-windows-forms-and-com-versus-wpf"></a>Modelo de objetos de entrada manuscrita: COM y formularios Windows Forms frente a WPF

Hay esencialmente tres plataformas que admiten la entrada de lápiz digital: la plataforma de Tablet PC Windows Forms, la plataforma de Tablet PC COM y la [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] plataforma.  La cuota de plataformas de Windows Forms y COM un modelo de objetos similares, pero el objeto de modelo para el [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plataforma es sustancialmente diferente.  Este tema describe las diferencias de alto nivel para que los desarrolladores que han trabajado con un modelo de objetos pueden comprender mejor el otro.  
  
## <a name="enabling-ink-in-an-application"></a>Habilitación de tinta en una aplicación  
 Las tres plataformas distribuyen objetos y controles que permiten que una aplicación recibir la entrada de un lápiz de tablet PC.  Las plataformas COM y formularios Windows Forms que se suministran con [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx), [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx), [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) y [ Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) clases.  [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) y [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx) son controles que se pueden agregar a una aplicación para recopilar entradas de lápiz.  El [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) y [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) se pueden adjuntar a una ventana existente a windows tinta-enable y controles personalizados.  
  
 La plataforma WPF incluye el <xref:System.Windows.Controls.InkCanvas> control.  Puede agregar una <xref:System.Windows.Controls.InkCanvas> a la aplicación y comenzar a recopilar inmediatamente tinta. Con el <xref:System.Windows.Controls.InkCanvas>, el usuario puede copiar, seleccionar y cambiar el tamaño de tinta.  Puede agregar otros controles a la <xref:System.Windows.Controls.InkCanvas>, y el usuario puede escribir a mano sobre esos controles demasiado.  Puede crear un control personalizado habilitado para entradas manuscritas agregando un <xref:System.Windows.Controls.InkPresenter> a él y recopilar sus puntos de lápiz.  
  
 La tabla siguiente muestra dónde obtener más información sobre la habilitación de tinta en una aplicación:  
  
|Para hacer esto...|En la plataforma WPF...|En las plataformas de Windows Forms y COM...|  
|-----------------|--------------------------|------------------------------------------|  
|Agregar un control habilitado para tinta a una aplicación|Vea [Getting Started with tinta](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md).|Vea [automáticamente notificaciones forman el ejemplo](http://msdn.microsoft.com/bec4333a-62ca-4254-a39b-04bc2c556992)|  
|Habilitar la entrada manuscrita en un control personalizado|Vea [crear un lápiz de entrada de Control](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).|Vea [tinta Portapapeles ejemplo](http://msdn.microsoft.com/a0c42f1c-543d-44f8-83d9-fe810de410ff).|  
  
## <a name="ink-data"></a>Datos de entrada manuscrita  
 En las plataformas de COM y formularios Windows Forms [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx), [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx), [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx), y [ Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) cada exponen un [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) objeto. El [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) objeto contiene los datos de uno o varios [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx?displayProperty=nameWithType) objetos y expone métodos y propiedades para administrar y manipular esos trazos comunes.  El [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) objeto administra la duración de los trazos que contiene; la [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) objeto crea y elimina los trazos que posee.  Cada [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx) tiene un identificador que es único dentro de su elemento primario [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) objeto.  
  
 En la plataforma WPF, la <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> clase posee y administra su propia duración. Un grupo de <xref:System.Windows.Ink.Stroke> objetos se pueden recopilar juntos en un <xref:System.Windows.Ink.StrokeCollection>, que proporciona métodos para tinta común las operaciones de administración de datos como llamadas pruebas, borrar, transformar y serializar la tinta. A <xref:System.Windows.Ink.Stroke> puede pertenecer a cero, uno o más <xref:System.Windows.Ink.StrokeCollection> objetos en cualquier dar a tiempo.  En lugar de tener un [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) objeto, el <xref:System.Windows.Controls.InkCanvas> y <xref:System.Windows.Controls.InkPresenter> contienen un <xref:System.Windows.Ink.StrokeCollection?displayProperty=nameWithType>.  
  
 El siguiente par de ilustraciones compara los modelos de objetos de datos de tinta.  En los formularios Windows Forms y las plataformas de COM, la [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) objeto limita la duración de la [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx?displayProperty=nameWithType) objetos y los paquetes del lápiz óptico pertenecen a los trazos individuales.  Dos o más trazos pueden hacer referencia a la misma [Microsoft.Ink.DrawingAttributes](https://msdn.microsoft.com/library/ms837931.aspx?displayProperty=nameWithType) de objeto, como se muestra en la siguiente ilustración.  
  
 ![Diagrama del modelo de objetos de entrada manuscrita para COM &#47; Formularios Windows Forms. ] (../../../../docs/framework/wpf/advanced/media/ink-inkownsstrokes.png "Ink_InkOwnsStrokes")  
  
 En el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], cada <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> es un objeto de common language runtime que existe mientras algo tiene una referencia a él.  Cada <xref:System.Windows.Ink.Stroke> referencias un <xref:System.Windows.Input.StylusPointCollection> y <xref:System.Windows.Ink.DrawingAttributes?displayProperty=nameWithType> objeto, que también son objetos de common language runtime.  
  
 ![Diagrama del modelo de objetos de entrada manuscrita para WPF. ] (../../../../docs/framework/wpf/advanced/media/ink-wpfinkobjectmodel.png "Ink_WPFInkObjectModel")  
  
 La tabla siguiente compara cómo llevar a cabo algunas tareas comunes en la [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plataforma y las plataformas COM y formularios Windows Forms.  
  
|Tarea|Windows Presentation Foundation|COM y formularios Windows Forms|  
|----------|-------------------------------------|---------------------------|  
|Guardar la tinta|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|[Microsoft.Ink.Ink.Save](https://technet.microsoft.com/library/security/microsoft.ink.ink.save(v=vs.90))|  
|Tinta de carga|Crear un <xref:System.Windows.Ink.StrokeCollection> con el <xref:System.Windows.Ink.StrokeCollection.%23ctor%2A> constructor.|[Microsoft.Ink.Ink.Load](https://msdn.microsoft.com/library/microsoft.ink.ink.load(v=vs.90).aspx)|  
|Prueba de posicionamiento|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|[Microsoft.Ink.Ink.HitTest](https://msdn.microsoft.com/library/aa515934.aspx)|  
|Copiar entrada manuscrita|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|[Microsoft.Ink.Ink.ClipboardCopy](https://msdn.microsoft.com/library/microsoft.ink.ink.clipboardcopy(v=vs.100).aspx)|  
|Pegue la tinta|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|[Microsoft.Ink.Ink.ClipboardPaste](https://msdn.microsoft.com/library/microsoft.ink.ink.clipboardpaste(v=vs.100).aspx)|  
|Propiedades personalizadas de acceso en una colección de trazos|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>(las propiedades se almacenan internamente y acceder a través del <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>, <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A>, y <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>)|Use [Microsoft.Ink.Ink.ExtendedProperties](https://msdn.microsoft.com/library/microsoft.ink.ink.extendedproperties(v=vs.100).aspx)|  
  
### <a name="sharing-ink-between-platforms"></a>Uso compartido de tinta entre plataformas  
 Aunque las plataformas tienen modelos de objetos diferentes para los datos de tinta, es muy fácil compartir los datos entre las plataformas. Los ejemplos siguientes guardar tinta de una aplicación de formularios Windows Forms y cargan la tinta en una aplicación de Windows Presentation Foundation.  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 Los ejemplos siguientes guardar tinta de una aplicación de Windows Presentation Foundation y cargan la tinta en una aplicación de formularios Windows Forms.  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]
## <a name="events-from-the-tablet-pen"></a>Eventos de lápiz de Tablet PC  
 El [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx), [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx), y [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) en los formularios de Windows y COM plataformas reciban eventos cuando el usuario entradas de datos con el lápiz.  El [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) o [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) se adjunta a una ventana o un control y pueden suscribirse a los eventos generados por los datos de entrada de Tablet PC.  El subproceso en el que se producen estos eventos depende de si se producen los eventos con un lápiz, un mouse, o mediante programación.  Para obtener más información acerca del subprocesamiento en relación con estos eventos, vea [consideraciones generales de subprocesamiento](http://msdn.microsoft.com/cf35724f-5f80-4b3e-992a-a9d5ea99aae9) y [subprocesos en lo que se puede desencadenar un evento](http://msdn.microsoft.com/d1a5ab9b-d474-4ed7-9aa8-b5bdb771934f).  
  
 En la plataforma de Windows Presentation Foundation, la <xref:System.Windows.UIElement> clase tiene eventos para la entrada de lápiz. Esto significa que cada control expone el conjunto completo de eventos de lápiz.  Los eventos de lápiz tienen eventos de túnel y propagación pares y siempre se producen en el subproceso de la aplicación.  Para obtener más información, consulte [enrutan Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Se muestra en el diagrama siguiente se comparan los modelos de objetos para las clases que provocan eventos de lápiz. El modelo de objetos de Windows Presentation Foundation muestra solo los eventos de propagación, no el túnel equivalentes de eventos.  
  
 ![Diagrama de los eventos Stylus en WPF frente a formularios Windows Forms. ] (../../../../docs/framework/wpf/advanced/media/ink-stylusevents.png "Ink_StylusEvents")  
  
## <a name="pen-data"></a>Datos del lápiz  
 Las tres plataformas proporcionan maneras de interceptar y manipular los datos procedentes un lápiz de tablet PC.  En las plataformas COM y formularios Windows Forms, esto se logra mediante la creación de un [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx), adjuntar una ventana o un control a la misma y la creación de una clase que implementa el [ Microsoft.StylusInput.IStylusSyncPlugin](https://msdn.microsoft.com/library/microsoft.stylusinput.istylussyncplugin(v=vs.100).aspx) o [Microsoft.StylusInput.IStylusAsyncPlugin](https://msdn.microsoft.com/library/microsoft.stylusinput.istylusasyncplugin(v=vs.100).aspx) interfaz. El complemento personalizado, a continuación, se agrega a la colección de complementos de la [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx). Para obtener más información acerca de este modelo de objetos, consulte [arquitectura de StylusInput APIs](http://msdn.microsoft.com/88bab0ab-df9f-4813-9a9f-9a137813f0b4).  
  
 En el [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plataforma, el <xref:System.Windows.UIElement> clase expone una colección de complementos, similares en el diseño para la [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx).  Para interceptar los datos del lápiz, cree una clase que hereda de <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> y agregar el objeto a la <xref:System.Windows.UIElement.StylusPlugIns%2A> colección de la <xref:System.Windows.UIElement>. Para obtener más información sobre esta interacción, vea [interceptando la entrada del lápiz óptico](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md).  
  
 En todas las plataformas, un grupo de subprocesos recibe los datos de entrada de lápiz a través de eventos de lápiz y lo envía al subproceso de la aplicación.  Para obtener más información acerca de los subprocesos en las plataformas de Windows y COM, consulte [Threading Considerations for the StylusInput APIs](http://msdn.microsoft.com/5d98768a-c60b-4bb0-8640-9bf38254d41f).  Para obtener más información acerca del subprocesamiento en el Software de presentación de Windows, vea [el modelo de subprocesamiento de tinta](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md).  
  
 La ilustración siguiente compara los modelos de objetos para las clases que reciben datos del lápiz en el grupo de subprocesos de lápiz.  
  
 ![Diagrama del modelo StylusPlugin en WPF frente a formularios Windows Forms. ] (../../../../docs/framework/wpf/advanced/media/ink-stylusplugins.png "Ink_StylusPlugins")

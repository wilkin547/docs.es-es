---
title: "Modelo de objetos de entrada manuscrita: COM y formularios Windows Forms frente a WPF | Microsoft Docs"
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
  - "habilitar la entrada manuscrita"
  - "eventos, lápiz de Tablet PC"
  - "modelo de objeto de entrada manuscrita"
  - "entrada manuscrita, habilitar"
  - "InkCanvas (control)"
  - "lápiz de Tablet PC, eventos"
ms.assetid: 577835be-b145-4226-8570-1d309e9b3901
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Modelo de objetos de entrada manuscrita: COM y formularios Windows Forms frente a WPF
Esencialmente, hay tres plataformas que admiten entradas de lápiz digitales: COM de Tablet PC, formularios Windows Forms de Tablet PC y [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  Las plataformas COM y formularios Windows Forms comparten un modelo de objetos similar, pero el modelo de objetos de la plataforma [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es sustancialmente diferente.  En este tema se abordan las diferencias de alto nivel, para que los programadores que han trabajado con un modelo de objetos puedan entender mejor el otro.  
  
## Habilitar entradas de lápiz en una aplicación  
 Las tres plataformas se distribuyen con objetos y controles que permiten que las aplicaciones reciban la entrada de un lápiz de Tablet PC.  Las plataformas Windows Forms y COM se distribuyen con las clases <xref:Microsoft.Ink.InkPicture>, <xref:Microsoft.Ink.InkEdit>, <xref:Microsoft.Ink.InkOverlay> y <xref:Microsoft.Ink.InkCollector>.  <xref:Microsoft.Ink.InkPicture> y <xref:Microsoft.Ink.InkEdit> son controles que se pueden agregar a una aplicación para recopilar entradas de lápiz.  <xref:Microsoft.Ink.InkOverlay> e <xref:Microsoft.Ink.InkCollector> se pueden asociar a una ventana existente a fin de habilitar las ventanas y los controles personalizados para entradas de lápiz.  
  
 La plataforma WPF incluye el control <xref:System.Windows.Controls.InkCanvas>.  Puede agregar una clase <xref:System.Windows.Controls.InkCanvas> a la aplicación y comenzar inmediatamente a recopilar entradas de lápiz.  Con <xref:System.Windows.Controls.InkCanvas>, el usuario puede copiar y seleccionar entradas de lápiz, así como ajustar su tamaño.  Puede agregar a <xref:System.Windows.Controls.InkCanvas> otros controles en los que el usuario también puede escribir a mano.  Puede crear un control personalizado habilitado para entradas de lápiz si agrega una clase <xref:System.Windows.Controls.InkPresenter> y recopila sus puntos de lápiz óptico.  
  
 En la tabla siguiente se muestra dónde obtener más información sobre cómo habilitar entradas de lápiz en una aplicación:  
  
|Para…|En la plataforma WPF…|En las plataformas COM y formularios Windows Forms…|  
|-----------|---------------------------|---------------------------------------------------------|  
|Agregar a una aplicación un control habilitado para entradas de lápiz|Vea [Introducción a las entradas manuscritas](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md).|Vea [Auto Claims Form Sample](http://msdn.microsoft.com/es-es/bec4333a-62ca-4254-a39b-04bc2c556992).|  
|Habilitar entradas de lápiz en un control personalizado|Vea [Creación de un control de entrada manuscrita](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).|Vea [Ink Clipboard Sample](http://msdn.microsoft.com/es-es/a0c42f1c-543d-44f8-83d9-fe810de410ff).|  
  
## Datos de las entradas de lápiz  
 En las plataformas COM y formularios Windows Forms, <xref:Microsoft.Ink.InkCollector>, <xref:Microsoft.Ink.InkOverlay>, <xref:Microsoft.Ink.InkEdit> e <xref:Microsoft.Ink.InkPicture> exponen un objeto <xref:Microsoft.Ink.Ink?displayProperty=fullName>.  El objeto <xref:Microsoft.Ink.Ink> contiene los datos correspondientes a uno o más objetos <xref:Microsoft.Ink.Stroke?displayProperty=fullName> y expone los métodos y propiedades comunes para administrar y manipular esos trazos.  El objeto <xref:Microsoft.Ink.Ink> administra la duración de los trazos que contiene; el objeto <xref:Microsoft.Ink.Ink> crea y elimina los trazos que posee.  Cada objeto <xref:Microsoft.Ink.Stroke> tiene un identificador que es único dentro de su objeto <xref:Microsoft.Ink.Ink> primario.  
  
 En la plataforma WPF, la clase <xref:System.Windows.Ink.Stroke?displayProperty=fullName> posee y administra su propia duración.  Puede recopilarse un grupo de objetos <xref:System.Windows.Ink.Stroke> juntos en un objeto <xref:System.Windows.Ink.StrokeCollection>, que proporciona los métodos para las operaciones comunes de administración de datos de las entradas de lápiz, tales como pruebas de posicionamiento, borrado, transformación y serialización de entradas de lápiz.  Un objeto <xref:System.Windows.Ink.Stroke> puede pertenecer a cero, uno o más objetos <xref:System.Windows.Ink.StrokeCollection> en cualquier momento dado.  En lugar de tener un objeto <xref:Microsoft.Ink.Ink?displayProperty=fullName>, <xref:System.Windows.Controls.InkCanvas> e <xref:System.Windows.Controls.InkPresenter> contienen un objeto <xref:System.Windows.Ink.StrokeCollection?displayProperty=fullName>.  
  
 En las dos ilustraciones siguientes se comparan los modelos de objetos de datos de entrada de lápiz.  En las plataformas COM y formularios Windows Forms, el objeto <xref:Microsoft.Ink.Ink?displayProperty=fullName> limita la duración de los objetos <xref:Microsoft.Ink.Stroke?displayProperty=fullName> y los paquetes del lápiz óptico pertenecen a los trazos individuales.  Dos o más trazos pueden hacer referencia al mismo objeto <xref:Microsoft.Ink.DrawingAttributes?displayProperty=fullName>, como se muestra en la ilustración siguiente.  
  
 ![Diagrama del modelo de objeto de entrada manuscrita para COM&#47;formularios Windows Forms.](../../../../docs/framework/wpf/advanced/media/ink-inkownsstrokes.png "Ink\_InkOwnsStrokes")  
  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], cada objeto <xref:System.Windows.Ink.Stroke?displayProperty=fullName> es un objeto de Common Language Runtime que existe mientras algo haga referencia a él.  Cada <xref:System.Windows.Ink.Stroke> hace referencia a un objeto <xref:System.Windows.Input.StylusPointCollection> y a un objeto <xref:System.Windows.Ink.DrawingAttributes?displayProperty=fullName>, que también son objetos de Common Language Runtime.  
  
 ![Diagrama del modelo de objeto de entrada manuscrita para WPF.](../../../../docs/framework/wpf/advanced/media/ink-wpfinkobjectmodel.png "Ink\_WPFInkObjectModel")  
  
 En la tabla siguiente se compara cómo lograr algunas tareas comunes en la plataforma [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] y en las plataformas COM y formularios Windows Forms.  
  
|Tarea|Windows Presentation Foundation|COM y formularios Windows Forms|  
|-----------|-------------------------------------|-------------------------------------|  
|Guardar entradas de lápiz|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|<xref:Microsoft.Ink.Ink.Save%2A>|  
|Cargar entradas de lápiz|Un objeto <xref:System.Windows.Ink.StrokeCollection> se crea con el constructor <xref:System.Windows.Ink.StrokeCollection.%23ctor%28System.IO.Stream%29?displayProperty=fullName>.|[M:Microsoft.Ink.Ink.Load\(System.Byte\<xref:Microsoft.Ink.Ink.Load%2A>|  
|Prueba de posicionamiento|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|<xref:Microsoft.Ink.Ink.HitTest%2A>|  
|Copiar entradas de lápiz|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|<xref:Microsoft.Ink.Ink.ClipboardCopy%2A>|  
|Pegar entradas de lápiz|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|<xref:Microsoft.Ink.Ink.ClipboardPaste%2A>|  
|Tener acceso a las propiedades personalizadas en una colección de trazos|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> \(las propiedades se almacenan internamente y se obtiene acceso a ellas a través de <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>, <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A> y <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>\).|Use <xref:Microsoft.Ink.Ink.ExtendedProperties%2A>|  
  
### Compartir entradas de lápiz entre plataformas  
 Aunque las plataformas tienen modelos de objetos diferentes para los datos de entrada de lápiz, compartir los datos entre las plataformas es muy fácil.  En los ejemplos siguientes se guardan las entradas de lápiz de una aplicación de Windows Forms y se cargan en una aplicación de Windows Presentation Foundation.  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 En los ejemplos siguientes se guardan las entradas de lápiz de una aplicación de Windows Presentation Foundation y se cargan en una aplicación de Windows Forms.  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]  
  
## Eventos del lápiz de Tablet PC  
 Las clases <xref:Microsoft.Ink.InkOverlay>, <xref:Microsoft.Ink.InkCollector> e <xref:Microsoft.Ink.InkPicture> de las plataformas COM y formularios Windows Forms reciben los eventos cuando el usuario introduce datos con el lápiz.  <xref:Microsoft.Ink.InkOverlay> o <xref:Microsoft.Ink.InkCollector> se asocian a una ventana o un control y pueden suscribirse a los eventos provocados por los datos de entrada de Tablet PC.  El subproceso en el que se producen estos eventos depende de si los eventos se provocan con un lápiz, un mouse o mediante programación.  Para obtener más información sobre los subprocesos relacionados con estos eventos, vea [General Threading Considerations](http://msdn.microsoft.com/es-es/cf35724f-5f80-4b3e-992a-a9d5ea99aae9) y [Threads on Which an Event Can Fire](http://msdn.microsoft.com/es-es/d1a5ab9b-d474-4ed7-9aa8-b5bdb771934f).  
  
 En la plataforma Windows Presentation Foundation, la clase <xref:System.Windows.UIElement> tiene eventos para entradas de lápiz.  Esto significa que cada control expone todos los eventos de lápiz óptico.  Los eventos de lápiz óptico tienen pares de eventos de túnel y propagación y siempre se producen en el subproceso de la aplicación.  Para obtener más información, consulte [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 En el diagrama siguiente se comparan los modelos de objetos correspondientes a las clases que provocan eventos de lápiz óptico.  El modelo de objetos de Windows Presentation Foundation muestra únicamente los eventos de propagación, no sus homólogos de túnel.  
  
 ![Diagrama de los eventos Stylus en WPF frente a formularios Windows Forms.](../../../../docs/framework/wpf/advanced/media/ink-stylusevents.png "Ink\_StylusEvents")  
  
## Datos del lápiz  
 Las tres plataformas proporcionan la manera de interceptar y manipular los datos procedentes de un lápiz de Tablet PC.  En las plataformas COM y formularios Windows Forms, para lograr esto se crea un objeto <xref:Microsoft.StylusInput.RealTimeStylus>, que se asocia a una ventana o control, y se crea una clase que implementa la interfaz <xref:Microsoft.StylusInput.IStylusSyncPlugin> o <xref:Microsoft.StylusInput.IStylusAsyncPlugin>.  A continuación, se agrega el complemento personalizado a la colección de complementos de <xref:Microsoft.StylusInput.RealTimeStylus>.  Para obtener más información acerca de este modelo de objetos, vea [Architecture of the StylusInput APIs](http://msdn.microsoft.com/es-es/88bab0ab-df9f-4813-9a9f-9a137813f0b4).  
  
 En la plataforma [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], la clase <xref:System.Windows.UIElement> expone una colección de complementos, con un diseño similar a <xref:Microsoft.StylusInput.RealTimeStylus>.  Para interceptar los datos del lápiz, cree una clase que herede de <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> y agregue el objeto a la colección <xref:System.Windows.UIElement.StylusPlugIns%2A> de <xref:System.Windows.UIElement>.  Para obtener más información sobre esta interacción, vea [Interceptar entradas del lápiz óptico](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md).  
  
 En todas las plataformas, un grupo de subprocesos recibe los datos de entradas de lápiz a través de los eventos de lápiz óptico y los envía al subproceso de la aplicación.  Para obtener más información sobre subprocesos en las plataformas COM y formularios Windows Forms, vea [Threading Considerations for the StylusInput APIs](http://msdn.microsoft.com/es-es/5d98768a-c60b-4bb0-8640-9bf38254d41f).  Para obtener más información sobre los subprocesos en el software de Windows Presentation Foundation, vea [Modelo de subprocesamiento de entrada manuscrita](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md).  
  
 En la ilustración siguiente se comparan los modelos de objetos de las clases que reciben los datos del lápiz en el grupo de subprocesos de lápiz.  
  
 ![Diagrama del modelo StylusPlugin en WPF frente a formularios Windows Forms.](../../../../docs/framework/wpf/advanced/media/ink-stylusplugins.png "Ink\_StylusPlugins")
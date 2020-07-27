---
title: Información general sobre la función de arrastrar y colocar
description: Obtenga información sobre la compatibilidad con arrastrar y colocar en Windows Presentation Foundation aplicaciones, que permite a los usuarios arrastrar objetos a una región de la interfaz de usuario.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], implementing
- drag sources [WPF], drag-and-drop
- data transfer [WPF], drag-and-drop
- drag-and-drop [WPF], about
- drag-and-drop [WPF], events
- drop targets [WPF], drag-and-drop
ms.assetid: 1a5b27b0-0ac5-4cdf-86c0-86ac0271fa64
ms.openlocfilehash: 63384e79d8a198e4cc9507ca3266c484c0506e2c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168076"
---
# <a name="drag-and-drop-overview"></a>Información general sobre la función de arrastrar y colocar
Este tema proporciona información general sobre la compatibilidad con arrastrar y colocar en aplicaciones [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Arrastrar y colocar se refiere normalmente a un método de transferencia de datos que implica el uso de un mouse (o cualquier otro dispositivo señalador) para seleccionar uno o más objetos, arrastrar estos objetos sobre un destino deseado en la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] y soltarlos.  

<a name="Drag_and_Drop_Support"></a>
## <a name="drag-and-drop-support-in-wpf"></a>Compatibilidad con arrastrar y colocar en WPF  
 Las operaciones de arrastrar y colocar suelen incluir dos partes: un origen de arrastre en el que se origina el objeto arrastrado y un destino de colocación que recibe el objeto colocado.  El origen de arrastre y el destino de colocación pueden ser elementos de la interfaz de usuario de la misma aplicación o de otra aplicación.  
  
 El tipo y número de objetos que se pueden manipular con arrastrar y colocar es completamente arbitrario. Por ejemplo, los archivos, las carpetas y las selecciones de contenido son algunos de los objetos más comunes que se manipulan mediante operaciones de arrastrar y colocar.  
  
 Las acciones concretas realizadas durante una operación de arrastrar y colocar son específicas de la aplicación y a menudo están determinadas por el contexto.  Por ejemplo, si se arrastra una selección de archivos de una carpeta a otra en el mismo dispositivo de almacenamiento, se mueven los archivos de forma predeterminada, mientras que si se arrastran archivos de un recurso compartido de Convención de nomenclatura universal (UNC) a una carpeta local, se copian de forma predeterminada los archivos.  
  
 Las funciones de arrastrar y colocar proporcionadas por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] están diseñadas para ser altamente flexibles y personalizables, para que admitan una amplia variedad de escenarios de arrastrar y colocar.  Arrastrar y colocar permite manipular objetos en una sola aplicación o entre aplicaciones diferentes. Arrastrar y colocar entre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones y otras aplicaciones de Windows también es totalmente compatible.  
  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], cualquier <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement> puede participar en una operación de arrastrar y colocar. Los eventos y los métodos necesarios para las operaciones de arrastrar y colocar están definidos en la clase <xref:System.Windows.DragDrop>. Las clases <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement> contienen un alias para los eventos adjuntos <xref:System.Windows.DragDrop>, de modo que los eventos aparezcan en la lista de miembros de clase cuando se hereda un <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement> como elemento base. Los controladores de eventos que están asociados a estos eventos se asocian al evento adjunto <xref:System.Windows.DragDrop> subyacente y reciben la misma instancia de datos de evento. Para obtener más información, vea el evento <xref:System.Windows.UIElement.Drop?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
> La operación de arrastrar y colocar de OLE no funciona en la zona de Internet.  
  
<a name="Data_Transfer"></a>
## <a name="data-transfer"></a>Transferencia de datos  
 Arrastrar y colocar es parte de un área más general de transferencia de datos. La transferencia de datos incluye la operación de arrastrar y colocar, así como la operación de copiar y pegar. Una operación de arrastrar y colocar es análoga a una operación de copiar y pegar o cortar y pegar que se usa para transferir datos de un objeto o aplicación a otro mediante el Portapapeles del sistema. Ambos tipos de operaciones requieren:  
  
- Un objeto de origen que proporciona los datos.  
  
- Una manera de almacenar temporalmente los datos transferidos.  
  
- Un objeto de destino que recibe los datos.  
  
 En una operación de copiar y pegar, el Portapapeles del sistema se usa para almacenar temporalmente los datos transferidos; en una operación de arrastrar y colocar, se usa un <xref:System.Windows.DataObject> para almacenar los datos. Desde el punto de vista conceptual, un objeto de datos consta de uno o más pares de <xref:System.Object> que contienen los datos reales y un identificador de formato de datos correspondiente.  
  
 El origen de arrastre inicia una operación de arrastrar y colocar llamando al método estático <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> y transfiriéndole los datos transferidos. El método <xref:System.Windows.DragDrop.DoDragDrop%2A> ajustará automáticamente los datos en un <xref:System.Windows.DataObject>, si es necesario. Para un mayor control del formato de datos, puede ajustar los datos en un <xref:System.Windows.DataObject> antes de pasarlos al método <xref:System.Windows.DragDrop.DoDragDrop%2A>. El destino de colocación es responsable de extraer los datos del <xref:System.Windows.DataObject>. Para obtener más información sobre cómo trabajar con objetos de datos, consulte [Datos y objetos de datos](data-and-data-objects.md).  
  
 El origen y el destino de una operación de arrastrar y colocar son elementos de la interfaz de usuario; sin embargo, los datos que se transfieren no suelen tener una representación visual. Puede escribir código para proporcionar una representación visual de los datos que se arrastran, como ocurre al arrastrar archivos en el Explorador de Windows. De forma predeterminada, se proporciona información al usuario cambiando el cursor para representar el efecto que la operación de arrastrar y colocar tendrá en los datos, por ejemplo si los datos se mueven o se copian.  
  
### <a name="drag-and-drop-effects"></a>Efectos de arrastrar y colocar  
 Las operaciones de arrastrar y colocar pueden tener efectos distintos en los datos transferidos. Por ejemplo, puede copiar los datos o puede mover los datos. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] define una enumeración <xref:System.Windows.DragDropEffects> que puede usar para especificar el efecto de una operación de arrastrar y colocar. En el origen de arrastre, puede especificar los efectos que el origen permitirá en el método <xref:System.Windows.DragDrop.DoDragDrop%2A>. En el destino de colocación, puede especificar el efecto que pretende tener el destino en la propiedad <xref:System.Windows.DragEventArgs.Effects%2A> de la clase <xref:System.Windows.DragEventArgs>. Cuando el destino de colocación especifica su efecto deseado en el evento <xref:System.Windows.DragDrop.DragOver>, esta información se devuelve al origen de arrastre en el evento <xref:System.Windows.DragDrop.GiveFeedback>. El origen de arrastre usa esta información para informar al usuario de qué efecto pretende tener en los datos el destino de colocación. Cuando se colocan los datos, el destino de colocación especifica su efecto real en el evento <xref:System.Windows.DragDrop.Drop>. Esta información se devuelve al origen de arrastre como valor devuelto del método <xref:System.Windows.DragDrop.DoDragDrop%2A>. Si el destino de colocación devuelve un efecto que no está en la lista de orígenes de arrastre de `allowedEffects`, la operación de arrastrar y colocar se cancela sin que se produzca ninguna transferencia de datos.  
  
 Es importante recordar que, en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], los valores <xref:System.Windows.DragDropEffects> solo se usan para proporcionar comunicación entre el origen de arrastre y el destino de colocación relativa a los efectos de la operación de arrastrar y colocar. El efecto real de la operación de arrastrar y colocar depende de que se escriba el código adecuado en la aplicación.  
  
 Por ejemplo, el destino de colocación podría especificar que el efecto de colocar datos es mover los datos. Sin embargo, para mover los datos, estos deben agregarse al elemento de destino y quitarse del elemento de origen. El elemento de origen podría indicar que permite mover los datos, pero si no se proporciona el código para quitar los datos del elemento de origen, el resultado final será que los datos se copian pero no se mueven.  
  
<a name="Drag_and_Drop_Events"></a>
## <a name="drag-and-drop-events"></a>Eventos de arrastrar y colocar  
 Las operaciones de arrastrar y colocar admiten un modelo basado en eventos.  El origen de arrastre y el destino de colocación usan un conjunto estándar de eventos para controlar las operaciones de arrastrar y colocar.  Las tablas siguientes resumen los eventos estándar de arrastrar y colocar. Se trata de eventos adjuntos a la clase <xref:System.Windows.DragDrop>. Para obtener más información sobre los eventos adjuntos, consulte [Información general sobre eventos adjuntos](attached-events-overview.md).  
  
### <a name="drag-source-events"></a>Eventos del origen de arrastre  
  
|Evento|Resumen|  
|-----------|-------------|  
|<xref:System.Windows.DragDrop.GiveFeedback>|Este evento se produce continuamente durante una operación de arrastrar y colocar y permite al origen de colocación proporcionar información al usuario. Esta información suelen proporcionarse mediante un cambio en la apariencia del puntero del mouse para indicar los efectos permitidos por el destino de colocación.  Se trata de un evento de propagación.|  
|<xref:System.Windows.DragDrop.QueryContinueDrag>|Este evento se produce cuando hay un cambio en los estados del botón del mouse o el teclado durante una operación de arrastrar y colocar, y permite al origen de colocación cancelar la operación de arrastrar y colocar en función de los estados del botón o del teclado. Se trata de un evento de propagación.|  
|<xref:System.Windows.DragDrop.PreviewGiveFeedback>|Versión de tunelización de <xref:System.Windows.DragDrop.GiveFeedback>.|  
|<xref:System.Windows.DragDrop.PreviewQueryContinueDrag>|Versión de tunelización de <xref:System.Windows.DragDrop.QueryContinueDrag>.|  
  
### <a name="drop-target-events"></a>Eventos del destino de colocación  
  
|Evento|Resumen|  
|-----------|-------------|  
|<xref:System.Windows.DragDrop.DragEnter>|Este evento se produce cuando se arrastra un objeto dentro de los límites del destino de colocación. Se trata de un evento de propagación.|  
|<xref:System.Windows.DragDrop.DragLeave>|Este evento se produce cuando se arrastra un objeto fuera de los límites del destino de colocación.  Se trata de un evento de propagación.|  
|<xref:System.Windows.DragDrop.DragOver>|Este evento se produce continuamente mientras se arrastra (se mueve) un objeto dentro de los límites del destino de colocación. Se trata de un evento de propagación.|  
|<xref:System.Windows.DragDrop.Drop>|Este evento se produce cuando se coloca un objeto en el destino de colocación.  Se trata de un evento de propagación.|  
|<xref:System.Windows.DragDrop.PreviewDragEnter>|Versión de tunelización de <xref:System.Windows.DragDrop.DragEnter>.|  
|<xref:System.Windows.DragDrop.PreviewDragLeave>|Versión de tunelización de <xref:System.Windows.DragDrop.DragLeave>.|  
|<xref:System.Windows.DragDrop.PreviewDragOver>|Versión de tunelización de <xref:System.Windows.DragDrop.DragOver>.|  
|<xref:System.Windows.DragDrop.PreviewDrop>|Versión de tunelización de <xref:System.Windows.DragDrop.Drop>.|  
  
 Para controlar los eventos de arrastrar y colocar para las instancias de un objeto, agregue controladores para los eventos enumerados en las tablas anteriores. Para controlar los eventos de arrastrar y colocar en el nivel de clase, invalide los métodos virtuales On*Event y On\*PreviewEvent correspondientes. Para obtener más información, consulte [Control de clases de eventos enrutados mediante clases base de control](marking-routed-events-as-handled-and-class-handling.md#Class_Handling_of_Routed_Events).  
  
<a name="Implementing_Drag_And_Drop"></a>
## <a name="implementing-drag-and-drop"></a>Implementación de arrastrar y colocar  
 Un elemento de la interfaz de usuario puede ser un origen de arrastre, un destino de colocación o ambos. Para implementar la operación básica de arrastrar y colocar, escriba código para iniciar la operación de arrastrar y colocar y para procesar los datos colocados. Puede mejorar la experiencia de arrastrar y colocar controlando los eventos de arrastrar y colocar opcionales.  
  
 Para implementar la operación básica de arrastrar y colocar, realice las siguientes tareas:  
  
- Identifique el elemento que será un origen de arrastre. Un origen de arrastre puede ser un <xref:System.Windows.UIElement> o un <xref:System.Windows.ContentElement>.  
  
- Cree un controlador de eventos en el origen de arrastre que iniciará la operación de arrastrar y colocar. El evento suele ser un evento <xref:System.Windows.UIElement.MouseMove>.  
  
- En el controlador de eventos del origen de arrastre, llame al método <xref:System.Windows.DragDrop.DoDragDrop%2A> para que inicie la operación de arrastrar y colocar. En la llamada a <xref:System.Windows.DragDrop.DoDragDrop%2A>, especifique el origen de arrastre, los datos que se van a transferir y los efectos permitidos.  
  
- Identifique el elemento que será un destino de colocación. Un destino de colocación puede ser un <xref:System.Windows.UIElement> o un <xref:System.Windows.ContentElement>.  
  
- En el destino de colocación, establezca la propiedad <xref:System.Windows.UIElement.AllowDrop%2A> en `true`.  
  
- En el destino de colocación, cree un controlador de eventos <xref:System.Windows.DragDrop.Drop> para procesar los datos colocados.  
  
- En el controlador de eventos <xref:System.Windows.DragDrop.Drop>, extraiga los datos de <xref:System.Windows.DragEventArgs> mediante los métodos <xref:System.Windows.DataObject.GetDataPresent%2A> y <xref:System.Windows.DataObject.GetData%2A>.  
  
- En el controlador de eventos <xref:System.Windows.DragDrop.Drop>, use los datos para realizar la operación de arrastrar y colocar deseada.  
  
 Puede mejorar la implementación de arrastrar y colocar creando un <xref:System.Windows.DataObject> personalizado y controlando eventos opcionales de origen de arrastre y destino de colocación, como se muestra en las siguientes tareas:  
  
- Para transferir datos personalizados o varios elementos de datos, cree un <xref:System.Windows.DataObject> para pasar al método <xref:System.Windows.DragDrop.DoDragDrop%2A>.  
  
- Para realizar acciones adicionales durante un arrastre, controle los eventos <xref:System.Windows.DragDrop.DragEnter>, <xref:System.Windows.DragDrop.DragOver> y <xref:System.Windows.DragDrop.DragLeave> en el destino de colocación.  
  
- Para cambiar la apariencia del puntero del mouse, controle el evento <xref:System.Windows.DragDrop.GiveFeedback> en el origen de arrastre.  
  
- Para cambiar cómo se cancela la operación de arrastrar y colocar, controle el evento <xref:System.Windows.DragDrop.QueryContinueDrag> en el origen de arrastre.  
  
<a name="Drag_And_Drop_Example"></a>
## <a name="drag-and-drop-example"></a>Ejemplo de arrastrar y colocar  
 En esta sección se describe cómo se implementa una operación de arrastrar y colocar para un elemento <xref:System.Windows.Shapes.Ellipse>. <xref:System.Windows.Shapes.Ellipse> es tanto un origen de arrastre como un destino de colocación. Los datos transferidos son la representación de cadena de la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de la elipse. El siguiente XAML muestra el elemento <xref:System.Windows.Shapes.Ellipse> y los eventos relacionados de arrastrar y colocar que controla. Si desea conocer los pasos completos para implementar una función de arrastrar y colocar, consulte [Tutorial: Habilitar la técnica de arrastrar y colocar en un control de usuario](walkthrough-enabling-drag-and-drop-on-a-user-control.md).  
  
 [!code-xaml[DragDropSnippets#EllipseXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#ellipsexaml)]  
  
### <a name="enabling-an-element-to-be-a-drag-source"></a>Habilitar un elemento para que sea un origen de arrastre  
 Un objeto que es un origen de arrastre es responsable de:  
  
- Identificar cuándo se produce un arrastre.  
  
- Iniciar la operación de arrastrar y colocar.  
  
- Identificar los datos que se van a transferir.  
  
- Especificar los efectos que puede tener la operación de arrastrar y colocar en los datos transferidos.  
  
 El origen de arrastre también puede proporcionar información al usuario sobre las acciones permitidas (mover, copiar, ninguna) y puede cancelar la operación de arrastrar y colocar en función de las acciones del usuario, como presionar la tecla ESC durante la operación de arrastre.  
  
 Es responsabilidad de la aplicación determinar cuándo se produce un arrastre y, a continuación, iniciar la operación de arrastrar y colocar mediante una llamada al método <xref:System.Windows.DragDrop.DoDragDrop%2A>. Normalmente, es cuando se produce un evento <xref:System.Windows.UIElement.MouseMove> en el elemento que se va a arrastrar mientras se presiona un botón del mouse. En el ejemplo siguiente se muestra cómo iniciar una operación de arrastrar y colocar desde el controlador de eventos <xref:System.Windows.UIElement.MouseMove> de un elemento <xref:System.Windows.Shapes.Ellipse> para convertirlo en un origen de arrastre. Los datos transferidos son la representación de cadena de la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de la elipse.  
  
 [!code-csharp[DragDropSnippets#DoDragDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#dodragdrop)]
 [!code-vb[DragDropSnippets#DoDragDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#dodragdrop)]  
  
 Dentro del controlador de eventos <xref:System.Windows.UIElement.MouseMove>, llame al método <xref:System.Windows.DragDrop.DoDragDrop%2A> para que inicie la operación de arrastrar y colocar. El método <xref:System.Windows.DragDrop.DoDragDrop%2A> toma tres parámetros:  
  
- `dragSource` – Una referencia al objeto de dependencia que es el origen de los datos transferidos; suele ser el origen del evento <xref:System.Windows.UIElement.MouseMove>.  
  
- `data` – Un objeto que contiene los datos transferidos, ajustados en un <xref:System.Windows.DataObject>.  
  
- `allowedEffects` – Uno de los valores de enumeración <xref:System.Windows.DragDropEffects> que especifica los efectos permitidos de la operación de arrastrar y colocar.  
  
 Puede pasar cualquier objeto serializable en el parámetro `data`. Si los datos todavía no están ajustados en un <xref:System.Windows.DataObject>, se ajustarán automáticamente en un <xref:System.Windows.DataObject> nuevo. Para pasar varios elementos de datos, debe crear por su cuenta el <xref:System.Windows.DataObject> y pasarlo al método <xref:System.Windows.DragDrop.DoDragDrop%2A>. Para obtener más información, consulte [Datos y objetos de datos](data-and-data-objects.md).  
  
 El parámetro `allowedEffects` se usa para especificar lo que el origen de arrastre permitirá que haga el destino de colocación con los datos transferidos. Los valores comunes para un origen de arrastre son <xref:System.Windows.DragDropEffects.Copy>, <xref:System.Windows.DragDropEffects.Move> y <xref:System.Windows.DragDropEffects.All>.  
  
> [!NOTE]
> El destino de colocación también puede especificar qué efectos desea tener como respuesta a los datos colocados. Por ejemplo, si el destino de colocación no reconoce el tipo de datos que se van a colocar, puede rechazar los datos estableciendo sus efectos permitidos en <xref:System.Windows.DragDropEffects.None>. Normalmente lo hace en su controlador de eventos <xref:System.Windows.DragDrop.DragOver>.  
  
 Opcionalmente, un origen de arrastre puede controlar los eventos <xref:System.Windows.DragDrop.GiveFeedback> y <xref:System.Windows.DragDrop.QueryContinueDrag>. Estos eventos tienen controladores predeterminados que se usan a menos que marque los eventos como controlados. Normalmente, omitirá estos eventos a menos que necesite cambiar su comportamiento predeterminado.  
  
 El evento <xref:System.Windows.DragDrop.GiveFeedback> se produce continuamente mientras se arrastra el origen de arrastre. El controlador predeterminado de este evento comprueba si el origen de arrastre se encuentra sobre un destino para colocar válido. Si es así, comprueba los efectos permitidos del destino de colocación. A continuación, ofrece información al usuario final sobre los efectos de colocación permitidos. Esto suele hacerse cambiando el cursor del mouse al cursor de mover, copiar o no colocar. Solo se debe controlar este evento si necesita usar cursores personalizados para proporcionar información al usuario. Si controla este evento, asegúrese de marcarlo como controlado para que el controlador predeterminado no invalide el controlador.  
  
 El evento <xref:System.Windows.DragDrop.QueryContinueDrag> se produce continuamente mientras se arrastra el origen de arrastre. Puede controlar este evento para determinar qué acción finaliza la operación de arrastrar y colocar en función del estado de las teclas ESC, MAYÚS, CTRL y ALT, así como el estado de los botones del mouse. El controlador predeterminado para este evento cancela la operación de arrastrar y colocar si se presiona la tecla ESC y coloca los datos si se suelta el botón del mouse.  
  
> [!CAUTION]
> Estos eventos se generan continuamente durante la operación de arrastrar y colocar. Por lo tanto, debe evitar las tareas que consumen muchos recursos en los controladores de eventos.  Por ejemplo, use un cursor en caché en lugar de crear un nuevo cursor cada vez que se produzca el evento <xref:System.Windows.DragDrop.GiveFeedback>.  
  
### <a name="enabling-an-element-to-be-a-drop-target"></a>Habilitar un elemento para que sea un destino de colocación  
 Un objeto que es un destino de colocación es responsable de:  
  
- Especificar que es un destino de colocación válido.  
  
- Responder al origen de arrastre cuando se arrastra sobre el destino.  
  
- Comprobar que los datos transferidos están en un formato que puede recibir.  
  
- Procesar los datos colocados.  
  
 Para especificar que un elemento es un destino de colocación, su propiedad <xref:System.Windows.UIElement.AllowDrop%2A> se establece en `true`. A continuación, se generarán los eventos del destino de colocación en el elemento para que pueda controlarlos. Durante una operación de arrastrar y colocar, se produce la siguiente secuencia de eventos en el destino de colocación:  
  
1. <xref:System.Windows.DragDrop.DragEnter>  
  
2. <xref:System.Windows.DragDrop.DragOver>  
  
3. <xref:System.Windows.DragDrop.DragLeave> o <xref:System.Windows.DragDrop.Drop>  
  
 El evento <xref:System.Windows.DragDrop.DragEnter> se produce cuando se arrastran los datos dentro de los límites del destino de colocación. Normalmente, este evento se controla para que proporcione una vista previa de los efectos de la operación de arrastrar y colocar, si es adecuado para la aplicación. No establezca la propiedad <xref:System.Windows.DragEventArgs.Effects%2A?displayProperty=nameWithType> en el evento <xref:System.Windows.DragDrop.DragEnter>, ya que se sobrescribirá en el evento <xref:System.Windows.DragDrop.DragOver>.  
  
 El ejemplo siguiente muestra el controlador de eventos <xref:System.Windows.DragDrop.DragEnter> para un elemento <xref:System.Windows.Shapes.Ellipse>. Este código muestra una vista previa de los efectos de la operación de arrastrar y colocar guardando el pincel <xref:System.Windows.Shapes.Shape.Fill%2A> actual. A continuación, usa el método <xref:System.Windows.DataObject.GetDataPresent%2A> para comprobar si el <xref:System.Windows.DataObject> que se está arrastrando sobre la elipse contiene datos de cadena que se pueden convertir en un <xref:System.Windows.Media.Brush>. Si es así, los datos se extraen mediante el método <xref:System.Windows.DataObject.GetData%2A>. A continuación, se convierte en un <xref:System.Windows.Media.Brush> y se aplica a la elipse. El cambio se revierte en el controlador de eventos <xref:System.Windows.DragDrop.DragLeave>. Si los datos no se pueden convertir en un <xref:System.Windows.Media.Brush>, no se lleva a cabo ninguna acción.  
  
 [!code-csharp[DragDropSnippets#DragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#dragenter)]
 [!code-vb[DragDropSnippets#DragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#dragenter)]  
  
 El evento <xref:System.Windows.DragDrop.DragOver> se produce continuamente mientras se arrastran los datos sobre el destino de colocación. Este evento se empareja con el evento <xref:System.Windows.DragDrop.GiveFeedback> en el origen de arrastre. En el controlador de eventos <xref:System.Windows.DragDrop.DragOver>, suelen usarse los métodos <xref:System.Windows.DataObject.GetDataPresent%2A> y <xref:System.Windows.DataObject.GetData%2A> para comprobar si los datos transferidos están en un formato que el destino de colocación puede procesar. También se puede comprobar si está presionada alguna tecla modificadora, lo que normalmente indicará si el usuario pretende realizar una acción de mover o copiar. Una vez realizadas estas comprobaciones, se establece la propiedad <xref:System.Windows.DragEventArgs.Effects%2A?displayProperty=nameWithType> para que notifique al origen de arrastre qué efectos tendrá la colocación de los datos. El origen de arrastre recibe esta información en los argumentos del evento <xref:System.Windows.DragDrop.GiveFeedback> y puede establecer un cursor apropiado para proporcionar información al usuario.  
  
 El ejemplo siguiente muestra el controlador de eventos <xref:System.Windows.DragDrop.DragOver> para un elemento <xref:System.Windows.Shapes.Ellipse>. Este código comprueba si el <xref:System.Windows.DataObject> que se está arrastrando sobre la elipse contiene datos de cadena que se pueden convertir en un <xref:System.Windows.Media.Brush>. Si es así, establece la propiedad <xref:System.Windows.DragEventArgs.Effects%2A?displayProperty=nameWithType> en <xref:System.Windows.DragDropEffects.Copy>. Esto indica al origen de arrastre que los datos se pueden copiar a la elipse. Si los datos no se pueden convertir en un <xref:System.Windows.Media.Brush>, la propiedad <xref:System.Windows.DragEventArgs.Effects%2A?displayProperty=nameWithType> se establece en <xref:System.Windows.DragDropEffects.None>. Esto indica al origen de arrastre que la elipse no es un destino para colocar válido para los datos.  
  
 [!code-csharp[DragDropSnippets#DragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#dragover)]
 [!code-vb[DragDropSnippets#DragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#dragover)]  
  
 El evento <xref:System.Windows.DragDrop.DragLeave> se produce cuando los datos se arrastran fuera de los límites del destino sin colocarse. Este evento se controla para deshacer todo lo que se hizo en el controlador de eventos <xref:System.Windows.DragDrop.DragEnter>.  
  
 El ejemplo siguiente muestra el controlador de eventos <xref:System.Windows.DragDrop.DragLeave> para un elemento <xref:System.Windows.Shapes.Ellipse>. Este código deshace la vista previa que se realizó en el controlador de eventos <xref:System.Windows.DragDrop.DragEnter> aplicando el <xref:System.Windows.Media.Brush> guardado a la elipse.  
  
 [!code-csharp[DragDropSnippets#DragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#dragleave)]
 [!code-vb[DragDropSnippets#DragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#dragleave)]  
  
 El evento <xref:System.Windows.DragDrop.Drop> se produce cuando los datos se colocan sobre el destino de colocación; de forma predeterminada, esto ocurre cuando se suelta el botón del mouse. En el controlador de eventos <xref:System.Windows.DragDrop.Drop>, se usa el método <xref:System.Windows.DataObject.GetData%2A> para extraer los datos transferidos desde el <xref:System.Windows.DataObject> y para realizar cualquier procesamiento de datos que requiere la aplicación. El evento <xref:System.Windows.DragDrop.Drop> finaliza la operación de arrastrar y colocar.  
  
 El ejemplo siguiente muestra el controlador de eventos <xref:System.Windows.DragDrop.Drop> para un elemento <xref:System.Windows.Shapes.Ellipse>. Este código aplica los efectos de la operación de arrastrar y colocar y es similar al código del controlador de eventos <xref:System.Windows.DragDrop.DragEnter>. Comprueba si el <xref:System.Windows.DataObject> que se está arrastrando sobre la elipse contiene datos de cadena que se pueden convertir en un <xref:System.Windows.Media.Brush>. Si es así, el <xref:System.Windows.Media.Brush> se aplica a la elipse. Si los datos no se pueden convertir en un <xref:System.Windows.Media.Brush>, no se lleva a cabo ninguna acción.  
  
 [!code-csharp[DragDropSnippets#Drop](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#drop)]
 [!code-vb[DragDropSnippets#Drop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#drop)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Clipboard>
- [Tutorial: Habilitar la técnica de arrastrar y colocar en un control de usuario](walkthrough-enabling-drag-and-drop-on-a-user-control.md)
- [Temas "Cómo..."](drag-and-drop-how-to-topics.md)
- [Arrastrar y colocar](drag-and-drop.md)

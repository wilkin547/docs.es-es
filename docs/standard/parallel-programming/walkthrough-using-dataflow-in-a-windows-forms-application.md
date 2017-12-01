---
title: 'Tutorial: Usar flujos de datos en aplicaciones de Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TPL dataflow library, in Windows Forms
- Task Parallel Library, dataflows
- Windows Forms, and TPL
ms.assetid: 9c65cdf7-660c-409f-89ea-59d7ec8e127c
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d2775cc99020fd99d6e7d79cdf3e1ffcc3219146
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-using-dataflow-in-a-windows-forms-application"></a>Tutorial: Usar flujos de datos en aplicaciones de Windows Forms
Este documento muestra cómo crear una red de bloques de flujo de datos que realizan el procesamiento de imágenes en una aplicación de Windows Forms.  
  
 En este ejemplo se cargan archivos de imagen de la carpeta especificada, se crea una imagen compuesta y se muestra el resultado. En el ejemplo se utiliza el modelo de flujo de datos para distribuir las imágenes por la red. En el modelo de flujo de datos, los componentes independientes de un programa se comunican entre sí mediante mensajes. Cuando un componente recibe un mensaje, realiza alguna acción y pasa el resultado a otro componente. Compare esto con el modelo de flujo de control, en el que una aplicación utiliza estructuras de control, como por ejemplo, instrucciones condicionales, bucles, etc., para controlar el orden de las operaciones en un programa.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Lea [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) antes de empezar este tutorial.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL (espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Para instalar el <xref:System.Threading.Tasks.Dataflow> espacio de nombres, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **administrar paquetes de NuGet** en el menú proyecto y busque en línea el `Microsoft.Tpl.Dataflow` paquete.  
 
  
## <a name="sections"></a>Secciones  
 Este tutorial contiene las siguientes secciones:  
  
-   [Crear una aplicación de Windows Forms](#winforms)  
  
-   [Crear la red del flujo de datos](#network)  
  
-   [Conectar la red del flujo de datos a la interfaz de usuario](#ui)  
  
-   [Ejemplo completo](#complete)  
  
<a name="winforms"></a>   
## <a name="creating-the-windows-forms-application"></a>Crear una aplicación de Windows Forms  
 En esta sección se describe cómo crear la aplicación básica de Windows Forms y agregar controles al formulario principal.  
  
#### <a name="to-create-the-windows-forms-application"></a>Para crear la aplicación de Windows Forms  
  
1.  En [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], cree un proyecto **Aplicación de Windows Forms** de [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] o Visual Basic. En este documento, el proyecto se denomina `CompositeImages`.  
  
2.  En el Diseñador de formularios para el formulario principal, Form1.cs (Form1.vb con [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), agregue un <xref:System.Windows.Forms.ToolStrip> control.  
  
3.  Agregar un <xref:System.Windows.Forms.ToolStripButton> el control a la <xref:System.Windows.Forms.ToolStrip> control. Establecer el <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> propiedad a <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> y <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad **elegir la carpeta de**.  
  
4.  Agregue un segundo <xref:System.Windows.Forms.ToolStripButton> el control a la <xref:System.Windows.Forms.ToolStrip> control. Establecer el <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> propiedad <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, el <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad **cancelar**y el <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> propiedad para `False`.  
  
5.  Agregar un <xref:System.Windows.Forms.PictureBox> objeto al formulario principal. Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.  
  
<a name="network"></a>   
## <a name="creating-the-dataflow-network"></a>Crear la red del flujo de datos  
 En esta sección se describe cómo crear la red del flujo de datos que lleva a cabo el procesamiento de imágenes.  
  
#### <a name="to-create-the-dataflow-network"></a>Para crear la red del flujo de datos  
  
1.  Agregue a su proyecto una referencia a System.Threading.Tasks.Dataflow.dll.  
  
2.  Asegúrese de que Form1.cs (Form1.vb para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contenga las siguientes instrucciones `using` (`Using` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]):  
  
     [!code-csharp[TPLDataflow_CompositeImages#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#1)]  
  
3.  Agregue a la clase `Form1` los miembros de datos siguientes:  
  
     [!code-csharp[TPLDataflow_CompositeImages#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#2)]  
  
4.  Agregue el método siguiente, `CreateImageProcessingNetwork`, a la clase `Form1`. Este método crea la red de procesamiento de imágenes.  
  
     [!code-csharp[TPLDataflow_CompositeImages#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#3)]  
  
5.  Implemente el método `LoadBitmaps`.  
  
     [!code-csharp[TPLDataflow_CompositeImages#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#4)]  
  
6.  Implemente el método `CreateCompositeBitmap`.  
  
     [!code-csharp[TPLDataflow_CompositeImages#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#5)]  
  
    > [!NOTE]
    >  La versión de C# de la `CreateCompositeBitmap` método utiliza punteros para permitir un procesamiento eficiente de los <xref:System.Drawing.Bitmap?displayProperty=nameWithType> objetos. Por lo tanto, debe habilitar la opción **Permitir código no seguro** en el proyecto para utilizar la palabra clave [unsafe](~/docs/csharp/language-reference/keywords/unsafe.md). Para obtener más información acerca de cómo habilitar el código no seguro en un [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] del proyecto, vea [página compilación, Diseñador de proyectos (C#)] https://msdn.microsoft.com/library/kb4wyys2).  
  
 En la tabla siguiente se describen los miembros de la red.  
  
|Miembro|Tipo|Descripción|  
|------------|----------|-----------------|  
|`loadBitmaps`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Toma una ruta de acceso de carpeta como entrada y genera una colección de <xref:System.Drawing.Bitmap> objetos como salida.|  
|`createCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Toma una colección de <xref:System.Drawing.Bitmap> objetos como entrada y genera un mapa de bits compuesto como salida.|  
|`displayCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Muestra el mapa de bits compuesto en el formulario.|  
|`operationCancelled`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Muestra una imagen para indicar que la operación se cancela y permite al usuario seleccionar otra carpeta.|  
  
 Para conectar los bloques de flujo de datos para formar una red, este ejemplo se utiliza la <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> método. El <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> método contiene una versión sobrecargada que toma un <xref:System.Predicate%601> objeto que determina si el bloque de destino acepta o rechaza un mensaje. Este mecanismo de filtrado permite que los bloques de mensajes reciban solo ciertos valores. En este ejemplo, la red puede dividirse en ramas de una de dos maneras. La rama principal carga las imágenes desde el disco, crea la imagen compuesta y la muestra en el formulario. La rama alternativa cancela la operación actual. El <xref:System.Predicate%601> objetos permiten que los bloques de flujo de datos a lo largo de la bifurcación main para cambiar a la bifurcación alternativa rechazando determinados mensajes. Por ejemplo, si el usuario cancela la operación, el bloque de flujo de datos `createCompositeBitmap` produce `null` (`Nothing` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) como salida. El bloque de flujo de datos `displayCompositeBitmap` rechaza valores de entrada `null` y, por lo tanto, el mensaje se ofrece a `operationCancelled`. El bloque de flujo de datos `operationCancelled` acepta todos los mensajes y, por lo tanto, muestra una imagen para indicar que se ha cancelado la operación.  
  
 En la ilustración siguiente se muestra la red de procesamiento de imágenes.  
  
 ![Red de procesamiento de imágenes](../../../docs/standard/parallel-programming/media/dataflowwinforms.png "DataflowWinForms")  
  
 Dado que los bloques de flujo de datos `displayCompositeBitmap` y `operationCancelled` actúan sobre la interfaz de usuario, es importante que esta acción se produzca en el subproceso de interfaz de usuario. Para ello, durante la construcción, estos objetos proporcionan una <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> objeto que tiene el <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> propiedad establecida en <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>. El método <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> crea un objeto <xref:System.Threading.Tasks.TaskScheduler> que funciona en el contexto de sincronización actual. Como se llama al método `CreateImageProcessingNetwork` desde el controlador del botón **Elegir carpeta**, que se ejecuta en el subproceso de la interfaz de usuario, las acciones para los bloques de flujo de datos `displayCompositeBitmap` y `operationCancelled` también se ejecutan en el subproceso de la interfaz de usuario.  
  
 Este ejemplo usa un token de cancelación compartidos en lugar de establecer la <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> propiedad porque el <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> propiedad permanentemente cancela la ejecución de bloques de flujo de datos. En este ejemplo, un token de cancelación permite reutilizar la misma red del flujo de datos varias veces, incluso cuando el usuario cancela una o varias operaciones. Para obtener un ejemplo que usa <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> para cancelar la ejecución de un bloque de flujo de datos de modo permanente, consulte [Cómo: cancelar un Dataflow Block](../../../docs/standard/parallel-programming/how-to-cancel-a-dataflow-block.md).  
  
<a name="ui"></a>   
## <a name="connecting-the-dataflow-network-to-the-user-interface"></a>Conectar la red del flujo de datos a la interfaz de usuario  
 En esta sección se describe cómo conectar la red del flujo de datos a la interfaz de usuario. La creación de la imagen compuesta y la cancelación de la operación se inician desde los botones **Elegir carpeta** y **Cancelar**. Cuando el usuario elige cualquiera de ellos, se inicia la acción correspondiente de forma asincrónica.  
  
#### <a name="to-connect-the-dataflow-network-to-the-user-interface"></a>Para conectar la red del flujo de datos a la interfaz de usuario  
  
1.  En el Diseñador de formularios del formulario principal, cree un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> eventos para el **elegir la carpeta** botón.  
  
2.  Implemente el <xref:System.Windows.Forms.ToolStripItem.Click> eventos para el **elegir la carpeta** botón.  
  
     [!code-csharp[TPLDataflow_CompositeImages#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#6)]  
  
3.  En el Diseñador de formularios del formulario principal, cree un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> eventos para el **cancelar** botón.  
  
4.  Implemente el <xref:System.Windows.Forms.ToolStripItem.Click> eventos para el **cancelar** botón.  
  
     [!code-csharp[TPLDataflow_CompositeImages#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#7)]  
  
<a name="complete"></a>   
## <a name="the-complete-example"></a>Ejemplo completo  
 En el ejemplo siguiente se muestra el código completo de este tutorial.  
  
 [!code-csharp[TPLDataflow_CompositeImages#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#100)]  
  
 En la ilustración siguiente se muestra la salida típica de la carpeta \Sample Pictures\ común.  
  
 ![Aplicación de Windows Forms](../../../docs/standard/parallel-programming/media/tpldataflow-compositeimages.gif "TPLDataflow_CompositeImages")  
  
## <a name="next-steps"></a>Pasos siguientes  
  
## <a name="see-also"></a>Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)

---
title: "Walkthrough: Using Dataflow in a Windows Forms Application | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "TPL dataflow library, in Windows Forms"
  - "Task Parallel Library, dataflows"
  - "Windows Forms, and TPL"
ms.assetid: 9c65cdf7-660c-409f-89ea-59d7ec8e127c
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Walkthrough: Using Dataflow in a Windows Forms Application
Este documento se muestra cómo crear una red de bloques de flujo de datos que realizan el procesamiento de imágenes en una aplicación de Windows Forms.  
  
 Este ejemplo carga los archivos de imagen de la carpeta especificada, crea una imagen compuesta, y muestra el resultado.  El ejemplo utiliza el modelo de flujo de datos para enrutar imágenes a través de la red.  En el modelo de flujo de datos, los componentes independientes de un programa se comunican entre sí enviando mensajes.  Cuando un componente recibe un mensaje, realiza alguna acción y pasa el resultado a otro componente.  Compare esto con el modelo de flujo de control, en el que una aplicación usa estructuras de control, como instrucciones condicionales, bucles, etc., para controlar el orden de las operaciones en un programa.  
  
## Requisitos previos  
 Lea [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) antes de iniciar este tutorial.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL \(espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Para instalar el espacio de nombres <xref:System.Threading.Tasks.Dataflow>, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **Administrar paquetes NuGet** en el menú Proyecto, y busque en línea el paquete `Microsoft.Tpl.Dataflow`.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL \(espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Para instalar el espacio de nombres <xref:System.Threading.Tasks.Dataflow>, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **Administrar paquetes NuGet** en el menú Proyecto, y busque en línea el paquete `Microsoft.Tpl.Dataflow`.  
  
## Secciones  
 Este tutorial contiene las siguientes secciones:  
  
-   [Crear la aplicación de formularios Windows Forms](#winforms)  
  
-   [Crear la red de flujo de datos](#network)  
  
-   [Conexión de red de flujo de datos con la interfaz de usuario](#ui)  
  
-   [Ejemplo completo](#complete)  
  
<a name="winforms"></a>   
## Crear la aplicación de formularios Windows Forms  
 En esta sección se describe cómo crear una aplicación de Windows Forms básicos y agregar controles al formulario principal.  
  
#### Para crear la aplicación de Windows Forms  
  
1.  En [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], cree [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] o un proyecto de Visual Basic **Aplicación de Windows Forms** .  En este documento, el proyecto se denomina `CompositeImages`.  
  
2.  En el diseñador de formularios para el formulario principal, Form1.cs \(Form1.vb para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), agregue un control de <xref:System.Windows.Forms.ToolStrip> .  
  
3.  Agregue un control de <xref:System.Windows.Forms.ToolStripButton> al control de <xref:System.Windows.Forms.ToolStrip> .  Establezca la propiedad de <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> a <xref:System.Windows.Forms.ToolStripItemDisplayStyle> y la propiedad de <xref:System.Windows.Forms.ToolStripItem.Text%2A> para elegir la carpeta.  
  
4.  Agregue un control de <xref:System.Windows.Forms.ToolStripButton> de segundo al control de <xref:System.Windows.Forms.ToolStrip> .  Establezca la propiedad de <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> a <xref:System.Windows.Forms.ToolStripItemDisplayStyle>, la propiedad de <xref:System.Windows.Forms.ToolStripItem.Text%2A> para cancelar, y la propiedad de <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> a `False`.  
  
5.  Agregue un objeto de <xref:System.Windows.Forms.PictureBox> al formulario principal.  Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle>.  
  
<a name="network"></a>   
## Crear la red de flujo de datos  
 En esta sección se describe cómo crear la red de flujo de datos que realiza el procesamiento de imágenes.  
  
#### Para crear la red de flujo de datos  
  
1.  Agregue una referencia a System.Threading.Tasks.Dataflow.dll al proyecto.  
  
2.  Asegúrese de que Form1.cs \(Form1.vb para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) contiene las siguientes instrucciones de `using` \(`Using` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\):  
  
     [!code-csharp[TPLDataflow_CompositeImages#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#1)]  
  
3.  Agregue los siguientes miembros de datos a la clase de `Form1` :  
  
     [!code-csharp[TPLDataflow_CompositeImages#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#2)]  
  
4.  Agregue el método siguiente, `CreateImageProcessingNetwork`, a la clase de `Form1` .  Este método crea la red de procesamiento de imágenes.  
  
     [!code-csharp[TPLDataflow_CompositeImages#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#3)]  
  
5.  Implemente el método `LoadBitmaps`.  
  
     [!code-csharp[TPLDataflow_CompositeImages#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#4)]  
  
6.  Implemente el método `CreateCompositeBitmap`.  
  
     [!code-csharp[TPLDataflow_CompositeImages#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#5)]  
  
    > [!NOTE]
    >  La versión de C\# del método de `CreateCompositeBitmap` utiliza punteros para habilitar el procesamiento eficaz de los objetos de <xref:System.Drawing.Bitmap?displayProperty=fullName> .  Por consiguiente, debe habilitar la opción de **Permitir código no seguro** en el proyecto para utilizar la palabra clave de [seguro](../Topic/unsafe%20\(C%23%20Reference\).md) .  Para obtener más información sobre cómo habilitar código no seguro en un proyecto de [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] , vea [Compilar \(Página, Diseñador de proyectos\) \(C\#\)](../Topic/Build%20Page,%20Project%20Designer%20\(C%23\).md).  
  
 En la tabla siguiente se describen los miembros de la red.  
  
|Miembro|Tipo|Descripción|  
|-------------|----------|-----------------|  
|`loadBitmaps`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Toma una ruta de la carpeta como entrada y genera una colección de objetos <xref:System.Drawing.Bitmap> como resultado.|  
|`createCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Toma una colección de objetos <xref:System.Drawing.Bitmap> como entrada y presenta un mapa de bits compuesto como resultado.|  
|`displayCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Muestra el mapa de bits compuesto en el formulario.|  
|`operationCancelled`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Muestra una imagen para indicar que se cancele la operación y permite al usuario seleccionar otra carpeta.|  
  
 Para conectar los bloques de flujo de datos para formar una red, este ejemplo utiliza el método de <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> .  El método de <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> contiene una versión sobrecargada que toma un objeto de <xref:System.Predicate%601> que determina si el bloque de destino acepta o rechaza un mensaje.  Este mecanismo de filtrado habilita los bloques de mensajes a ciertos valores RO.  En este ejemplo, la red puede crear bifurcaciones de dos maneras.  La bifurcación principal carga las imágenes desde el disco, crea la imagen compuesta, y muestra esa imagen en el formulario.  Alternar las cancelaciones de bifurcación la operación actual.  Los objetos de <xref:System.Predicate%601> permiten a los bloques de flujo de datos a lo largo de la bifurcación principal para cambiar a la alternativa bifurcación rechazando determinados mensajes.  Por ejemplo, si el usuario cancela la operación, el bloque `createCompositeBitmap` de flujo de datos genera `null` \(`Nothing` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) como resultado.  El bloque `displayCompositeBitmap` de flujo de datos rechaza valores de entrada de `null` y, por consiguiente, el mensaje se proporciona a `operationCancelled`.  El bloque `operationCancelled` de flujo de datos acepta todos los mensajes y por lo tanto, muestra una imagen para indicar que la operación se cancela.  
  
 La siguiente ilustración se muestra la red de procesamiento de imágenes.  
  
 ![La red de procesamiento de imágenes](../../../docs/standard/parallel-programming/media/dataflowwinforms.png "DataflowWinForms")  
  
 Dado que los bloques de flujo de datos de `displayCompositeBitmap` y de `operationCancelled` representar en la interfaz de usuario, es importante que estas acciones aparecen en el subproceso de interfaz de usuario.  Para ello, durante la creación, estos objetos cada proporcionan un objeto de <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> que tiene la propiedad de <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> establecida en <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName>.  El método de <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName> crea un objeto de <xref:System.Threading.Tasks.TaskScheduler> que realice el trabajo en el contexto de sincronización.  Dado que el método de `CreateImageProcessingNetwork` se denomina del controlador del botón de la carpeta de elegir, que se ejecuta en el subproceso de interfaz de usuario, acciones para los bloques de flujo de datos de `displayCompositeBitmap` y de `operationCancelled` también se ejecutan en el subproceso de interfaz de usuario.  
  
 Este ejemplo utiliza un símbolo compartido de cancelación en lugar de establecer la propiedad de <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> porque la propiedad de <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> cancela permanentemente la ejecución del bloque de flujo de datos.  Un token de cancelación permite a este ejemplo reutilizar los mismos varias veces la red de flujo de datos, incluso cuando el usuario cancela una o más operaciones.  Para obtener un ejemplo que utiliza <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> para cancelar permanentemente la ejecución de un bloque de flujo de datos, vea [How to: Cancel a Dataflow Block](../../../docs/standard/parallel-programming/how-to-cancel-a-dataflow-block.md).  
  
<a name="ui"></a>   
## Conexión de red de flujo de datos con la interfaz de usuario  
 Esta sección describe cómo conectar la red de flujo de datos a la interfaz de usuario.  Creación de imagen compuesta y cancelar la operación se inician de carpeta y de los botones Cancelar choose.  Cuando el usuario elige cualquiera de estos botones, la acción adecuada se inicia de forma asincrónica.  
  
#### Para conectar la red de flujo de datos a la interfaz de usuario  
  
1.  En el diseñador de formularios para el formulario principal, cree un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click> para el botón de la carpeta de elegir.  
  
2.  Implemente el evento de <xref:System.Windows.Forms.ToolStripItem.Click> para el botón de la carpeta de elegir.  
  
     [!code-csharp[TPLDataflow_CompositeImages#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#6)]  
  
3.  En el diseñador de formularios para el formulario principal, cree un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click> para el botón cancel.  
  
4.  Implemente el evento de <xref:System.Windows.Forms.ToolStripItem.Click> para el botón cancel.  
  
     [!code-csharp[TPLDataflow_CompositeImages#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#7)]  
  
<a name="complete"></a>   
## Ejemplo completo  
 El ejemplo siguiente se muestra el código completo de este tutorial.  
  
 [!code-csharp[TPLDataflow_CompositeImages#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#100)]  
  
 La ilustración siguiente se muestra la salida normal para la carpeta común de Pictures\\ de \\Sample.  
  
 ![Aplicación de Windows Forms](../../../docs/standard/parallel-programming/media/tpldataflow-compositeimages.gif "TPLDataflow\_CompositeImages")  
  
## Pasos siguientes  
  
## Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
---
title: "Quitar el estado de vista que el diseñador agrega a un archivo XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a801ce22-8699-483c-a392-7bb3834aae4f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d9f153d212e1180e5de92a6299d2fbb2d6864c42
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="removing-the-view-state-the-designer-adds-to-an-xaml-file"></a><span data-ttu-id="0e3fa-102">Quitar el estado de vista que el diseñador agrega a un archivo XAML</span><span class="sxs-lookup"><span data-stu-id="0e3fa-102">Removing the View State the Designer Adds to an XAML File</span></span>
<span data-ttu-id="0e3fa-103">Este ejemplo muestra cómo crear una clase que se deriva de <xref:System.Windows.Markup.XamlWriter> y quita el estado de vista de un archivo XAML.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-103">This sample demonstrates how to create a class that derives from <xref:System.Windows.Markup.XamlWriter> and removes view state from a XAML file.</span></span> [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)]<span data-ttu-id="0e3fa-104"> escribe información en el documento XAML, que se conoce como estado de la vista.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-104"> writes information into the XAML document, which is known as view state.</span></span> <span data-ttu-id="0e3fa-105">El estado de la vista hace referencia a la información que se necesita en tiempo de diseño, como la posición del diseño, que no se necesita en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-105">View state refers to the information that is required at design time, such as layout positioning, that is not required at runtime.</span></span> [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)]<span data-ttu-id="0e3fa-106"> inserta esta información en el documento XAML mientras se edita.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-106"> inserts this information into the XAML document as it is edited.</span></span> [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)]<span data-ttu-id="0e3fa-107"> escribe el estado de la vista en el archivo XAML con el atributo `mc:Ignorable`, por lo que esta información no se carga cuando el tiempo de ejecución carga el archivo XAML.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-107"> writes the view state into the XAML file with the `mc:Ignorable` attribute, so this information is not loaded when the runtime loads the XAML file.</span></span> <span data-ttu-id="0e3fa-108">Este ejemplo muestra cómo crear una clase que quite esa información del estado de vista mientras se procesan los nodos XAML.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-108">This sample demonstrates how to create a class that removes that view state information while processing XAML nodes.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="0e3fa-109">Explicación</span><span class="sxs-lookup"><span data-stu-id="0e3fa-109">Discussion</span></span>  
 <span data-ttu-id="0e3fa-110">En este ejemplo se muestra cómo crear un sistema de escritura personalizado.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-110">This sample demonstrates how to create a custom writer.</span></span>  
  
 <span data-ttu-id="0e3fa-111">Para compilar un sistema de escritura XAML personalizado, cree una clase que herede de la clase <xref:System.Windows.Markup.XamlWriter>.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-111">To build a custom XAML writer, create a class that inherits from <xref:System.Windows.Markup.XamlWriter>.</span></span> <span data-ttu-id="0e3fa-112">Como los escritores de XAML a menudo están anidados, es habitual realizar un seguimiento de un sistema de escritura XAML "interno".</span><span class="sxs-lookup"><span data-stu-id="0e3fa-112">As XAML writers are often nested, it is typical to keep track of an "inner" XAML writer.</span></span> <span data-ttu-id="0e3fa-113">Estos "interno" escritores pueden considerarse como la referencia a la pila restante de los escritores XAML, lo que permite tener varios puntos de entrada para trabajar y, a continuación, delegar el procesamiento al resto de la pila.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-113">These "inner’ writers can be thought of as the reference to the remaining stack of XAML writers, allowing you to have multiple entry points to do work and then delegate processing to the remainder of the stack.</span></span>  
  
 <span data-ttu-id="0e3fa-114">En este ejemplo, hay algunos elementos de interés.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-114">In this sample, there are a few items of interest.</span></span> <span data-ttu-id="0e3fa-115">Uno es la comprobación para ver si el elemento que se está escribiendo procede de un espacio de nombres de diseñador.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-115">One is the check to see whether the item being written is from a designer namespace.</span></span> <span data-ttu-id="0e3fa-116">Observe que esto también elimina el uso de otros tipos del espacio de nombres del diseñador en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-116">Note that this also strips out the use of other types from the designer namespace in a workflow.</span></span>  
  
```csharp
static Boolean IsDesignerAttachedProperty(XamlMember xamlMember)  
{  
    return xamlMember.IsAttachable &&  
        xamlMember.PreferredXamlNamespace.Equals(c_sapNamespaceURI, StringComparison.OrdinalIgnoreCase);  
}  
  
const String c_sapNamespaceURI = "http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation";  

// The next item of interest is the constructor, where the utilization of the inner XAML writer is seen.  
public ViewStateCleaningWriter(XamlWriter innerWriter)  
{  
    this.InnerWriter = innerWriter;  
    this.MemberStack = new Stack<XamlMember>();  
}  
  
XamlWriter InnerWriter {get; set; }  
Stack<XamlMember> MemberStack {get; set; }  
```  
  
 <span data-ttu-id="0e3fa-117">Esto crea también una pila de miembros XAML que se utilizan al atravesar la secuencia de nodos.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-117">This also creates a stack of XAML members that are used while traversing the node stream.</span></span> <span data-ttu-id="0e3fa-118">El trabajo restante de este ejemplo se encuentra en gran medida en la <!--zz  <xref:System.Windows.Markup.XamlWriter.WriteStartMember%2A>--> `System.Windows.Markup.XamlWriter.WriteStartMember` método.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-118">The remaining work of this sample is largely contained in the <!--zz  <xref:System.Windows.Markup.XamlWriter.WriteStartMember%2A>--> `System.Windows.Markup.XamlWriter.WriteStartMember` method.</span></span>  
  
```csharp
public override void WriteStartMember(XamlMember xamlMember)  
{  
    MemberStack.Push(xamlMember);

    if (IsDesignerAttachedProperty(xamlMember))  
    {  
        m_attachedPropertyDepth++;  
    }  
  
    if (m_attachedPropertyDepth > 0)  
    {  
        return;  
    }  
  
    InnerWriter.WriteStartMember(xamlMember);  
}  
```  
  
 <span data-ttu-id="0e3fa-119">A continuación, los métodos posteriores comprueban si siguen estando incluidos en un contenedor de estado de vista, y en ese caso, devuelven y no pasan el nodo a la pila del sistema de escritura.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-119">Subsequent methods then check to see whether they are still contained in a view state container, and if so, return, and do not pass the node down the writer stack.</span></span>  
  
```csharp
public override void WriteValue(Object value)  
{  
    if (m_attachedPropertyDepth > 0)  
    {  
        return;  
    }  
  
    InnerWriter.WriteValue(value);  
}  
```  
  
 <span data-ttu-id="0e3fa-120">Para utilizar un sistema de escritura de XAML personalizado, debe encadenarlo en una pila de sistemas de escritura de XAML.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-120">To use a custom XAML writer, you must chain it together in a stack of XAML writers.</span></span> <span data-ttu-id="0e3fa-121">El código siguiente muestra cómo puede utilizarse esto.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-121">The following code shows how this can be used.</span></span>  
  
```csharp 
XmlWriterSettings writerSettings = new XmlWriterSettings {  Indent = true };  
XmlWriter xmlWriter = XmlWriter.Create(File.OpenWrite(args[1]), writerSettings);  
XamlXmlWriter xamlWriter = new XamlXmlWriter(xmlWriter, new XamlSchemaContext());  
XamlServices.Save(new ViewStateCleaningWriter(ActivityXamlServices.CreateBuilderWriter(xamlWriter)), ab);  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="0e3fa-122">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="0e3fa-122">To use this sample</span></span>  
  
1. <span data-ttu-id="0e3fa-123">Abra el archivo de solución ViewStateCleaningWriter.sln utilizando [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e3fa-123">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ViewStateCleaningWriter.sln solution file.</span></span>  
  
2. <span data-ttu-id="0e3fa-124">Abra un símbolo del sistema y navegue al directorio donde ViewStageCleaningWriter.exe está compilado.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-124">Open a command prompt and navigate to the directory where the ViewStageCleaningWriter.exe is built.</span></span>  
  
3. <span data-ttu-id="0e3fa-125">Ejecute ViewStateCleaningWriter.exe en el archivo Workflow1.xaml.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-125">Run ViewStateCleaningWriter.exe on the Workflow1.xaml file.</span></span>  

   <span data-ttu-id="0e3fa-126">La sintaxis de la aplicación ejecutable se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-126">The syntax for the executable is shown in the following example.</span></span>  
  
   ```console
   ViewStateCleaningWriter.exe [input file] [output file]
   ```
   
   <span data-ttu-id="0e3fa-127">Esto genera un archivo XAML a \[outfile], que tiene toda su información de estado de vista quitada.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-127">This outputs a XAML file to \[outfile], which has all its view state information removed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e3fa-128">En un flujo de trabajo <xref:System.Activities.Statements.Sequence>, se quitan varias sugerencias de virtualización.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-128">For a <xref:System.Activities.Statements.Sequence> workflow, a number of virtualization hints are removed.</span></span> <span data-ttu-id="0e3fa-129">Esto hace que el diseñador vuelva a calcular el diseño la próxima vez que se carga.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-129">This causes the designer to recalculate layout the next time it is loaded.</span></span> <span data-ttu-id="0e3fa-130">Cuando se utiliza este ejemplo de <xref:System.Activities.Statements.Flowchart>, se elimina toda la información de posición y de enrutamiento de línea y en la posterior carga en el diseñador, todas las actividades se apilan en el lado izquierdo de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-130">When you use this sample for a <xref:System.Activities.Statements.Flowchart>, all positioning and line routing information are removed and on subsequent loading into the designer, all activities are stacked on the left side of the screen.</span></span>  
  
#### <a name="to-create-a-sample-xaml-file-for-use-with-this-sample"></a><span data-ttu-id="0e3fa-131">Para crear un archivo XAML de muestra para usar con este ejemplo</span><span class="sxs-lookup"><span data-stu-id="0e3fa-131">To create a sample XAML file for use with this sample</span></span>  
  
1. <span data-ttu-id="0e3fa-132">Abra [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e3fa-132">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2. <span data-ttu-id="0e3fa-133">Cree una aplicación de consola de flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-133">Create a new Workflow Console Application.</span></span>  
  
3. <span data-ttu-id="0e3fa-134">Arrastre y coloque algunas actividades en el lienzo</span><span class="sxs-lookup"><span data-stu-id="0e3fa-134">Drag and drop a few activities onto the canvas</span></span>  
  
4. <span data-ttu-id="0e3fa-135">Guarde el archivo XAML de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-135">Save the workflow XAML file.</span></span>  
  
5. <span data-ttu-id="0e3fa-136">Inspeccione el archivo XAML para ver las propiedades asociadas con el estado de vista.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-136">Inspect the XAML file to see the view state attached properties.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0e3fa-137">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0e3fa-138">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-138">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="0e3fa-139">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0e3fa-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0e3fa-140">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-140">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`

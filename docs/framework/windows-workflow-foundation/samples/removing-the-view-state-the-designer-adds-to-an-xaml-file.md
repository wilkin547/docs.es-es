---
title: "Quitar el estado de vista que el dise&#241;ador agrega a un archivo XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a801ce22-8699-483c-a392-7bb3834aae4f
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Quitar el estado de vista que el dise&#241;ador agrega a un archivo XAML
Este ejemplo muestra cómo crear una clase que se deriva de <xref:System.Windows.Markup.XamlWriter> y quita el estado de la vista de un archivo XAML.[!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] escribe información en el documento XAML, que se conoce como estado de la vista.El estado de la vista hace referencia a la información que se necesita en tiempo de diseño, como la posición del diseño, que no se necesita en tiempo de ejecución.[!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] inserta esta información en el documento XAML mientras se edita.[!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] escribe el estado de la vista en el archivo XAML con el atributo `mc:Ignorable`, por lo que esta información no se carga cuando el runtime carga el archivo XAML.Este ejemplo muestra cómo crear una clase que quite esa información del estado de vista mientras se procesan los nodos XAML.  
  
## Análisis  
 En este ejemplo se muestra cómo crear un sistema de escritura personalizado.  
  
 Para compilar un sistema de escritura XAML personalizado, cree una clase que herede de la clase <xref:System.Windows.Markup.XamlWriter>.Dado que los sistemas de escritura de XAML están a menudo anidados, normalmente se realiza un seguimiento de un sistema de escritura de XAML "interno."Estos sistemas de escritura "internos" se pueden considerar como la referencia a la pila restante de sistemas de escritura de XAML, lo que le permite tener varios puntos de entrada para hacer el trabajo y después delegar el procesamiento al resto de la pila.  
  
 En este ejemplo, hay algunos elementos de interés.Uno es la comprobación para ver si el elemento que se está escribiendo procede de un espacio de nombres de diseñador.Observe que esto también elimina el uso de otros tipos del espacio de nombres del diseñador en un flujo de trabajo.  
  
```  
static Boolean IsDesignerAttachedProperty(XamlMember xamlMember)  
{  
return xamlMember.IsAttachable &&  
   xamlMember.PreferredXamlNamespace.Equals(c_sapNamespaceURI, StringComparison.OrdinalIgnoreCase);  
}  
  
const String c_sapNamespaceURI = "http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation";  
The next item of interest is the constructor, where the utilization of the inner XAML writer is seen.  
public ViewStateCleaningWriter(XamlWriter innerWriter)  
{  
this.InnerWriter = innerWriter;  
this.MemberStack = new Stack<XamlMember>();  
}  
  
XamlWriter InnerWriter {get; set; }  
Stack<XamlMember> MemberStack {get; set; }  
  
```  
  
 Esto crea también una pila de miembros XAML que se utilizan al atravesar la secuencia de nodos.El trabajo restante de este ejemplo se encuentra fundamentalmente en el método <xref:System.Windows.Markup.XamlWriter.WriteStartMember%2A>.  
  
```  
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
  
 A continuación, los métodos posteriores comprueban si siguen estando incluidos en un contenedor de estado de vista, y en ese caso, devuelven y no pasan el nodo a la pila del sistema de escritura.  
  
```  
public override void WriteValue(Object value)  
{  
if (m_attachedPropertyDepth > 0)  
{  
return;  
}  
  
InnerWriter.WriteValue(value);  
}  
```  
  
 Para utilizar un sistema de escritura de XAML personalizado, debe encadenarlo en una pila de sistemas de escritura de XAML.El código siguiente muestra cómo puede utilizarse esto.  
  
```  
XmlWriterSettings writerSettings = new XmlWriterSettings {  Indent = true };  
XmlWriter xmlWriter = XmlWriter.Create(File.OpenWrite(args[1]), writerSettings);  
XamlXmlWriter xamlWriter = new XamlXmlWriter(xmlWriter, new XamlSchemaContext());  
XamlServices.Save(new ViewStateCleaningWriter(ActivityXamlServices.CreateBuilderWriter(xamlWriter)), ab);  
  
```  
  
#### Para utilizar este ejemplo  
  
1.  Abra el archivo de solución ViewStateCleaningWriter.sln utilizando [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Abra un símbolo del sistema y navegue al directorio donde ViewStageCleaningWriter.exe está compilado.  
  
3.  Ejecute ViewStateCleaningWriter.exe en el archivo Workflow1.xaml.  
  
     La sintaxis de la aplicación ejecutable se muestra en el siguiente ejemplo.  
  
 **ViewStateCleaningWriter.exe \[archivo de entrada\] \[archivo de salida\]**     Esto genera un archivo XAML a \[outfile\] del que se ha eliminado toda la información de estado de vista.  
  
    > [!NOTE]
    >  En un flujo de trabajo <xref:System.Activities.Statements.Sequence>, se quitan varias sugerencias de virtualización.Esto hace que el diseñador vuelva a calcular el diseño la próxima vez que se carga.Cuando se utiliza este ejemplo de <xref:System.Activities.Statements.Flowchart>, se elimina toda la información de posición y de enrutamiento de línea y en la posterior carga en el diseñador, todas las actividades se apilan en el lado izquierdo de la pantalla.  
  
#### Para crear un archivo XAML de muestra para usar con este ejemplo  
  
1.  Abra [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Cree una aplicación de consola de flujos de trabajo.  
  
3.  Arrastre y coloque algunas actividades en el lienzo  
  
4.  Guarde el archivo XAML de flujo de trabajo.  
  
5.  Inspeccione el archivo XAML para ver las propiedades asociadas con el estado de vista.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>: \WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`  
  
## Vea también
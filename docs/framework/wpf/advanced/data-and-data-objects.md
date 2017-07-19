---
title: "Datos y objetos de datos | Microsoft Docs"
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
  - "transferencia de datos [WPF], arrastrar y colocar"
  - "DataFormats (clase) [WPF]"
  - "DataObject (clase) [WPF]"
ms.assetid: 5967d557-1867-420f-a524-ae3af78402da
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Datos y objetos de datos
Los datos que se transfieren como parte de una operación de arrastrar y colocar se almacenan en un objeto de datos.  Conceptualmente, un objeto de datos se compone de uno o varios de los siguientes pares:  
  
-   Un <xref:System.Object> que contiene los datos reales.  
  
-   Un identificador del formato de datos correspondiente.  
  
 Los datos en sí pueden estar compuestos de cualquier elemento que se puede representar como una clase base <xref:System.Object>.  El formato de datos correspondiente es una cadena o <xref:System.Type> que proporciona información sobre el formato de los datos.  Los objetos de datos permiten hospedar varios pares de datos\/formato de datos; esto permite que un mismo objeto de datos proporcione los datos en varios formatos.  
  
<a name="Data_and_Data_Objects"></a>   
## Objetos de datos  
 Todos los objetos de datos deben implementar la interfaz <xref:System.Windows.IDataObject>, que proporciona el siguiente conjunto de métodos estándar que habilitan y facilitan la transferencia de datos.  
  
|Método|Resumen|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Recupera un objeto de datos en un formato de datos especificado.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Comprueba si los datos están disponibles en un formato especificado o se pueden convertir a él.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Devuelve una lista de formatos en los que se almacenan los datos de este objeto de datos; o bien, a los que se pueden convertir.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Almacena los datos especificados en este objeto de datos.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una implementación básica de <xref:System.Windows.IDataObject> en la clase <xref:System.Windows.DataObject>.  La clase <xref:System.Windows.DataObject> estándar es suficiente para muchos escenarios comunes de transferencia de datos.  
  
 Hay varios formatos predefinidos, tales como mapa de bits, CSV, archivo, HTML, RTF, cadena, texto y audio.  Para obtener información sobre formatos de datos predefinidos proporcionados con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte el tema de referencia de la clase <xref:System.Windows.DataFormats>.  
  
 Los objetos de datos suelen incluir una función para convertir automáticamente datos almacenados en un formato a un formato diferente al extraer los datos; esta función se denomina autoconversión.  Al consultar los formatos de datos disponibles en un objeto de datos, los formatos de datos autoconvertibles se pueden filtrar para distinguirlos de los formatos de datos nativos llamando al método <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> o <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> y estableciendo el parámetro `autoConvert` en `false`.  Al agregar datos a un objeto de datos con el método <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29>, se puede prohibir la autoconversión de los datos estableciendo el parámetro `autoConvert` en `false`.  
  
<a name="Working_with_Data_Objects"></a>   
## Trabajar con objetos de datos  
 En esta sección se describen las técnicas comunes para crear objetos de datos y trabajar con ellos.  
  
### Crear nuevos objetos de datos  
 La clase <xref:System.Windows.DataObject> proporciona varios constructores sobrecargados que facilitan la operación de rellenar una nueva instancia de <xref:System.Windows.DataObject> con un solo par de datos\/formato de datos.  
  
 En el ejemplo de código siguiente se crea un nuevo objeto de datos y se utiliza uno de los constructores sobrecargados <xref:System.Windows.DataObject.%23ctor%2A>\(<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>\) para inicializar el objeto de datos con una cadena y un formato de datos especificado.  En este caso, el formato de los datos lo especifica una cadena; la clase <xref:System.Windows.DataFormats> proporciona un conjunto de cadenas de tipo predefinidas.  Se permite la autoconversión de los datos almacenados de forma predeterminada.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Para obtener más ejemplos de código en los que se crean objetos de datos, consulte [Crear un objeto de datos](../../../../docs/framework/wpf/advanced/how-to-create-a-data-object.md).  
  
### Almacenar datos en varios formatos  
 Un mismo objeto de datos puede almacenar los datos en varios formatos.  El uso estratégico de varios formatos de datos dentro de un mismo objeto de datos hace que el objeto de datos se pueda utilizar potencialmente por una mayor diversidad de destinos de colocación que si únicamente fuese posible representar un formato de datos.  En general, tenga en cuenta que un origen de arrastre debe ser válido con respecto a los formatos de datos los destinos potenciales pueden utilizar.  
  
 En el ejemplo siguiente se muestra cómo utilizar el método <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> para agregar datos a un objeto de datos en varios formatos.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### Consultar los formatos disponibles en un objeto de datos  
 Dado que un mismo objeto de datos puede contener un número arbitrario de formatos de datos, los objetos de datos incluyen medios para recuperar una lista de los formatos de datos disponibles.  
  
 En el ejemplo de código siguiente se utiliza la sobrecarga de <xref:System.Windows.DataObject.GetFormats%2A> para obtener una matriz de cadenas que representan todos los formatos de datos disponibles en un objeto de datos \(tanto nativos como por autoconversión\).  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Para obtener más ejemplos de código en que se consultan los formatos de datos disponibles en un objeto de datos, consulte [Mostrar los formatos de datos en un objeto de datos](../../../../docs/framework/wpf/advanced/how-to-list-the-data-formats-in-a-data-object.md).  Para obtener ejemplos sobre cómo consultar un objeto de datos para comprobar si está presente en él un formato de datos determinado, consulte [Determinar si un formato de datos está presente en un objeto de datos](../../../../docs/framework/wpf/advanced/how-to-determine-if-a-data-format-is-present-in-a-data-object.md).  
  
### Recuperar datos de un objeto de datos  
 Para recuperar los datos de un objeto de datos en un formato concreto basta con llamar a uno de los métodos <xref:System.Windows.DataObject.GetData%2A> y especificar el formato de datos deseado.  Uno de los métodos <xref:System.Windows.DataObject.GetDataPresent%2A> se puede utilizar para comprobar la presencia de un formato de datos determinado.  <xref:System.Windows.DataObject.GetData%2A> devuelve los datos de un <xref:System.Object>; según cuál sea el formato de datos, este objeto se puede convertir a un contenedor específico del tipo.  
  
 En el ejemplo de código siguiente se utiliza la sobrecarga de <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> para comprobar si está disponible un formato de datos concreto \(nativo o por autoconversión\).  Si el formato especificado está disponible, entonces el ejemplo recupera los datos mediante el método <xref:System.Windows.DataObject.GetData%28System.String%29>.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Para obtener más ejemplos de código en que se recuperan datos de un objeto de datos, consulte [Recuperar datos en un formato concreto](../../../../docs/framework/wpf/advanced/how-to-retrieve-data-in-a-particular-data-format.md).  
  
### Quitar datos de un objeto de datos  
 No es posible quitar directamente los datos de un objeto de datos.  Para quitar de manera efectiva los datos de un objeto de datos, siga estos pasos:  
  
1.  Cree un nuevo objeto de datos que únicamente contendrá los datos que desea conservar.  
  
2.  "Copie" los datos deseados de del objeto de datos anterior al nuevo.  Para copiar los datos, utilice uno de los métodos <xref:System.Windows.DataObject.GetData%2A> para recuperar una clase <xref:System.Object> que contiene los datos sin procesar y, a continuación, utilice uno de los métodos <xref:System.Windows.DataObject.SetData%2A> para agregar los datos al nuevo objeto de datos.  
  
3.  Reemplace el objeto de datos anterior por el nuevo.  
  
> [!NOTE]
>  Los métodos <xref:System.Windows.DataObject.SetData%2A> únicamente agregan datos a un objeto de datos; no reemplazan esos datos, aunque los datos y el formato de datos sean exactamente iguales que en una llamada anterior.  Al llamar dos veces a <xref:System.Windows.DataObject.SetData%2A> para obtener los mismos datos y formato de datos hará que el par de datos\/formato de datos esté presente dos veces en el objeto de datos.
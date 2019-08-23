---
title: Datos y objetos de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data transfer [WPF], drag-and-drop
- DataFormats class [WPF]
- DataObject class [WPF]
ms.assetid: 5967d557-1867-420f-a524-ae3af78402da
ms.openlocfilehash: 4b948a64a14df7ea79b54b810f734056d57ef406
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964867"
---
# <a name="data-and-data-objects"></a>Datos y objetos de datos
Los datos que se transfieren como parte de una operación de arrastrar y colocar se almacenan en un objeto de datos.  Conceptualmente, un objeto de datos consta de uno o varios de los siguientes pares:  
  
- <xref:System.Object> Que contiene los datos reales.  
  
- Identificador de formato de datos correspondiente.  
  
 Los propios datos pueden constar de cualquier elemento que se pueda representar como <xref:System.Object>base.  El formato de datos correspondiente es una cadena <xref:System.Type> o que proporciona una sugerencia sobre el formato de los datos.  Los objetos de datos admiten el hospedaje de varios pares de formato de datos y datos; Esto permite a un único objeto de datos proporcionar datos en varios formatos.  
  
<a name="Data_and_Data_Objects"></a>   
## <a name="data-objects"></a>Objetos de datos  
 Todos los objetos de datos deben <xref:System.Windows.IDataObject> implementar la interfaz, que proporciona el siguiente conjunto estándar de métodos que habilitan y facilitan la transferencia de datos.  
  
|Método|Resumen|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Recupera un objeto de datos en un formato de datos especificado.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Comprueba si los datos están disponibles en un formato especificado o se pueden convertir a él.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Devuelve una lista de formatos en los que se almacenan los datos de este objeto de datos o a los que se puede convertir.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Almacena los datos especificados en este objeto de datos.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]proporciona una implementación básica de <xref:System.Windows.IDataObject> en la <xref:System.Windows.DataObject> clase. La clase <xref:System.Windows.DataObject> stock es suficiente para muchos escenarios comunes de transferencia de datos.  
  
 Hay varios formatos predefinidos, como mapa de bits, CSV, archivo, HTML, RTF, cadena, texto y audio. Para obtener información sobre los formatos de datos predefinidos que se <xref:System.Windows.DataFormats> proporcionan con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea el tema de referencia de la clase.  
  
 Los objetos de datos suelen incluir una utilidad para convertir automáticamente los datos almacenados en un formato a un formato diferente durante la extracción de datos. Esta instalación se conoce como conversión automática. Al consultar los formatos de datos disponibles en un objeto de datos, se pueden filtrar los formatos de datos de conversión automática de los formatos de datos <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> nativos <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> llamando al método o y `autoConvert` especificando `false`el parámetro como.  Al agregar datos a un objeto de datos con <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> el método, se puede prohibir la conversión automática de datos estableciendo `autoConvert` el parámetro `false`en.  
  
<a name="Working_with_Data_Objects"></a>   
## <a name="working-with-data-objects"></a>Trabajar con objetos de datos  
 En esta sección se describen técnicas comunes para crear y trabajar con objetos de datos.  
  
### <a name="creating-new-data-objects"></a>Crear nuevos objetos de datos  
 La <xref:System.Windows.DataObject> clase proporciona varios constructores sobrecargados que facilitan el rellenado de una nueva <xref:System.Windows.DataObject> instancia con un solo par de datos y formato de datos.  
  
 En el código de ejemplo siguiente se crea un nuevo objeto de datos y se usa uno de los <xref:System.Windows.DataObject.%23ctor%2A>constructores sobrecargados (<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>) para inicializar el objeto de datos con una cadena y un formato de datos especificado.  En este caso, el formato de datos se especifica mediante una cadena; la <xref:System.Windows.DataFormats> clase proporciona un conjunto de cadenas de tipo predefinidas. De forma predeterminada, se permite la conversión automática de los datos almacenados.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Para obtener más ejemplos de código que crea un objeto de datos, vea [crear un objeto de datos](how-to-create-a-data-object.md).  
  
### <a name="storing-data-in-multiple-formats"></a>Almacenar datos en varios formatos  
 Un solo objeto de datos puede almacenar datos en varios formatos.   El uso estratégico de varios formatos de datos dentro de un único objeto de datos hace que el objeto de datos sea consumible por una variedad más amplia de destinos de colocación que si solo se pudiera representar un formato de datos único.  Tenga en cuenta que, en general, un origen de arrastre debe ser independiente de los formatos de datos que son consumibles por posibles destinos de colocación.  
  
 En el ejemplo siguiente se muestra cómo utilizar <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> el método para agregar datos a un objeto de datos en varios formatos.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>Consultar los formatos disponibles en un objeto de datos  
 Dado que un único objeto de datos puede contener un número arbitrario de formatos de datos, los objetos de datos incluyen funciones para recuperar una lista de formatos de datos disponibles.  
  
 En el ejemplo de código siguiente <xref:System.Windows.DataObject.GetFormats%2A> se usa la sobrecarga para obtener una matriz de cadenas que denotan todos los formatos de datos disponibles en un objeto de datos (tanto nativos como por conversión automática).  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Para obtener más ejemplos de código que consulta un objeto de datos para ver los formatos de datos disponibles, vea [enumerar los formatos de datos en un objeto de datos](how-to-list-the-data-formats-in-a-data-object.md).  Para obtener ejemplos de cómo consultar un objeto de datos para ver la presencia de un formato de datos determinado, vea [determinar si un formato de datos está presente en un objeto de datos](how-to-determine-if-a-data-format-is-present-in-a-data-object.md).  
  
### <a name="retrieving-data-from-a-data-object"></a>Recuperar datos de un objeto de datos  
 La recuperación de datos de un objeto de datos en un formato determinado simplemente implica llamar a <xref:System.Windows.DataObject.GetData%2A> uno de los métodos y especificar el formato de datos deseado.  Se puede usar <xref:System.Windows.DataObject.GetDataPresent%2A> uno de los métodos para comprobar la presencia de un formato de datos determinado.  <xref:System.Windows.DataObject.GetData%2A>Devuelve los datos de un <xref:System.Object>objeto; dependiendo del formato de los datos, este objeto se puede convertir en un contenedor específico del tipo.  
  
 En el ejemplo de código siguiente <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> se usa la sobrecarga para comprobar si un formato de datos especificado está disponible (nativo o por conversión automática). Si el formato especificado está disponible, en el ejemplo se recuperan los datos mediante <xref:System.Windows.DataObject.GetData%28System.String%29> el método.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Para obtener más ejemplos de código que recupera datos de un objeto de datos, vea [recuperar datos en un formato de datos determinado](how-to-retrieve-data-in-a-particular-data-format.md).  
  
### <a name="removing-data-from-a-data-object"></a>Quitar datos de un objeto de datos  
 Los datos no se pueden quitar directamente de un objeto de datos.  Para quitar eficazmente los datos de un objeto de datos, siga estos pasos:  
  
1. Cree un nuevo objeto de datos que contendrá solo los datos que desea conservar.  
  
2. "Copiar" los datos deseados del antiguo objeto de datos al nuevo objeto de datos.  Para copiar los datos, use uno de los <xref:System.Windows.DataObject.GetData%2A> métodos para recuperar un <xref:System.Object> que contiene los datos sin procesar y, a continuación, use <xref:System.Windows.DataObject.SetData%2A> uno de los métodos para agregar los datos al nuevo objeto de datos.  
  
3. Reemplace el objeto de datos anterior por el nuevo.  
  
> [!NOTE]
> Los <xref:System.Windows.DataObject.SetData%2A> métodos solo agregan datos a un objeto de datos; no reemplazan los datos, incluso si el formato de datos y datos es exactamente el mismo que el de una llamada anterior. La <xref:System.Windows.DataObject.SetData%2A> llamada a dos veces para los mismos datos y formato de datos dará lugar a que el formato de datos o datos esté presente dos veces en el objeto de datos.

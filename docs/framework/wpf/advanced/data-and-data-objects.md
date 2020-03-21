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
ms.openlocfilehash: 532c254f997da183b073ddc9e00b4364ecfcd739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186343"
---
# <a name="data-and-data-objects"></a>Datos y objetos de datos
Los datos que se transfieren como parte de una operación de arrastrar y colocar se almacenan en un objeto de datos.  Conceptualmente, un objeto de datos consta de uno o varios de los siguientes pares:  
  
- Un <xref:System.Object> que contiene los datos reales.  
  
- Identificador de formato de datos correspondiente.  
  
 Los datos en sí pueden consistir en <xref:System.Object>cualquier cosa que se pueda representar como una base.  El formato de datos <xref:System.Type> correspondiente es una cadena o que proporciona una sugerencia sobre en qué formato se encuentra los datos.  Los objetos de datos admiten el hospedaje de varios pares de formato de datos/datos; esto permite que un único objeto de datos proporcione datos en varios formatos.  
  
<a name="Data_and_Data_Objects"></a>
## <a name="data-objects"></a>Objetos de datos  
 Todos los objetos <xref:System.Windows.IDataObject> de datos deben implementar la interfaz, que proporciona el siguiente conjunto estándar de métodos que habilitan y facilitan la transferencia de datos.  
  
|Método|Resumen|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Recupera un objeto de datos en un formato de datos especificado.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Comprueba si los datos están disponibles en un formato especificado o se pueden convertir a él.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Devuelve una lista de formatos en los que se almacenan los datos de este objeto de datos; o bien, a los que se pueden convertir.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Almacena los datos especificados en este objeto de datos.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]proporciona una implementación básica de <xref:System.Windows.IDataObject> la <xref:System.Windows.DataObject> clase. La <xref:System.Windows.DataObject> clase de stock es suficiente para muchos escenarios comunes de transferencia de datos.  
  
 Hay varios formatos predefinidos, como mapa de bits, CSV, archivo, HTML, RTF, cadena, texto y audio. Para obtener información acerca de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]los formatos de datos predefinidos proporcionados con , consulte el <xref:System.Windows.DataFormats> tema de referencia de clase.  
  
 Los objetos de datos suelen incluir una función para convertir automáticamente los datos almacenados en un formato a un formato diferente mientras se extraen datos; esta instalación se conoce como auto-conversión. Al consultar los formatos de datos disponibles en un objeto de datos, los <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> formatos de `autoConvert` datos `false`autoconvertibles se pueden filtrar desde formatos de datos nativos llamando al método o y especificando el parámetro como .  Al agregar datos a un <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> objeto de datos con el método, `autoConvert` se `false`puede prohibir la conversión automática de datos estableciendo el parámetro en .  
  
<a name="Working_with_Data_Objects"></a>
## <a name="working-with-data-objects"></a>Trabajar con objetos de datos  
 En esta sección se describen las técnicas comunes para crear y trabajar con objetos de datos.  
  
### <a name="creating-new-data-objects"></a>Creación de nuevos objetos de datos  
 La <xref:System.Windows.DataObject> clase proporciona varios constructores sobrecargados que <xref:System.Windows.DataObject> facilitan rellenar una nueva instancia con un único par de formato de datos/datos.  
  
 El siguiente código de ejemplo crea un nuevo objeto <xref:System.Windows.DataObject.%23ctor%2A>de<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>datos y utiliza uno de los constructores sobrecargados ( ) para inicializar el objeto de datos con una cadena y un formato de datos especificado.  En este caso, el formato de datos se especifica mediante una cadena; la <xref:System.Windows.DataFormats> clase proporciona un conjunto de cadenas de tipo predefinidas. La conversión automática de los datos almacenados está permitida de forma predeterminada.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Para obtener más ejemplos de código que crea un objeto de datos, vea [Crear un objeto](how-to-create-a-data-object.md)de datos .  
  
### <a name="storing-data-in-multiple-formats"></a>Almacenamiento de datos en múltiples formatos  
 Un único objeto de datos puede almacenar datos en varios formatos.   El uso estratégico de varios formatos de datos dentro de un único objeto de datos potencialmente hace que el objeto de datos sea consumible por una variedad más amplia de destinos de colocación que si solo se pudiera representar un único formato de datos.  Tenga en cuenta que, en general, un origen de arrastre debe ser independiente sobre los formatos de datos que son consumibles por posibles destinos de colocación.  
  
 En el ejemplo siguiente <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> se muestra cómo utilizar el método para agregar datos a un objeto de datos en varios formatos.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>Consulta de un objeto de datos para los formatos disponibles  
 Dado que un único objeto de datos puede contener un número arbitrario de formatos de datos, los objetos de datos incluyen facilidades para recuperar una lista de formatos de datos disponibles.  
  
 El siguiente código <xref:System.Windows.DataObject.GetFormats%2A> de ejemplo utiliza la sobrecarga para obtener una matriz de cadenas que denotan todos los formatos de datos disponibles en un objeto de datos (tanto nativo como por conversión automática).  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Para obtener más ejemplos de código que consulta un objeto de datos para los formatos de datos disponibles, vea [Listar los formatos](how-to-list-the-data-formats-in-a-data-object.md)de datos en un objeto de datos .  Para obtener ejemplos de consulta de un objeto de datos para la presencia de un formato de datos determinado, vea Determinar si un formato de datos [está presente en un objeto](how-to-determine-if-a-data-format-is-present-in-a-data-object.md)de datos .  
  
### <a name="retrieving-data-from-a-data-object"></a>Recuperación de datos de un objeto de datos  
 Recuperar datos de un objeto de datos en un <xref:System.Windows.DataObject.GetData%2A> formato determinado simplemente implica llamar a uno de los métodos y especificar el formato de datos deseado.  Uno de <xref:System.Windows.DataObject.GetDataPresent%2A> los métodos se puede utilizar para comprobar la presencia de un formato de datos determinado.  <xref:System.Windows.DataObject.GetData%2A>devuelve los datos <xref:System.Object>en un ; dependiendo del formato de datos, este objeto se puede convertir en un contenedor específico de tipo.  
  
 El siguiente código <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> de ejemplo utiliza la sobrecarga para comprobar si hay un formato de datos especificado disponible (nativo o por conversión automática). Si el formato especificado está disponible, el ejemplo <xref:System.Windows.DataObject.GetData%28System.String%29> recupera los datos mediante el método.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Para obtener más ejemplos de código que recupera datos de un objeto de datos, vea [Recuperar datos en un formato](how-to-retrieve-data-in-a-particular-data-format.md)de datos determinado .  
  
### <a name="removing-data-from-a-data-object"></a>Eliminación de datos de un objeto de datos  
 Los datos no se pueden quitar directamente de un objeto de datos.  Para eliminar eficazmente los datos de un objeto de datos, siga estos pasos:  
  
1. Cree un nuevo objeto de datos que contendrá solo los datos que desea conservar.  
  
2. "Copiar" los datos deseados del objeto de datos antiguo al nuevo objeto de datos.  Para copiar los datos, <xref:System.Windows.DataObject.GetData%2A> utilice uno <xref:System.Object> de los métodos para recuperar un <xref:System.Windows.DataObject.SetData%2A> que contiene los datos sin procesar y, a continuación, utilice uno de los métodos para agregar los datos al nuevo objeto de datos.  
  
3. Reemplace el objeto de datos antiguo por el nuevo.  
  
> [!NOTE]
> Los <xref:System.Windows.DataObject.SetData%2A> métodos solo agregan datos a un objeto de datos; no reemplazan los datos, incluso si los datos y el formato de datos son exactamente los mismos que una llamada anterior. Llamar <xref:System.Windows.DataObject.SetData%2A> dos veces para el mismo formato de datos y datos dará como resultado que el formato de datos/datos esté presente dos veces en el objeto de datos.

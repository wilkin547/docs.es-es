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
ms.openlocfilehash: 9dc195ece60739cf0c137a2893c9e9150e0d4d3f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312064"
---
# <a name="data-and-data-objects"></a>Datos y objetos de datos
Datos que se transfieren como parte de una operación de arrastrar y colocar se almacenan en un objeto de datos.  Conceptualmente, un objeto de datos consta de uno o varios de los siguientes pares:  
  
-   Un <xref:System.Object> que contiene los datos reales.  
  
-   Un identificador de formato de datos correspondiente.  
  
 Los datos en sí pueden constar de cualquier cosa que se puede representar como una base de <xref:System.Object>.  El formato de datos correspondiente es una cadena o <xref:System.Type> que proporciona una sugerencia sobre el formato de los datos se encuentra en.  Objetos de datos admiten el hospedaje de varios pares de formato de datos/datos; Esto permite un único objeto de datos proporcionar datos en varios formatos.  
  
<a name="Data_and_Data_Objects"></a>   
## <a name="data-objects"></a>Objetos de datos  
 Todos los objetos de datos deben implementar la <xref:System.Windows.IDataObject> interfaz, que proporciona el siguiente conjunto estándar de métodos que habilitan y facilitar la transferencia de datos.  
  
|Método|Resumen|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Recupera un objeto de datos en un formato de datos especificado.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Comprueba si están disponibles en los datos, o pueden convertirse en un formato especificado.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Devuelve una lista de formatos que se almacenarán en los datos de este objeto de datos, o pueden convertirse en.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Almacena los datos especificados en este objeto de datos.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Proporciona una implementación básica de <xref:System.Windows.IDataObject> en el <xref:System.Windows.DataObject> clase. Las existencias <xref:System.Windows.DataObject> clase es suficiente para muchos escenarios comunes de transferencia de datos.  
  
 Hay varios formatos predefinidos, como mapa de bits, CSV, archivo, HTML, RTF, cadena, texto y audio. Para obtener información acerca de los formatos de datos predefinidos proporcionados con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte el <xref:System.Windows.DataFormats> tema de referencia de clase.  
  
 Objetos de datos suelen incluyen una función para convertir automáticamente los datos almacenados en un formato a un formato diferente al extraer los datos; Esta función se conoce como conversión automática. Al consultar los formatos de datos disponibles en un objeto de datos, formatos de datos automática se pueden filtrar de formatos de datos nativos mediante una llamada a la <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> o <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> método y especificando el `autoConvert` parámetro como `false`.  Al agregar datos a un objeto de datos con el <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> puede prohibirse el método, la conversión automática de datos estableciendo el `autoConvert` parámetro `false`.  
  
<a name="Working_with_Data_Objects"></a>   
## <a name="working-with-data-objects"></a>Trabajar con objetos de datos  
 Esta sección describen las técnicas comunes para crear y trabajar con objetos de datos.  
  
### <a name="creating-new-data-objects"></a>Crear nuevos objetos de datos  
 El <xref:System.Windows.DataObject> clase proporciona varios constructores sobrecargados que facilitan el relleno de un nuevo <xref:System.Windows.DataObject> instancia con un par de formato de datos único.  
  
 Ejemplo de código siguiente crea un nuevo objeto de datos y utiliza uno de los constructores sobrecargados <xref:System.Windows.DataObject.%23ctor%2A>(<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>) para inicializar el objeto de datos con una cadena y un formato de datos especificado.  En este caso, se especifica el formato de datos mediante una cadena; la <xref:System.Windows.DataFormats> clase proporciona un conjunto de cadenas de tipo predefinidas. Se permite la conversión automática de los datos almacenados de forma predeterminada.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Para obtener más ejemplos de código que crea un objeto de datos, vea [crear un objeto de datos](how-to-create-a-data-object.md).  
  
### <a name="storing-data-in-multiple-formats"></a>Almacenamiento de datos en varios formatos  
 Un único objeto de datos es capaz de almacenar datos en varios formatos.   Uso estratégico de varios formatos de datos dentro de un único objeto de datos potencialmente hace que el objeto de datos compatible con una amplia variedad de destinos de colocación que si solo se puede representar un solo formato de datos.  Tenga en cuenta, en general, un origen de arrastre debe ser independiente sobre los formatos de datos que son consumibles por posibles destinos de colocación.  
  
 El ejemplo siguiente muestra cómo usar el <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> para agregar datos a un objeto de datos en varios formatos.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>Consultando un objeto de datos para los formatos disponibles  
 Dado que un objeto de datos solo puede contener un número arbitrario de formatos de datos, objetos de datos incluyen medios para recuperar una lista de formatos de datos disponibles.  
  
 El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetFormats%2A> sobrecarga para obtener una matriz de cadenas que denotan todos los formatos de datos disponibles en un objeto de datos (nativo y mediante la conversión automática).  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Para obtener más ejemplos de código que realiza consultas en un objeto de datos para los formatos de datos disponibles, consulte [mostrar los formatos de datos en un objeto de datos](how-to-list-the-data-formats-in-a-data-object.md).  Para obtener ejemplos de la consulta de un objeto de datos para la presencia de un formato concreto, vea [determinar si un formato de datos está presente en un objeto de datos](how-to-determine-if-a-data-format-is-present-in-a-data-object.md).  
  
### <a name="retrieving-data-from-a-data-object"></a>Recuperación de datos de un objeto de datos  
 Recuperar datos de un objeto de datos en un formato determinado, basta con llamar a uno de los <xref:System.Windows.DataObject.GetData%2A> métodos y especificar el formato de datos que desee.  Uno de los <xref:System.Windows.DataObject.GetDataPresent%2A> métodos pueden usarse para comprobar la presencia de un formato concreto.  <xref:System.Windows.DataObject.GetData%2A> Devuelve los datos en un <xref:System.Object>; según el formato de datos, este objeto puede convertirse en un contenedor específico del tipo.  
  
 El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> sobrecarga para comprobar si un formato de datos especificado está disponible (nativo o mediante la conversión automática). Si el formato especificado está disponible, el ejemplo recupera los datos mediante el <xref:System.Windows.DataObject.GetData%28System.String%29> método.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Para obtener más ejemplos de código que recupera datos de un objeto de datos, vea [recuperar datos en un formato de datos determinado](how-to-retrieve-data-in-a-particular-data-format.md).  
  
### <a name="removing-data-from-a-data-object"></a>Eliminación de datos de un objeto de datos  
 Datos no se puede quitar directamente desde un objeto de datos.  Para quitar eficazmente los datos de un objeto de datos, siga estos pasos:  
  
1. Cree un nuevo objeto de datos que contendrá solo los datos que desea conservar.  
  
2. "Copie" los datos deseados del objeto de datos anterior al nuevo objeto de datos.  Para copiar los datos, utilice uno de los <xref:System.Windows.DataObject.GetData%2A> métodos para recuperar un <xref:System.Object> que contiene los datos sin procesar y, a continuación, use uno de los <xref:System.Windows.DataObject.SetData%2A> métodos para agregar los datos al nuevo objeto de datos.  
  
3. Reemplace el objeto de datos antiguo con uno nuevo.  
  
> [!NOTE]
>  El <xref:System.Windows.DataObject.SetData%2A> métodos sólo agregan datos a un objeto de datos; no reemplazan los datos, incluso si los datos y el formato de datos son exactamente igual que una llamada anterior. Una llamada a <xref:System.Windows.DataObject.SetData%2A> dos veces para los mismos datos y formato dará como resultado el formato de datos/datos están presentes dos veces en el objeto de datos.

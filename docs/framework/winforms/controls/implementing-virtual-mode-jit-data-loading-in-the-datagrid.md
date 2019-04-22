---
title: Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: c2a052b9-423c-4ff7-91dc-d8c7c79345f6
ms.openlocfilehash: 641db19cc6493a20c9f9a34622f466e3623c32ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088657"
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms
Una razón para implementar el modo virtual en el <xref:System.Windows.Forms.DataGridView> control consiste en recuperar datos sólo según sea necesario. Esto se denomina *la carga de datos just-in-time*.  
  
 Si está trabajando con una tabla muy grande en una base de datos remota, por ejemplo, puede evitar retrasos de inicio por recuperar únicamente los datos que sean necesarios para mostrar y recuperar datos adicionales solo cuando el usuario desplaza las nuevas filas en la vista. Si los equipos cliente que ejecuta la aplicación tienen una cantidad limitada de memoria disponible para almacenar datos, también puede descartar los datos no usados al recuperar los nuevos valores de la base de datos.  
  
 Las secciones siguientes describen cómo usar un <xref:System.Windows.Forms.DataGridView> control con una caché just-in-time.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: Implementar el modo Virtual con la carga de datos Just-In-Time en el Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="the-form"></a>El formulario  
 El ejemplo de código siguiente define un formulario que contenga solo lectura <xref:System.Windows.Forms.DataGridView> control que interactúa con un `Cache` objeto a través de un <xref:System.Windows.Forms.DataGridView.CellValueNeeded> controlador de eventos. El `Cache` objeto administra los valores almacenados localmente y usa un `DataRetriever` objeto para recuperar valores de la tabla Orders de la base de datos de ejemplo Northwind. El `DataRetriever` objeto, que implementa el `IDataPageRetriever` interfaz requerida por el `Cache` de clases, también se usa para inicializar el <xref:System.Windows.Forms.DataGridView> controlar las filas y columnas.  
  
 El `IDataPageRetriever`, `DataRetriever`, y `Cache` tipos se describen más adelante en este tema.  
  
> [!NOTE]
>  Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>La interfaz IDataPageRetriever  
 En el ejemplo de código siguiente se define la `IDataPageRetriever` interfaz, que se implementa mediante el `DataRetriever` clase. El único método que se declaran en esta interfaz es la `SupplyPageOfData` método, que requiere un índice de fila inicial y un recuento del número de filas en una sola página de datos. Estos valores se usan por el implementador para recuperar un subconjunto de datos de un origen de datos.  
  
 Un `Cache` objeto usa una implementación de esta interfaz durante la construcción para cargar dos páginas iniciales de datos. Cada vez que un valor que no es necesario, la memoria caché se descarta una de estas páginas y solicita una nueva página que contiene el valor de la `IDataPageRetriever`.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>La clase DataRetriever  
 En el ejemplo de código siguiente se define la `DataRetriever` clase que implementa el `IDataPageRetriever` interfaz para recuperar las páginas de datos desde un servidor. El `DataRetriever` también proporciona la clase `Columns` y `RowCount` propiedades, que el <xref:System.Windows.Forms.DataGridView> control usa para crear las columnas necesarias y para agregar el número adecuado de filas vacías para los <xref:System.Windows.Forms.DataGridView.Rows%2A> colección. Agregar filas vacías es necesario para que el control se comporte como si tuviera todos los datos de la tabla. Esto significa que el cuadro de desplazamiento en la barra de desplazamiento tienen el tamaño adecuado y el usuario podrá tener acceso a cualquier fila de la tabla. Las filas se rellenan mediante la <xref:System.Windows.Forms.DataGridView.CellValueNeeded> controlador de eventos sólo cuando se desplazan en la vista.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>La clase Cache  
 En el ejemplo de código siguiente se define la `Cache` (clase), que administra dos páginas de datos que se rellenan a través de un `IDataPageRetriever` implementación. El `Cache` clase define el interior `DataPage` estructura, que contiene un <xref:System.Data.DataTable> para almacenar los valores en una memoria caché única página y que calcula la fila de índices que representan los límites superiores e inferiores de la página.  
  
 La `Cache` clase carga dos páginas de datos en tiempo de construcción. Cada vez que el <xref:System.Windows.Forms.DataGridView.CellValueNeeded> evento solicita un valor, el `Cache` objeto determina si el valor está disponible en uno de sus dos páginas y, si es así, lo devuelve. Si el valor no está disponible localmente, el `Cache` objeto determina cuál de sus dos páginas más alejado de las filas mostradas actualmente y reemplaza la página con uno nuevo que contiene el valor solicitado, que luego se devuelve.  
  
 Suponiendo que el número de filas de una página de datos es el mismo que el número de filas que se pueden mostrar en pantalla a la vez, este modelo permite a los usuarios paginar a través de la tabla devolver de forma eficaz a la página de vista más recientemente.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>Consideraciones adicionales  
 Los ejemplos de código anteriores se proporcionan como una demostración de la carga de datos just-in-time. Deberá modificar el código para sus propias necesidades lograr la máxima eficiencia. Como mínimo, deberá elegir un valor adecuado para el número de filas por página de datos en la memoria caché. Este valor se pasa a la `Cache` constructor. El número de filas por página debe ser no menor que el número de filas que se pueden mostrar simultáneamente en sus <xref:System.Windows.Forms.DataGridView> control.  
  
 Para obtener mejores resultados, deberá llevar a cabo las pruebas de rendimiento y pruebas de uso para determinar los requisitos del sistema y los usuarios. Varios factores que debe tomar en consideración incluyen la cantidad de memoria en los equipos cliente que ejecutan la aplicación, el ancho de banda disponible de la conexión de red utilizada y la latencia del servidor utilizado. El ancho de banda y latencia deben determinarse en los momentos de uso máximo.  
  
 Para mejorar el rendimiento del desplazamiento de la aplicación, puede aumentar la cantidad de datos almacenados localmente. Sin embargo, para mejorar el tiempo de inicio, debe evitar cargar inicialmente muchos datos. Es posible que desee modificar el `Cache` clase para aumentar el número de páginas de datos que puede almacenar. Uso de más páginas de datos puede mejorar la eficacia de desplazamiento, pero deberá determinar el número ideal de las filas de una página de datos, según el ancho de banda disponible y la latencia del servidor. Con las páginas más pequeñas, el servidor se accederá con mayor frecuencia, pero tardará menos tiempo en devolver los datos solicitados. Si la latencia es más un problema que el ancho de banda, desea utilizar las páginas de datos más grandes.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Ajuste del rendimiento del control DataGridView en Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Modo virtual del control DataGridView de Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Tutorial: Implementar el modo Virtual en el Control DataGridView de formularios de Windows](implementing-virtual-mode-wf-datagridview-control.md)
- [Cómo: Implementar el modo Virtual con la carga de datos Just-In-Time en el Control DataGridView de Windows Forms](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)

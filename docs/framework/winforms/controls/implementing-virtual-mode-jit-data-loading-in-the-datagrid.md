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
ms.openlocfilehash: fa40f1657a433f5f4ade3de25648ca04c37dfa67
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962602"
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms
Una razón para implementar el modo virtual en <xref:System.Windows.Forms.DataGridView> el control es recuperar datos solo cuando sea necesario. Esto se denomina *carga de datos Just-in-Time*.  
  
 Si está trabajando con una tabla muy grande en una base de datos remota, por ejemplo, puede que desee evitar retrasos de inicio recuperando únicamente los datos necesarios para mostrar y recuperar datos adicionales solo cuando el usuario desplace nuevas filas a la vista. Si los equipos cliente que ejecutan la aplicación tienen una cantidad limitada de memoria disponible para almacenar los datos, puede que también desee descartar los datos no usados al recuperar nuevos valores de la base de datos.  
  
 En las secciones siguientes se describe cómo utilizar <xref:System.Windows.Forms.DataGridView> un control con una caché Just-in-Time.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: Implemente el modo virtual con la carga de datos Just-in-Time en](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)el control DataGridView Windows Forms.  
  
## <a name="the-form"></a>El formulario  
 En el ejemplo de código siguiente se define un formulario que contiene <xref:System.Windows.Forms.DataGridView> un control de solo lectura que `Cache` interactúa con un <xref:System.Windows.Forms.DataGridView.CellValueNeeded> objeto a través de un controlador de eventos. El `Cache` objeto administra los valores almacenados localmente y usa un `DataRetriever` objeto para recuperar los valores de la tabla Orders de la base de datos Northwind de ejemplo. El `DataRetriever` objeto, que implementa la `IDataPageRetriever` interfaz requerida por la `Cache` clase, también se usa para inicializar las <xref:System.Windows.Forms.DataGridView> filas y las columnas del control.  
  
 Los `IDataPageRetriever`tipos `DataRetriever`, y`Cache` se describen más adelante en este tema.  
  
> [!NOTE]
> Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>La interfaz IDataPageRetriever  
 En el ejemplo de código siguiente `IDataPageRetriever` se define la interfaz, que se `DataRetriever` implementa mediante la clase. El único método declarado en esta interfaz es el `SupplyPageOfData` método, que requiere un índice de fila inicial y un recuento del número de filas en una sola página de datos. El implementador utiliza estos valores para recuperar un subconjunto de datos de un origen de datos.  
  
 Un `Cache` objeto utiliza una implementación de esta interfaz durante la construcción para cargar dos páginas iniciales de datos. Siempre que se necesita un valor no almacenado en caché, la memoria caché descarta una de estas páginas y solicita una nueva página que contiene el valor `IDataPageRetriever`de.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>La clase del recuperador  
 En el ejemplo de código siguiente `DataRetriever` se define la clase, que `IDataPageRetriever` implementa la interfaz para recuperar páginas de datos de un servidor. La `DataRetriever` clase también proporciona `Columns` las `RowCount` propiedades y, que <xref:System.Windows.Forms.DataGridView> el control usa para crear las columnas necesarias y para agregar el número adecuado de filas vacías <xref:System.Windows.Forms.DataGridView.Rows%2A> a la colección. Es necesario agregar filas vacías para que el control se comporte como si tuviera todos los datos de la tabla. Esto significa que el cuadro de desplazamiento de la barra de desplazamiento tendrá el tamaño adecuado y el usuario podrá tener acceso a cualquier fila de la tabla. El controlador de <xref:System.Windows.Forms.DataGridView.CellValueNeeded> eventos rellena las filas solo cuando se desplazan a la vista.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>La clase cache  
 En el ejemplo de código siguiente `Cache` se define la clase, que administra dos páginas de datos `IDataPageRetriever` rellenados a través de una implementación de. La `Cache` clase define una estructura `DataPage` interna, que contiene un <xref:System.Data.DataTable> para almacenar los valores en una sola página de caché y que calcula los índices de fila que representan los límites superior e inferior de la página.  
  
 La `Cache` clase carga dos páginas de datos en el momento de la construcción. Siempre que <xref:System.Windows.Forms.DataGridView.CellValueNeeded> el evento solicita un valor, `Cache` el objeto determina si el valor está disponible en una de sus dos páginas y, en caso afirmativo, lo devuelve. Si el valor no está disponible localmente, el `Cache` objeto determina cuál de sus dos páginas es más alejada de las filas mostradas actualmente y reemplaza la página por una nueva que contiene el valor solicitado, que después devuelve.  
  
 Suponiendo que el número de filas de una página de datos es el mismo que el número de filas que se pueden mostrar en la pantalla al mismo tiempo, este modelo permite a los usuarios paginar la tabla para volver a la página que se vio más recientemente.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>Consideraciones adicionales  
 Los ejemplos de código anteriores se proporcionan como demostración de la carga de datos Just-in-Time. Tendrá que modificar el código para sus propias necesidades para lograr la máxima eficacia. Como mínimo, tendrá que elegir un valor adecuado para el número de filas por página de datos en la memoria caché. Este valor se pasa al `Cache` constructor. El número de filas por página no debe ser menor que el número de filas que se pueden mostrar simultáneamente en el <xref:System.Windows.Forms.DataGridView> control.  
  
 Para obtener los mejores resultados, tendrá que realizar pruebas de rendimiento y pruebas de facilidad de uso para determinar los requisitos del sistema y de los usuarios. Entre los factores que debe tener en cuenta se incluyen la cantidad de memoria en los equipos cliente que ejecutan la aplicación, el ancho de banda disponible de la conexión de red usada y la latencia del servidor utilizado. El ancho de banda y la latencia deben determinarse a horas de uso máximo.  
  
 Para mejorar el rendimiento del desplazamiento de la aplicación, puede aumentar la cantidad de datos almacenados localmente. Sin embargo, para mejorar el tiempo de inicio, debe evitar cargar inicialmente demasiados datos. Puede que desee modificar la `Cache` clase para aumentar el número de páginas de datos que puede almacenar. El uso de más páginas de datos puede mejorar la eficacia del desplazamiento, pero tendrá que determinar el número ideal de filas en una página de datos, en función del ancho de banda disponible y de la latencia del servidor. Con páginas más pequeñas, se tiene acceso al servidor con mayor frecuencia, pero se tardará menos tiempo en devolver los datos solicitados. Si la latencia es mayor que un problema que el ancho de banda, puede que desee usar páginas de datos más grandes.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Ajuste del rendimiento del control DataGridView en Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Modo virtual del control DataGridView de Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Tutorial: Implementar el modo virtual en el control DataGridView Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
- [Cómo: Implementar el modo virtual con la carga de datos Just-in-Time en el control DataGridView Windows Forms](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)

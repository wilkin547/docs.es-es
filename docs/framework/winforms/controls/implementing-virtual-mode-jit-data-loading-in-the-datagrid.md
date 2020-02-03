---
title: Implementar el modo virtual con la carga de datos Just-in-Time en el control DataGridView
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
ms.openlocfilehash: 85c6877a9fc6a92752eb039da9d36e34811f8b77
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745068"
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms
Una razón para implementar el modo virtual en el control <xref:System.Windows.Forms.DataGridView> es recuperar los datos solo cuando sea necesario. Esto se denomina *carga de datos Just-in-Time*.  
  
 Si está trabajando con una tabla muy grande en una base de datos remota, por ejemplo, puede que desee evitar retrasos de inicio recuperando únicamente los datos necesarios para mostrar y recuperar datos adicionales solo cuando el usuario desplace nuevas filas a la vista. Si los equipos cliente que ejecutan la aplicación tienen una cantidad limitada de memoria disponible para almacenar los datos, puede que también desee descartar los datos no usados al recuperar nuevos valores de la base de datos.  
  
 En las secciones siguientes se describe cómo utilizar un control de <xref:System.Windows.Forms.DataGridView> con una caché Just-in-Time.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: implementar el modo virtual con la carga de datos Just-in-Time en el control DataGridView Windows Forms](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="the-form"></a>El formulario  
 En el ejemplo de código siguiente se define un formulario que contiene un control de <xref:System.Windows.Forms.DataGridView> de solo lectura que interactúa con un objeto `Cache` a través de un controlador de eventos <xref:System.Windows.Forms.DataGridView.CellValueNeeded>. El objeto `Cache` administra los valores almacenados localmente y utiliza un objeto `DataRetriever` para recuperar los valores de la tabla Orders de la base de datos Northwind de ejemplo. El objeto `DataRetriever`, que implementa la interfaz `IDataPageRetriever` requerida por la clase `Cache`, también se usa para inicializar las filas y columnas del control <xref:System.Windows.Forms.DataGridView>.  
  
 Los tipos `IDataPageRetriever`, `DataRetriever`y `Cache` se describen más adelante en este tema.  
  
> [!NOTE]
> Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>La interfaz IDataPageRetriever  
 En el ejemplo de código siguiente se define la interfaz `IDataPageRetriever`, implementada por la clase `DataRetriever`. El único método declarado en esta interfaz es el método `SupplyPageOfData`, que requiere un índice de fila inicial y un recuento del número de filas en una sola página de datos. El implementador utiliza estos valores para recuperar un subconjunto de datos de un origen de datos.  
  
 Un objeto `Cache` usa una implementación de esta interfaz durante la construcción para cargar dos páginas iniciales de datos. Siempre que se necesita un valor no almacenado en caché, la memoria caché descarta una de estas páginas y solicita una nueva página que contiene el valor de la `IDataPageRetriever`.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>La clase del recuperador  
 En el ejemplo de código siguiente se define la clase `DataRetriever`, que implementa la interfaz `IDataPageRetriever` para recuperar páginas de datos de un servidor. La clase `DataRetriever` también proporciona las propiedades `Columns` y `RowCount`, que el control <xref:System.Windows.Forms.DataGridView> utiliza para crear las columnas necesarias y para agregar el número adecuado de filas vacías a la colección <xref:System.Windows.Forms.DataGridView.Rows%2A>. Es necesario agregar filas vacías para que el control se comporte como si tuviera todos los datos de la tabla. Esto significa que el cuadro de desplazamiento de la barra de desplazamiento tendrá el tamaño adecuado y el usuario podrá tener acceso a cualquier fila de la tabla. El controlador de eventos <xref:System.Windows.Forms.DataGridView.CellValueNeeded> rellena las filas solo cuando se desplazan a la vista.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>La clase cache  
 En el ejemplo de código siguiente se define la clase `Cache`, que administra dos páginas de datos rellenadas a través de una implementación `IDataPageRetriever`. La clase `Cache` define una estructura de `DataPage` interna, que contiene un <xref:System.Data.DataTable> para almacenar los valores en una sola página de caché y que calcula los índices de fila que representan los límites superior e inferior de la página.  
  
 La clase `Cache` carga dos páginas de datos en el momento de la construcción. Cada vez que el evento de <xref:System.Windows.Forms.DataGridView.CellValueNeeded> solicita un valor, el objeto de `Cache` determina si el valor está disponible en una de sus dos páginas y, en caso afirmativo, lo devuelve. Si el valor no está disponible localmente, el objeto de `Cache` determina cuál de sus dos páginas es más alejada de las filas mostradas actualmente y reemplaza la página por una nueva que contiene el valor solicitado, que después devuelve.  
  
 Suponiendo que el número de filas de una página de datos es el mismo que el número de filas que se pueden mostrar en la pantalla al mismo tiempo, este modelo permite a los usuarios paginar la tabla para volver a la página que se vio más recientemente.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>Consideraciones adicionales  
 Los ejemplos de código anteriores se proporcionan como demostración de la carga de datos Just-in-Time. Tendrá que modificar el código para sus propias necesidades para lograr la máxima eficacia. Como mínimo, tendrá que elegir un valor adecuado para el número de filas por página de datos en la memoria caché. Este valor se pasa al constructor de `Cache`. El número de filas por página no debe ser menor que el número de filas que se pueden mostrar simultáneamente en el control de <xref:System.Windows.Forms.DataGridView>.  
  
 Para obtener los mejores resultados, tendrá que realizar pruebas de rendimiento y pruebas de facilidad de uso para determinar los requisitos del sistema y de los usuarios. Entre los factores que debe tener en cuenta se incluyen la cantidad de memoria en los equipos cliente que ejecutan la aplicación, el ancho de banda disponible de la conexión de red usada y la latencia del servidor utilizado. El ancho de banda y la latencia deben determinarse a horas de uso máximo.  
  
 Para mejorar el rendimiento del desplazamiento de la aplicación, puede aumentar la cantidad de datos almacenados localmente. Sin embargo, para mejorar el tiempo de inicio, debe evitar cargar inicialmente demasiados datos. Puede que desee modificar la clase `Cache` para aumentar el número de páginas de datos que puede almacenar. El uso de más páginas de datos puede mejorar la eficacia del desplazamiento, pero tendrá que determinar el número ideal de filas en una página de datos, en función del ancho de banda disponible y de la latencia del servidor. Con páginas más pequeñas, se tiene acceso al servidor con mayor frecuencia, pero se tardará menos tiempo en devolver los datos solicitados. Si la latencia es mayor que un problema que el ancho de banda, puede que desee usar páginas de datos más grandes.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Ajuste del rendimiento del control DataGridView en Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Modo virtual del control DataGridView de Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Tutorial: Implementar el modo virtual en el control DataGridView de Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
- [Implementar el modo virtual con la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)

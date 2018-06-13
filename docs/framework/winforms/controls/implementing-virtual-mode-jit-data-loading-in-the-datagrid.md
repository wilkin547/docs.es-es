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
ms.openlocfilehash: ad3ec7fb2e0012459bcf597ac9abee76c20b767e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540922"
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms
Una razón para implementar el modo virtual en el <xref:System.Windows.Forms.DataGridView> control consiste en recuperar datos sólo según sea necesario. Esto se denomina *carga de datos just-in-time*.  
  
 Si está trabajando con una tabla muy grande en una base de datos remota, por ejemplo, puede evitar retrasos en el inicio, recuperar únicamente los datos que sean necesarios para mostrar y recuperar datos adicionales sólo cuando el usuario desplaza nuevas filas en la vista. Si los equipos cliente que se ejecuta la aplicación tienen una cantidad limitada de memoria disponible para almacenar datos, también puede descartar los datos no utilizados al recuperar nuevos valores de la base de datos.  
  
 Las secciones siguientes describen cómo utilizar un <xref:System.Windows.Forms.DataGridView> control con una caché just-in-time.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: implementar el modo Virtual con la carga de datos Just en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="the-form"></a>El formulario  
 En el ejemplo de código siguiente se define un formulario que contenga solo lectura <xref:System.Windows.Forms.DataGridView> control que interactúa con un `Cache` objeto a través de un <xref:System.Windows.Forms.DataGridView.CellValueNeeded> controlador de eventos. El `Cache` objeto administra los valores almacenados localmente y usa un `DataRetriever` objeto que se va a recuperar los valores de la tabla Orders de la base de datos de ejemplo Northwind. El `DataRetriever` objeto, que implementa el `IDataPageRetriever` interfaz requerida por el `Cache` de clases, también se utiliza para inicializar el <xref:System.Windows.Forms.DataGridView> controlar las filas y columnas.  
  
 El `IDataPageRetriever`, `DataRetriever`, y `Cache` tipos se describen más adelante en este tema.  
  
> [!NOTE]
>  Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>La interfaz IDataPageRetriever  
 En el ejemplo de código siguiente se define la `IDataPageRetriever` interfaz, que se implementa mediante la `DataRetriever` clase. El único método declarado en esta interfaz es la `SupplyPageOfData` método, que requiere un índice de fila inicial y un recuento del número de filas en una sola página de datos. Estos valores se usan por el implementador para recuperar un subconjunto de datos de un origen de datos.  
  
 Un `Cache` objeto utiliza una implementación de esta interfaz durante la construcción para cargar dos páginas iniciales de datos. Cada vez que se necesita un valor sin almacenar en caché, la memoria caché descarta una de estas páginas y solicita una nueva página que contiene el valor de la `IDataPageRetriever`.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>La clase DataRetriever  
 En el ejemplo de código siguiente se define la `DataRetriever` de la clase, que implementa el `IDataPageRetriever` interfaz para recuperar las páginas de datos de un servidor. El `DataRetriever` clase también proporciona `Columns` y `RowCount` propiedades, que la <xref:System.Windows.Forms.DataGridView> control usa para crear las columnas necesarias y para agregar el número adecuado de filas vacías para los <xref:System.Windows.Forms.DataGridView.Rows%2A> colección. Agregar filas vacías es necesario para que el control se comporte como si tuviera todos los datos de la tabla. Esto significa que el cuadro de desplazamiento en la barra de desplazamiento tendrá el tamaño adecuado y el usuario podrá tener acceso a cualquier fila de la tabla. Las filas se rellenan el <xref:System.Windows.Forms.DataGridView.CellValueNeeded> controlador de eventos solo cuando se desplazan en la vista.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>Cache (clase)  
 En el ejemplo de código siguiente se define la `Cache` (clase), que administra dos páginas de datos que se rellenan a través de un `IDataPageRetriever` implementación. El `Cache` clase define interior `DataPage` estructura que contiene un <xref:System.Data.DataTable> para almacenar los valores en una memoria caché única página y que calcula la fila de índices que representan los límites superiores e inferiores de la página.  
  
 La `Cache` clase carga dos páginas de datos en tiempo de construcción. Cada vez que la <xref:System.Windows.Forms.DataGridView.CellValueNeeded> evento solicita un valor, la `Cache` objeto determina si el valor está disponible en una de sus dos páginas y, si es así, lo devuelve. Si el valor no está disponible localmente, el `Cache` objeto determina cuál de sus dos páginas está más alejado de las filas mostradas actualmente y reemplaza la página con uno nuevo que contiene el valor solicitado, que, a continuación, devuelve.  
  
 Suponiendo que el número de filas de una página de datos es el mismo que el número de filas que se pueden mostrar en pantalla al mismo tiempo, este modelo permite a los usuarios paginar a través de la tabla devolver de forma eficaz la página vista más recientemente.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>Consideraciones adicionales  
 Los ejemplos de código anteriores se proporcionan como una demostración de la carga de datos just-in-time. Debe modificar el código para sus propias necesidades lograr la máxima eficiencia. Como mínimo, debe elegir un valor adecuado para el número de filas por página de datos en la memoria caché. Este valor se pasa en el `Cache` constructor. El número de filas por página debe ser no menor que el número de filas que se pueden mostrar simultáneamente en el <xref:System.Windows.Forms.DataGridView> control.  
  
 Para obtener mejores resultados, debe llevar a cabo pruebas de rendimiento y las pruebas de facilidad de uso para determinar los requisitos del sistema y los usuarios. Algunos factores que debe tomar en consideración incluyen la cantidad de memoria en los equipos cliente ejecutan la aplicación, el ancho de banda disponible de la conexión de red utilizada y la latencia del servidor utilizado. La latencia y al ancho de banda deben determinarse en los momentos de uso máximo.  
  
 Para mejorar el rendimiento del desplazamiento de la aplicación, puede aumentar la cantidad de datos almacenados localmente. Sin embargo, para mejorar el tiempo de inicio, debe evitar cargar inicialmente demasiado datos. Puede que desee modificar el `Cache` clase para aumentar el número de páginas de datos que puede almacenar. Uso de más páginas de datos puede mejorar la eficacia de desplazamiento, pero debe determinar el número ideal de filas en una página de datos, según el ancho de banda disponible y la latencia del servidor. Con páginas más pequeñas, el servidor de acceso con más frecuencia, pero tardará menos tiempo para devolver los datos solicitados. Si la latencia es superior de un problema de ancho de banda, puede que desee usar las páginas de datos mayor.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 [Ajuste del rendimiento del control DataGridView en Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [Modo virtual del control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [Tutorial: Implementar el modo virtual en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 [Implementar el modo virtual con la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)

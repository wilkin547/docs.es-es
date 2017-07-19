---
title: "Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "datos [Windows Forms], administrar conjuntos de datos grandes"
  - "DataGridView (control) [Windows Forms], conjuntos de datos grandes"
  - "DataGridView (control) [Windows Forms], modo virtual"
  - "ejemplos [Windows Forms], carga de datos Just-In-Time"
  - "carga de datos Just-In-Time"
  - "modo virtual, carga de datos Just-In-Time"
ms.assetid: c2a052b9-423c-4ff7-91dc-d8c7c79345f6
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms
Una razón para implementar el modo virtual en el control <xref:System.Windows.Forms.DataGridView> es recuperar datos únicamente cuando se necesiten.  Esto se denomina *carga de datos Just\-in\-time \(JIT\)*.  
  
 Por ejemplo, si está trabajando con una tabla muy extensa en una base de datos remota, querrá evitar los retrasos del inicio recuperando sólo los datos que sean necesarios para mostrar y recuperar datos adicionales sólo cuando el usuario desplace nuevas filas a la vista.  Si los equipos de cliente que ejecutan la aplicación tienen una cantidad limitada de memoria disponible para almacenar datos, también querrá descartar los datos no utilizados al recuperar nuevos valores de la base de datos.  
  
 Las secciones siguientes describen cómo utilizar un control <xref:System.Windows.Forms.DataGridView> con una caché Just\-in\-time.  
  
 Para copiar el código de este tema como un listado sencillo, vea [Cómo: Implementar el modo virtual con la carga de datos Just\-In\-Time en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## El formulario  
 En el ejemplo de código siguiente se define un formulario que contiene un control <xref:System.Windows.Forms.DataGridView> de sólo lectura que interactúa con un objeto `Cache` mediante un controlador de eventos <xref:System.Windows.Forms.DataGridView.CellValueNeeded>.  El objeto `Cache` administra los valores localmente almacenados y utiliza un objeto `DataRetriever`para recuperar los valores desde la tabla Orders de la base de datos de ejemplo Northwind.  El objeto `DataRetriever`, que implementa la interfaz `IDataPageRetriever` requerida por la clase `Cache`, también se utiliza para inicializar las filas y columnas del control <xref:System.Windows.Forms.DataGridView>.  
  
 Los tipos `IDataPageRetriever`, `DataRetriever` y `Cache` se describen más adelante en este tema.  
  
> [!NOTE]
>  El hecho de almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.  El uso de la autenticación de Windows \(también conocida como seguridad integrada\) es un modo más seguro de controlar el acceso a una base de datos.  Para obtener más información, vea [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## La interfaz IDataPageRetriever  
 En el ejemplo de código siguiente se define la interfaz `IDataPageRetriever`, que es implementada por la clase `DataRetriever`.  El único método declarado en esta interfaz es el método `SupplyPageOfData`, que requiere un índice de filas inicial y un contador del número de filas en una única página de datos.  El implementador utiliza estos valores para recuperar un subconjunto de datos de un origen de datos.  
  
 El objeto `Cache` utiliza una implementación de esta interfaz durante la construcción para cargar dos páginas iniciales de datos.  Siempre que se necesite a un valor que no esté en la caché, ésta descarta una de estas páginas y solicita una nueva página que contiene el valor de `IDataPageRetriever`.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## La clase DataRetriever  
 En el ejemplo de código siguiente se define la clase `DataRetriever`, que implementa la interfaz `IDataPageRetriever` para recuperar paginas de los datos de un servidor.  La clase `DataRetriever` también proporciona las propiedades `Columns` y `RowCount`, que utiliza el control <xref:System.Windows.Forms.DataGridView> para crear las columnas necesarias y agregar el número adecuado de filas vacías a la colección <xref:System.Windows.Forms.DataGridView.Rows%2A>.  Agregar filas vacías es necesario para que el control se comporte como si tuviera todos los datos en la tabla.  Esto significa que el cuadro de desplazamiento de la barra de desplazamiento tendrá el tamaño apropiado, y que el usuario podrá tener acceso a cualquier fila de la tabla.  El controlador de eventos <xref:System.Windows.Forms.DataGridView.CellValueNeeded> rellena sólo las filas cuando se desplazan en la vista.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## La clase Cache  
 En el ejemplo de código siguiente se define la clase `Cache`, que administra dos páginas de datos rellenas mediante a una implementación de `IDataPageRetriever`.  La clase `Cache` define una estructura `DataPage` interna, que contiene un <xref:System.Data.DataTable> para almacenar los valores en una única página de caché y que calcula los índices de fila que representan los límites superior e inferior de la página.  
  
 La clase `Cache` carga dos páginas de datos en tiempo de construcción.  Siempre que el evento <xref:System.Windows.Forms.DataGridView.CellValueNeeded> solicite un valor, el objeto `Cache` determina si el valor está disponible en una de sus dos páginas y, si es así, lo devuelve.  Si el valor no está disponible localmente, el objeto `Cache` determina cuál de sus dos páginas está más alejada de las dos filas mostradas actualmente y reemplaza la página con una nueva que contiene el valor solicitado, que devuelve a continuación.  
  
 Suponiendo que el número de filas de una página de datos es el mismo que el número de filas que se pueden mostrar en la pantalla de una sola vez, este modelo permite a los usuarios desplazarse por las páginas de la tabla para devolver de forma eficaz la página vista más recientemente.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## Consideraciones adicionales  
 En los ejemplos de código anteriores se proporcionan como una demostración de carga de datos Just\-in\-time \(JIT\).  Necesitará modificar el código en función de sus necesidades para lograr la máxima eficacia.  Como mínimo, tendrá que elegir un valor adecuado para el número de filas por página de datos en la caché.  Este valor se pasa en el constructor `Cache`.  El número de filas por página no debería ser menor que el número de filas que se pueden mostrar simultáneamente en el control <xref:System.Windows.Forms.DataGridView>.  
  
 Para obtener un mejor resultado, tendrá que realizar una prueba de rendimiento y de uso para determinar los requisitos del sistema y de los usuarios.  Entre los diversos factores que tendrá que tomar en consideración se incluyen el total de memoria en los equipos de cliente que están ejecutando la aplicación, el ancho de banda disponible de la conexión de red utilizada y la latencia del servidor utilizado.  El ancho de banda y la latencia deberían determinarse en los momentos de uso máximo.  
  
 Para mejorar el rendimiento del desplazamiento de la aplicación, puede aumentar la cantidad de datos almacenados localmente.  No obstante, para mejorar el tiempo de inicio debe evitar cargar inicialmente demasiado datos.  Quizá desee modificar la clase `Cache` para aumentar el número de páginas de datos que puede almacenar.  Utilizar más páginas de datos puede mejorar la eficacia del desplazamiento, pero tendrá que determinar el número de filas idóneo en una página de datos, dependiendo del ancho de banda disponible y de la latencia del servidor.  Con un menor número de páginas, tendrá acceso con más frecuencia al servidor, pero tardará menos tiempo en devolver los datos solicitados.  Si la latencia supone más problema que el ancho de banda, utilice un mayor número de páginas de datos.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>   
 [Ajuste del rendimiento del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [Modo virtual del control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)   
 [Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)   
 [Cómo: Implementar el modo virtual con la carga de datos Just\-In\-Time en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)
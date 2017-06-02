---
title: "Escenarios del control DataGridView (formularios Windows Forms) | Microsoft Docs"
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
  - "datos [Windows Forms], mostrar en formato de tabla"
  - "cuadrículas de datos, acerca de las cuadrículas de datos"
  - "DataGridView (control) [Windows Forms], escenarios"
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Escenarios del control DataGridView (formularios Windows Forms)
Con el control <xref:System.Windows.Forms.DataGridView>, puede mostrar datos en formato de tabla de distintos orígenes de datos.  Para usos sencillos, puede rellenar manualmente un control <xref:System.Windows.Forms.DataGridView> y manipular directamente los datos a través del control.  No obstante, normalmente almacenará los datos en un origen de datos externo y enlazará el control a él a través de un componente <xref:System.Windows.Forms.BindingSource>.  
  
 En este tema se describen algunos de los escenarios comunes en los que interviene el control <xref:System.Windows.Forms.DataGridView>.  
  
## Escenario 1: Mostrar pequeñas cantidades de datos  
 No tiene que almacenar los datos en un origen de datos externo para mostrarlos en el control <xref:System.Windows.Forms.DataGridView>.  Si trabaja con una pequeña cantidad de datos, puede rellenar el control y manipular los datos a través del control.  A esto se lo denomina *modo sin enlazar*.  Para obtener más información, vea [Cómo: Crear un control DataGridView no enlazado en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
### Puntos clave del escenario  
  
-   En el modo sin enlazar, puede rellenar manualmente el control.  
  
-   El modo sin enlazar resulta especialmente adecuado para pequeñas cantidades de datos de sólo lectura.  
  
-   El modo sin enlazar también resulta adecuado para tablas del estilo de hoja de cálculo o muy poco pobladas.  
  
## Escenario 2: Mostrar y actualizar datos almacenados en un origen de datos externo  
 Puede utilizar el control <xref:System.Windows.Forms.DataGridView> como una interfaz de usuario \(IU\) a través de la que los usuarios pueden tener acceso a datos conservados en un origen de datos como una tabla de base de datos o una colección de objetos comerciales.  Para obtener más información, vea [Cómo: Enlazar datos al control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
### Puntos clave del escenario  
  
-   El modo de enlace permite conectar con un origen de datos, generar automáticamente columnas según las propiedades del origen de datos o las columnas de base de datos y rellenar automáticamente el control.  
  
-   El modo de enlace resulta adecuado para una interacción intensiva del usuario con los datos.  Se puede dar formato a los datos para su presentación y analizarse los datos especificados por el usuario en el formato esperado por el origen de datos.  Se pueden detectar errores de formato de introducción de datos y de restricción de base de datos de modo que se pueda advertir a los usuarios y corregirse las celdas con error.  
  
-   Funciones adicionales como ordenación de columnas, inmovilización y reordenación permiten a los usuarios mostrar los datos de la manera más cómoda para su flujo de trabajo.  
  
-   La función del Portapapeles permite a los usuarios copiar datos de la aplicación en otras aplicaciones.  
  
## Escenario 3: Datos avanzados  
 Si tiene necesidades especiales que el modelo de enlace de datos estándar no trata, puede administrar la interacción entre el control y los datos implementando el *modo virtual*.  Implementar el modo virtual significa implementar uno o más controladores de eventos que permiten al control solicitar información sobre celdas cuando la necesita.  
  
 Por ejemplo, si trabaja con grandes cantidades de datos, quizá desee implementar el modo virtual para garantizar una eficacia óptima.  El modo virtual también resulta de utilidad para mantener los valores de columnas sin enlazar que puede mostrar junto con columnas recuperadas de otro origen de datos.  
  
 Para obtener más información sobre el modo de virtual, vea [Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
### Puntos clave del escenario  
  
-   El modo virtual resulta adecuado para mostrar cantidades muy grandes de datos cuando necesita ajustar el rendimiento.  
  
## Escenario 4: Cambio de tamaño de filas y columnas automático  
 Cuando muestra datos que se actualizan regularmente, puede cambiar el tamaño de filas y columnas automáticamente para garantizar que todo el contenido está visible.  El control <xref:System.Windows.Forms.DataGridView> proporciona varias opciones que permiten habilitar o deshabilitar el cambio de tamaño manual, el cambio de tamaño mediante programación a horas concretas o el cambio de tamaño automático cada vez que cambia el contenido.  Para obtener más información, vea [Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).  
  
### Puntos clave del escenario  
  
-   El cambio de tamaño manual permite a los usuarios ajustar el alto y ancho de celdas.  
  
-   El cambio de tamaño automático permite mantener los tamaños de celda para que nunca se recorte el contenido de la celda.  
  
-   El cambio de tamaño mediante programación permite cambiar el tamaño de las celdas en momentos concretos para evitar la reducción del rendimiento por el cambio de tamaño automático continuo.  
  
## Escenario 5: Personalización simple  
 El control <xref:System.Windows.Forms.DataGridView> proporciona muchas maneras de modificar el aspecto y comportamiento básico.  Para obtener más información, vea [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
### Puntos clave del escenario  
  
-   Los objetos <xref:System.Windows.Forms.DataGridViewCellStyle> permiten proporcionar color, fuente, formato e información de posición en varios niveles y para elementos individuales del control.  
  
-   Se pueden disponer en capas los estilos de celda y compartirse entre varios elementos, lo que permite reutilizar el código.  
  
## Escenario 6: Personalización avanzada  
 El control <xref:System.Windows.Forms.DataGridView> proporciona muchas maneras de personalizar su aspecto y comportamiento.  
  
### Puntos clave del escenario  
  
-   Puede proporcionar su propio código de dibujo de celda.  Para obtener más información, vea [Cómo: Personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md).  
  
-   Puede proporcionar su propio dibujo de fila.  Por ejemplo, esto resulta de utilidad para crear filas con contenido que abarca varias columnas.  Para obtener más información, vea [Cómo: Personalizar la apariencia de las filas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md).  
  
-   Puede implementar sus propias clases de celda y columna para personalizar la apariencia de la celda.  Para obtener más información, vea [Cómo: Personalizar celdas y columnas en el control DataGridView de formularios Windows Forms ampliando su comportamiento y apariencia](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).  
  
-   Puede implementar sus propias clases de celda y columna para hospedar controles que no sean los proporcionados por los tipos de columna integrados.  Para obtener más información, vea [Cómo: Alojar controles en celdas DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 [Información general del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)
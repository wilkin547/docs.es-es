---
title: Escenarios del control DataGridView (formularios Windows Forms)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 919197d8fdb40f0e0fb7b91fecae38f4e0e061bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="datagridview-control-scenarios-windows-forms"></a>Escenarios del control DataGridView (formularios Windows Forms)
Con el <xref:System.Windows.Forms.DataGridView> control, puede mostrar datos tabulares de una variedad de orígenes de datos. Para usos sencillos, puede rellenar manualmente un <xref:System.Windows.Forms.DataGridView> y manipular los datos directamente a través del control. Normalmente, sin embargo, se almacenan los datos en un origen de datos externo y enlazar el control a él a través de un <xref:System.Windows.Forms.BindingSource> componente.  
  
 Este tema describen algunos de los escenarios comunes que implican el <xref:System.Windows.Forms.DataGridView> control.  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a>Escenario 1: Mostrar pequeñas cantidades de datos  
 No es necesario que almacenar los datos en un origen de datos externo para que se muestre en el <xref:System.Windows.Forms.DataGridView> control. Si está trabajando con una pequeña cantidad de datos, puede rellenar el control y manipular los datos a través del control. Esto se denomina *el modo sin enlazar*. Para obtener más información, consulte [Cómo: crear un DataGridView Control de Windows Forms sin enlazar](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Puntos clave del escenario  
  
-   En el modo sin enlazar, rellenar manualmente el control.  
  
-   El modo sin enlazar es especialmente adecuado para pequeñas cantidades de datos de solo lectura.  
  
-   El modo sin enlazar también es ideal para las tablas de hoja de cálculo o apenas llena.  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a>Escenario 2: Ver y actualizar los datos almacenados en un origen de datos externo  
 Puede usar el <xref:System.Windows.Forms.DataGridView> control como una interfaz de usuario (UI) a través de los usuarios que pueden tener acceso a datos guardados en un origen de datos como una tabla de base de datos o una colección de objetos comerciales. Para obtener más información, consulte [Cómo: enlazar datos al DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Puntos clave del escenario  
  
-   El modo de enlace le permite conectarse a un origen de datos, generar automáticamente columnas basándose en las propiedades del origen de datos o columnas de base de datos y rellenar automáticamente el control.  
  
-   Modo de enlace es adecuado para la interacción del usuario pesada con datos. Se pueden aplicar el formato de datos para su presentación y se pueden analizar los datos especificados por el usuario en el formato esperado por el origen de datos. Se pueden detectar errores y errores de restricción de la base de datos de formato de entrada de datos para que pueden advertir a los usuarios y corregirse las celdas pueden corregirse.  
  
-   Funcionalidad adicional como la ordenación de columnas, inmovilización y la reordenación de permiten a los usuarios ver los datos de la manera más conveniente para su flujo de trabajo.  
  
-   Compatibilidad con el Portapapeles permite a los usuarios copiar datos desde la aplicación en otras aplicaciones.  
  
## <a name="scenario-3-advanced-data"></a>Escenario 3: Avanzada de datos  
 Si tiene necesidades especiales que el modelo de enlace de datos estándar no se soluciona, puede administrar la interacción entre el control y los datos mediante la implementación *modo virtual*. Implementar el modo virtual significa implementar uno o más controladores de eventos que permiten al control solicitar información acerca de las celdas que la información es necesaria.  
  
 Por ejemplo, si trabaja con grandes cantidades de datos, puede implementar el modo virtual para garantizar una eficiencia óptima. Modo virtual también es útil para mantener los valores de columnas sin enlazar que puede mostrar junto con columnas recuperadas de otro origen de datos.  
  
 Para obtener más información sobre el modo virtual, vea [Tutorial: implementar el modo Virtual en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Puntos clave del escenario  
  
-   Modo virtual es adecuado para mostrar grandes cantidades de datos cuando se necesita optimizar el rendimiento.  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a>Escenario 4: Cambiar el tamaño automáticamente filas y columnas  
 Cuando muestra datos que se actualizan con regularidad, puede cambiar automáticamente filas y columnas para asegurarse de que todo el contenido está visible. El <xref:System.Windows.Forms.DataGridView> control ofrece varias opciones que permiten habilitar o deshabilitar manualmente el cambio de tamaño, cambiar el tamaño mediante programación a horas específicas o cambio de tamaño automáticamente cada vez que cambie el contenido. Para obtener más información, consulte [opciones de ajuste de tamaño en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Puntos clave del escenario  
  
-   El cambio de tamaño manual permite a los usuarios ajustar el alto de celda y el ancho.  
  
-   Cambio de tamaño automático permite mantener los tamaños de celda para que nunca se recorta el contenido de la celda.  
  
-   Cambiar el tamaño mediante programación permite cambiar el tamaño de las celdas en momentos concretos para evitar la reducción del rendimiento de tamaño automático continuo.  
  
## <a name="scenario-5-simple-customization"></a>Escenario 5: Personalización Simple  
 El <xref:System.Windows.Forms.DataGridView> control proporciona muchas formas de modificar su aspecto y comportamiento básico. Para obtener más información, consulte [estilos de celda en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Puntos clave del escenario  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle>objetos permiten proporcionar color, fuente, formato e información de posición en varios niveles y de los elementos individuales del control.  
  
-   Estilos de celda se pueden niveles y compartidos por varios elementos, lo que le permite reutilizar el código.  
  
## <a name="scenario-6-advanced-customization"></a>Escenario 6: Personalización avanzada  
 El <xref:System.Windows.Forms.DataGridView> control proporciona muchas maneras de personalizar su apariencia y comportamiento.  
  
### <a name="scenario-key-points"></a>Puntos clave del escenario  
  
-   Puede proporcionar su propio código de dibujo de la celda. Para obtener más información, consulte [Cómo: personalizar la apariencia de celdas en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md).  
  
-   Puede proporcionar su propio dibujo de fila. Esto es útil, por ejemplo, para crear filas con contenido que abarca varias columnas. Para obtener más información, consulte [Cómo: personalizar la apariencia de filas en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md).  
  
-   Puede implementar sus propias clases de celda y de columna para personalizar el aspecto de la celda. Para obtener más información, consulte [Cómo: personalizar celdas y columnas en el DataGridView Control de formularios Windows Forms por extender su comportamiento y apariencia](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).  
  
-   Puede implementar sus propias clases de celda y columna para hospedar controles distintos de los proporcionados por los tipos de columna integrados. Para obtener más información, consulte [Cómo: hospedar controles en celdas DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 [Información general del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)

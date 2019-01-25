---
title: Escenarios del control DataGridView (formularios Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
ms.openlocfilehash: c8d6f3d9b1d0380ccf78badd44484c96e0593bd8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54621440"
---
# <a name="datagridview-control-scenarios-windows-forms"></a>Escenarios del control DataGridView (formularios Windows Forms)
Con el <xref:System.Windows.Forms.DataGridView> control, puede mostrar datos tabulares de una variedad de orígenes de datos. Para usos simples, puede rellenar manualmente un <xref:System.Windows.Forms.DataGridView> y manipular los datos directamente a través del control. Por lo general, sin embargo, almacenará los datos en un origen de datos externo y enlazar el control a él a través de un <xref:System.Windows.Forms.BindingSource> componente.  
  
 En este tema se describe algunos de los escenarios comunes que implican la <xref:System.Windows.Forms.DataGridView> control.  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a>Escenario 1: Mostrar pequeñas cantidades de datos  
 No es necesario que almacenar los datos en un origen de datos externo para mostrarlo en el <xref:System.Windows.Forms.DataGridView> control. Si está trabajando con una pequeña cantidad de datos, puede rellenar el control y manipular los datos a través del control. Esto se denomina *modo independiente*. Para obtener más información, vea [Cómo: Crear un Control DataGridView de formularios de Windows independiente](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Puntos clave del escenario  
  
-   En el modo independiente, rellena el control manualmente.  
  
-   Modo independiente es especialmente adecuado para pequeñas cantidades de datos de solo lectura.  
  
-   Modo independiente también es adecuado para las tablas de hojas de cálculo o apenas llena.  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a>Escenario 2: Ver y actualizar los datos almacenados en un origen de datos externo  
 Puede usar el <xref:System.Windows.Forms.DataGridView> controlar como una interfaz de usuario (IU) a través de los usuarios que pueden acceder a datos que se mantienen en un origen de datos como una tabla de base de datos o una colección de objetos de negocios. Para obtener más información, vea [Cómo: Enlazar datos a la Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Puntos clave del escenario  
  
-   Modo de enlace le permite conectarse a un origen de datos, generar automáticamente columnas basándose en las propiedades del origen de datos o columnas de base de datos y rellenar automáticamente el control.  
  
-   Modo de enlace es adecuado para la interacción del usuario pesada con datos. Se pueden aplicar el formato de datos para su presentación y se pueden analizar los datos especificados por el usuario en el formato esperado por el origen de datos. Por lo que pueden advertir a los usuarios y las celdas erróneas pueden corregirse, se puede detectar errores y errores de restricción de la base de datos de formato de entrada de datos.  
  
-   Funcionalidad adicional como ordenación de columnas, la inmovilización y la reordenación de permiten que los usuarios ver los datos de la manera más conveniente para su flujo de trabajo.  
  
-   Compatibilidad con el Portapapeles permite a los usuarios copiar datos desde la aplicación en otras aplicaciones.  
  
## <a name="scenario-3-advanced-data"></a>Escenario 3: Datos avanzados  
 Si tiene necesidades especiales que no se corrige el modelo de enlace de datos estándar, puede administrar la interacción entre el control y sus datos mediante la implementación *modo virtual*. Implementar el modo virtual significa implementar uno o varios controladores de eventos que permiten al control solicitar información acerca de las celdas que la información es necesaria.  
  
 Por ejemplo, si trabaja con grandes cantidades de datos, es posible que desee implementar el modo virtual para garantizar una eficiencia óptima. Modo virtual también es útil para mantener los valores de columnas independientes que muestran junto con columnas recuperadas desde otro origen de datos.  
  
 Para obtener más información sobre el modo virtual, consulte [Tutorial: Implementar el modo Virtual en el Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Puntos clave del escenario  
  
-   Modo virtual es adecuado para mostrar grandes cantidades de datos cuando deba ajustar el rendimiento.  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a>Escenario 4: Cambiar automáticamente el tamaño de filas y columnas  
 Cuando muestra datos que se actualizan periódicamente, puede cambiar automáticamente las filas y columnas para asegurarse de que todo el contenido está visible. El <xref:System.Windows.Forms.DataGridView> control ofrece varias opciones que permiten habilitar o deshabilitar manualmente el cambio de tamaño, cambiar el tamaño mediante programación a horas específicas o cambio de tamaño automáticamente cada vez que cambie el contenido. Para obtener más información, consulte [opciones de ajuste de tamaño en el DataGridView Control de formularios de Windows](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Puntos clave del escenario  
  
-   El cambio de tamaño manual permite que los usuarios ajustar el ancho y el alto de celda.  
  
-   Cambio de tamaño automático le permite mantener los tamaños de celda para que nunca se recorta el contenido de la celda.  
  
-   El cambio de tamaño mediante programación le permite cambiar el tamaño de las celdas en momentos concretos para evitar la disminución del rendimiento de tamaño automático continuo.  
  
## <a name="scenario-5-simple-customization"></a>Escenario 5: Personalización sencilla  
 El <xref:System.Windows.Forms.DataGridView> control proporciona muchas formas de modificar su aspecto y comportamiento básico. Para obtener más información, consulte [estilos de celda en el DataGridView Control de Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Puntos clave del escenario  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle> objetos permiten proporcionar color, fuente, formato e información de posición en varios niveles y para elementos individuales del control.  
  
-   Estilos de celda pueden ser en capas y compartidos por varios elementos, lo que le permite reutilizar el código.  
  
## <a name="scenario-6-advanced-customization"></a>Escenario 6: Personalización avanzada  
 El <xref:System.Windows.Forms.DataGridView> control proporciona muchas formas de personalizar su apariencia y comportamiento.  
  
### <a name="scenario-key-points"></a>Puntos clave del escenario  
  
-   Puede proporcionar su propio código de dibujo de la celda. Para obtener más información, vea [Cómo: Personalizar la apariencia de celdas en el Control DataGridView de formularios de Windows](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md).  
  
-   Puede proporcionar su propio dibujo de fila. Esto es útil, por ejemplo, para crear filas con contenido que abarca varias columnas. Para obtener más información, vea [Cómo: Personalizar la apariencia de las filas en el Control DataGridView de formularios de Windows](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md).  
  
-   Puede implementar sus propias clases de celda y de columna para personalizar el aspecto de la celda. Para obtener más información, vea [Cómo: Personalizar celdas y columnas en la Windows Forms DataGridView Control ampliando su comportamiento y apariencia](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).  
  
-   Puede implementar sus propias clases de celda y de columna para hospedar controles distintos de los proporcionados por los tipos de columna integrados. Para obtener más información, vea [Cómo: Alojar controles en formularios de Windows las celdas de DataGridView](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.DataGridView>
- [Información general del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)

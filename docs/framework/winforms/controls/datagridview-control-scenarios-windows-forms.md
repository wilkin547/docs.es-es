---
title: Escenarios del control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
ms.openlocfilehash: 160d967c6445fb753cb6c73babfb02a734a07e28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742459"
---
# <a name="datagridview-control-scenarios-windows-forms"></a>Escenarios del control DataGridView (formularios Windows Forms)
Con el control <xref:System.Windows.Forms.DataGridView>, puede mostrar datos tabulares de diversos orígenes de datos. En el caso de los usos sencillos, puede rellenar manualmente una <xref:System.Windows.Forms.DataGridView> y manipular los datos directamente a través del control. Sin embargo, normalmente almacenará los datos en un origen de datos externo y le enlazará el control a través de un componente de <xref:System.Windows.Forms.BindingSource>.  
  
 En este tema se describen algunos de los escenarios comunes que implican el control de <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a>Escenario 1: Mostrar pequeñas cantidades de datos  
 No es necesario almacenar los datos en un origen de datos externo para mostrarlos en el control <xref:System.Windows.Forms.DataGridView>. Si está trabajando con una pequeña cantidad de datos, puede rellenar el control usted mismo y manipular los datos a través del control. Esto se denomina *modo sin enlazar*. Para obtener más información, vea [Cómo: crear un control DataGridView de Windows Forms independiente](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Puntos clave de escenario  
  
- En el modo sin enlazar, rellenar el control manualmente.  
  
- El modo sin enlazar es especialmente adecuado para pequeñas cantidades de datos de solo lectura.  
  
- El modo sin enlazar también es adecuado para las tablas con forma de hoja de cálculo o con rellenado disperso.  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a>Escenario 2: ver y actualizar los datos almacenados en un origen de datos externo  
 Puede usar el control <xref:System.Windows.Forms.DataGridView> como una interfaz de usuario a través de la cual los usuarios pueden tener acceso a los datos que se mantienen en un origen de datos, como una tabla de base de datos o una colección de objetos empresariales. Para obtener más información, vea [Cómo: enlazar datos al control DataGridView Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Puntos clave de escenario  
  
- El modo enlazado le permite conectarse a un origen de datos, generar columnas automáticamente en función de las propiedades de origen de datos o columnas de base de datos y rellenar automáticamente el control.  
  
- El modo de enlace es adecuado para una gran interacción del usuario con los datos. Se puede dar formato a los datos para su presentación y los datos especificados por el usuario se pueden analizar en el formato esperado por el origen de datos. Los errores de formato de entrada de datos y los errores de restricción de base de datos pueden detectarse para que se puedan avisar a los usuarios y corregir las celdas erróneas.  
  
- La funcionalidad adicional, como la ordenación de columnas, la inmovilización y la reordenación permiten a los usuarios ver los datos de la manera más conveniente para su flujo de trabajo.  
  
- La compatibilidad con el portapapeles permite a los usuarios copiar datos de la aplicación en otras aplicaciones.  
  
## <a name="scenario-3-advanced-data"></a>Escenario 3: datos avanzados  
 Si tiene necesidades especiales que el modelo de enlace de datos estándar no trata, puede administrar la interacción entre el control y los datos implementando el *modo virtual*. Al implementar el modo virtual, se implementan uno o varios controladores de eventos que permiten al control solicitar información sobre las celdas a medida que se necesita la información.  
  
 Por ejemplo, si trabaja con grandes cantidades de datos, puede que desee implementar el modo virtual para garantizar una eficiencia óptima. El modo virtual también es útil para mantener los valores de las columnas sin enlazar que se muestran junto con las columnas recuperadas de otro origen de datos.  
  
 Para obtener más información sobre el modo virtual, vea [Tutorial: implementar el modo virtual en el control DataGridView de Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Puntos clave de escenario  
  
- El modo virtual es adecuado para mostrar grandes cantidades de datos cuando es necesario ajustar el rendimiento.  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a>Escenario 4: cambiar el tamaño de las filas y columnas automáticamente  
 Al mostrar los datos que se actualizan periódicamente, puede cambiar automáticamente el tamaño de las filas y columnas para asegurarse de que todo el contenido está visible. El control <xref:System.Windows.Forms.DataGridView> proporciona varias opciones que permiten habilitar o deshabilitar el cambio de tamaño manual, cambiar el tamaño mediante programación a horas específicas o cambiar el tamaño automáticamente cada vez que cambie el contenido. Para obtener más información, consulte [Opciones de ajuste de tamaño en el control DataGridView Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Puntos clave de escenario  
  
- El cambio de tamaño manual permite a los usuarios ajustar el alto y el ancho de las celdas.  
  
- El cambio de tamaño automático le permite mantener los tamaños de celda para que el contenido de la celda nunca se recorte.  
  
- El cambio de tamaño mediante programación permite cambiar el tamaño de las celdas en momentos concretos para evitar la reducción del rendimiento del cambio de tamaño automático continuo.  
  
## <a name="scenario-5-simple-customization"></a>Escenario 5: personalización sencilla  
 El control <xref:System.Windows.Forms.DataGridView> proporciona muchas formas de modificar su aspecto y comportamiento básicos. Para obtener más información, vea [estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Puntos clave de escenario  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle> objetos permiten proporcionar información sobre el color, la fuente, el formato y la posición en varios niveles y para elementos individuales del control.  
  
- Los estilos de celda pueden ser superpuestos y compartidos por varios elementos, lo que permite reutilizar el código.  
  
## <a name="scenario-6-advanced-customization"></a>Escenario 6: personalización avanzada  
 El control <xref:System.Windows.Forms.DataGridView> proporciona muchas maneras de personalizar su apariencia y comportamiento.  
  
### <a name="scenario-key-points"></a>Puntos clave de escenario  
  
- Puede proporcionar su propio código de dibujo de celda. Para obtener más información, vea [Cómo: personalizar la apariencia de las celdas en el control DataGridView Windows Forms](customize-the-appearance-of-cells-in-the-datagrid.md).  
  
- Puede proporcionar su propia representación de filas. Esto resulta útil, por ejemplo, para crear filas con contenido que abarque varias columnas. Para obtener más información, vea [Cómo: personalizar la apariencia de las filas en el control DataGridView Windows Forms](customize-the-appearance-of-rows-in-the-datagrid.md).  
  
- Puede implementar sus propias clases de celda y columna para personalizar el aspecto de la celda. Para obtener más información, vea [Cómo: personalizar celdas y columnas en el Control Windows Forms DataGridView extendiendo su comportamiento y apariencia](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).  
  
- Puede implementar sus propias clases de celda y columna para hospedar controles distintos de los proporcionados por los tipos de columna integrados. Para obtener más información, vea [Cómo: hospedar controles en Windows Forms celdas de DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- [Información general del control DataGridView](datagridview-control-overview-windows-forms.md)

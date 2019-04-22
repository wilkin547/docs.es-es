---
title: Resumen de la tecnología ToolStrip
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], technology summary
- status bars [Windows Forms], technology summary
- toolbars [Windows Forms], technology summary
- menus [Windows Forms], technology summary
ms.assetid: e8d61973-7af9-429f-9df5-05a899c15a7b
ms.openlocfilehash: b6537faa3be7ee28a934927fc95100a34a64e176
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120969"
---
# <a name="toolstrip-technology-summary"></a>Resumen de la tecnología ToolStrip
En este tema se resume la información sobre el control `ToolStrip` y las clases que admiten su uso.  
  
 El control `ToolStrip` y las clases asociadas a él proporcionan una solución completa para la creación de barras de herramientas, barras de estado y menús.  
  
## <a name="namespaces"></a>Espacios de nombres  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
## <a name="background"></a>Fondo  
 Con el control `ToolStrip` y las clases asociadas a él, puede crear funcionalidad avanzada de barras de herramientas con un aspecto y un comportamiento coherente y profesional. El control `ToolStrip` y sus clases ofrecen las siguientes mejoras en comparación con los controles anteriores:  
  
-   Un modelo de evento más coherente.  
  
-   Un comportamiento en tiempo de diseño más coherente que contiene editores de colecciones de elementos y listas de tareas.  
  
-   Representación personalizada con `ToolStripManager` y `ToolStripRenderer`.  
  
-   Espacio compartido integrado (uso compartido del espacio horizontal o vertical dentro del área de la herramienta cuando se acopla) con `ToolStripContainer` y `ToolStripPanel`.  
  
-   Reordenación de elementos en tiempo de diseño y tiempo de ejecución con la propiedad <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>.  
  
-   Reubicación de elementos a un menú de desbordamiento con la propiedad <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>.  
  
-   Ubicación de controles completamente configurable con `ToolStripContainer`, `ToolStripPanel` y `ToolStripContentPanel`.  
  
-   Hospedaje de `ToolStrip`, controles tradicionales o personalizados con `ToolStripControlHost`.  
  
-   Combinación de controles `ToolStrip` con `ToolStripPanel`.  
  
 `ToolStrip` es la clase base extensible de `MenuStrip`, `ContextMenuStrip` y `StatusStrip`. Estos controles son contenedores <xref:System.Windows.Forms.ToolStripItem> que heredan el control de eventos y el comportamiento común, extendidos para que cada implementación se ocupe del comportamiento que es adecuado para ella. Los controles que derivan de <xref:System.Windows.Forms.ToolStripItem> se muestran en la tabla siguiente. La clase base `ToolStrip` administra los eventos de pintura, entrada del usuario y arrastrar y colocar de estos controles.  
  
 Los controles `ToolStrip`, `MenuStrip`, `ContextMenuStrip` y `StatusStrip` reemplazan la barra de herramientas, el menú, el menú contextual y los controles de la barra de estado anteriores, aunque estos controles se conservan por compatibilidad con versiones anteriores.  
  
## <a name="toolstrip-classes-at-a-glance"></a>Resumen de las clases de ToolStrip  
 La siguiente tabla muestra las clases de ToolStrip agrupadas por área de tecnología.  
  
|Área de tecnología|Clase|  
|---------------------|-----------|  
|Contenedores de barra de herramientas, estado y menú|<xref:System.Windows.Forms.ToolStrip><br /><br /> <xref:System.Windows.Forms.MenuStrip><br /><br /> <xref:System.Windows.Forms.ContextMenuStrip><br /><br /> <xref:System.Windows.Forms.StatusStrip><br /><br /> <xref:System.Windows.Forms.ToolStripDropDownMenu>|  
|Elementos de ToolStrip|<xref:System.Windows.Forms.ToolStripLabel><br /><br /> <xref:System.Windows.Forms.ToolStripDropDownItem><br /><br /> <xref:System.Windows.Forms.ToolStripMenuItem><br /><br /> <xref:System.Windows.Forms.ToolStripButton><br /><br /> <xref:System.Windows.Forms.ToolStripStatusLabel><br /><br /> <xref:System.Windows.Forms.ToolStripSeparator><br /><br /> <xref:System.Windows.Forms.ToolStripControlHost><br /><br /> <xref:System.Windows.Forms.ToolStripComboBox><br /><br /> <xref:System.Windows.Forms.ToolStripTextBox><br /><br /> <xref:System.Windows.Forms.ToolStripProgressBar><br /><br /> <xref:System.Windows.Forms.ToolStripDropDownButton><br /><br /> <xref:System.Windows.Forms.ToolStripSplitButton>|  
|Ubicación|<xref:System.Windows.Forms.ToolStripContainer><br /><br /> <xref:System.Windows.Forms.ToolStripContentPanel><br /><br /> <xref:System.Windows.Forms.ToolStripPanel>|  
|Presentación y representación|<xref:System.Windows.Forms.ToolStripManager><br /><br /> <xref:System.Windows.Forms.ToolStripRenderer><br /><br /> <xref:System.Windows.Forms.ToolStripProfessionalRenderer><br /><br /> <xref:System.Windows.Forms.ToolStripRenderMode><br /><br /> <xref:System.Windows.Forms.ToolStripManagerRenderMode>|  
  
## <a name="toolstrip-design-time-features"></a>Características en tiempo de diseño de ToolStrip  
 La familia de controles <xref:System.Windows.Forms.ToolStrip> proporciona un sofisticado conjunto de herramientas y plantillas para editar y definir localmente los elementos básicos de la interfaz de usuario, de modo que pueda crear rápidamente una aplicación que funcione.  
  
### <a name="task-dialog-boxes"></a>Cuadros de diálogo de tareas  
 En Visual Studio, al hacer clic en la etiqueta inteligente de un control en el diseñador, se muestra una lista de tareas que permite acceder cómodamente a muchos comandos habituales.  
  
-   [Cuadro de diálogo de tareas de MenuStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233645(v=vs.100))  
  
-   [Cuadro de diálogo de tareas de ToolStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233648(v=vs.100))  
  
-   [Cuadro de diálogo de tareas de ContextMenuStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233646(v=vs.100))  
  
-   [Cuadro de diálogo de tareas de StatusStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233642(v=vs.100))  
  
-   [Cuadro de diálogo de tareas de ToolStripContainer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233647(v=vs.100))  
  
### <a name="items-collection-editors"></a>Editores de colecciones de elementos  
 En Visual Studio, al hacer clic en **editar elementos** en la tarea de lista o haga clic en el control y seleccione **editar elementos** en el menú contextual, se muestra el editor de colecciones para el control. Los editores de colecciones le permiten agregar, quitar y reordenar los elementos que contiene el control. También puede ver y cambiar las propiedades del control y los elementos del control.  
  
-   [Editor de colección de elementos MenuStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233625(v=vs.100))  
  
-   [Editor de colección de elementos StatusStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233631(v=vs.100))  
  
-   [Editor de colección de elementos ContextMenuStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233641(v=vs.100))  
  
-   [Editor de colección de elementos de ToolStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100))  
  
## <a name="hosting-controls"></a>Hospedaje de controles  
 La clase <xref:System.Windows.Forms.ToolStripControlHost> proporciona contenedores integrados para los controles <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox> y <xref:System.Windows.Forms.ToolStripProgressBar>. También puede hospedar cualquier otro control existente o COM en un <xref:System.Windows.Forms.ToolStripControlHost>.  
  
 Para obtener un ejemplo de hospedaje de controles, vea [Cómo: Ajustar un Control de Windows Forms con ToolStripControlHost](how-to-wrap-a-windows-forms-control-with-toolstripcontrolhost.md).  
  
## <a name="rendering"></a>Representación  
 Las clases <xref:System.Windows.Forms.ToolStrip> implementan un esquema de representación que es significativamente diferente de otros controles de formularios Windows Forms. Con este esquema, puede aplicar fácilmente estilos y temas.  
  
 Para aplicar un estilo a un <xref:System.Windows.Forms.ToolStrip> y a todos los objetos <xref:System.Windows.Forms.ToolStripItem> que contiene, no es necesario controlar el evento <xref:System.Windows.Forms.ToolStripItem.Paint> de cada elemento, sino que puede establecer la propiedad <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> como uno de los valores <xref:System.Windows.Forms.ToolStripRenderMode> distintos de <xref:System.Windows.Forms.ToolStripRenderMode.Custom>. También puede establecer el <xref:System.Windows.Forms.ToolStrip.Renderer%2A> directamente como cualquier clase que herede de la clase <xref:System.Windows.Forms.ToolStripRenderer>. Al establecer esta propiedad, se establece automáticamente el <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>.  
  
 Puede aplicar el mismo estilo a varios objetos <xref:System.Windows.Forms.ToolStrip> de la misma aplicación estableciendo <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> como <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> y estableciendo la propiedad <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A> o <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> como el <xref:System.Windows.Forms.ToolStripManagerRenderMode> que quiera o el valor <xref:System.Windows.Forms.ToolStripRenderer>, respectivamente.  
  
 Para obtener ejemplos de representación, vea [Cómo: Crear y establecer un representador personalizado para el Control ToolStrip de Windows Forms](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md).  
  
## <a name="styles-and-themes"></a>Estilos y temas  
 <xref:System.Windows.Forms.ToolStrip> y las clases asociadas permiten admitir fácilmente estilos visuales y aspectos personalizados sin necesidad de reemplazar los métodos <xref:System.Windows.Forms.ToolStripItem.OnPaint%2A> de cada elemento. Use <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> y las propiedades <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> y <xref:System.Windows.Forms.ToolStrip.Renderer%2A>.  
  
## <a name="rafting-and-docking"></a>Espacio compartido y acoplamiento  
 Puede ajustar el espacio compartido o acoplar o colocar en posición absoluta los controles <xref:System.Windows.Forms.ToolStrip>. Los elementos <xref:System.Windows.Forms.ToolStrip> se muestran con el <xref:System.Windows.Forms.ToolStrip.LayoutEngine%2A> del contenedor.  
  
 *Espacio compartido* es la capacidad de las barras de herramientas para compartir el espacio horizontal o vertical. Un formulario Windows Forms puede tener un <xref:System.Windows.Forms.ToolStripContainer> que, a su vez, tenga paneles en los lados izquierdo, derecho, superior e inferior del formulario para colocar y compartir el espacio de los controles <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.StatusStrip>. Los diferentes controles <xref:System.Windows.Forms.ToolStrip> se apilan verticalmente si los coloca en el <xref:System.Windows.Forms.ToolStripContainer> izquierdo o derecho. Se apilan horizontalmente si los coloca en el <xref:System.Windows.Forms.ToolStripContainer> superior o inferior. Puede usar el <xref:System.Windows.Forms.ToolStripContentPanel> central del <xref:System.Windows.Forms.ToolStripContainer> para colocar controles tradicionales en el formulario.  
  
 Los controles <xref:System.Windows.Forms.ToolStripContainer> se pueden seleccionar (uno solo o todos ellos) en tiempo de diseño y se pueden eliminar. Los <xref:System.Windows.Forms.ToolStripContainer> se pueden expandir y contraer, y cambian de tamaño con los controles que contienen.  
  
 *Acoplamiento* es la especificación de la ubicación simple de un control en la izquierda, derecha, superior o inferior del formulario.  
  
 La ventaja del espacio compartido frente al acoplamiento es que los controles <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.StatusStrip> pueden compartir el espacio horizontal o vertical con otros controles.  
  
 La mayoría de los controles <xref:System.Windows.Forms.ToolStrip> se puede acoplar al formulario como otros controles en lugar de utilizar el espacio compartido. También puede especificar que un control <xref:System.Windows.Forms.ToolStrip> se sitúe libremente en el formulario quitándolo de su <xref:System.Windows.Forms.ToolStripContainer> y estableciendo su propiedad `Dock` como `None`, o puede especificar su posición absoluta estableciendo la propiedad <xref:System.Windows.Forms.Control.Location%2A> correspondiente. Vea [Cómo: Mover un objeto ToolStrip de un contenedor ToolStripContainer a un formulario](how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form.md).  
  
 Utilice uno o más controles <xref:System.Windows.Forms.ToolStripPanel> para una mayor flexibilidad, especialmente para las aplicaciones de interfaz de múltiples documentos (MDI), o si no necesita <xref:System.Windows.Forms.ToolStripContainer>. Un <xref:System.Windows.Forms.ToolStripPanel> proporciona un espacio acoplable para buscar y compartir el espacio de los controles <xref:System.Windows.Forms.ToolStrip>, pero no los controles tradicionales. De forma predeterminada, el <xref:System.Windows.Forms.ToolStripPanel> no aparece en el diseñador **cuadro de herramientas**, pero puede poner allí haciendo clic con el **cuadro de herramientas**y, a continuación, haga clic en **elegir elementos**. También puede acceder al <xref:System.Windows.Forms.ToolStripPanel> mediante programación, como con cualquier otra clase.  
  
 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.StatusStrip> permiten el desbordamiento de elementos. Es similar al comportamiento de estos elementos en las barras de herramientas de Microsoft Office.  
  
## <a name="see-also"></a>Vea también

- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Arquitectura del control ToolStrip](toolstrip-control-architecture.md)

---
title: 'Cómo: crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
ms.openlocfilehash: 84639a5d49a3fa4a8c6845793c39fc8a67c31e02
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245547"
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a>Cómo: Crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)
Puede mostrar datos relacionados mediante dos o más <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controles para crear un formulario principal-detalle. Por ejemplo, desea mostrar una lista de clientes en uno <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>y cuando el usuario selecciona un cliente, mostrar una lista de los pedidos del cliente en un segundo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
 Puede mostrar datos relacionados arrastrando los elementos de detalle que comparten el mismo nodo de tabla maestra de la **orígenes de datos** ventana hasta un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. Por ejemplo, si tiene un origen de datos que tiene una tabla denominada Customers y una tabla de pedidos relacionada, vea ambas tablas como nodos de nivel superior en la vista de árbol en el **orígenes de datos** ventana. Expanda el nodo de los clientes para que puedan ver las columnas. Tenga en cuenta que la última columna en la lista es un nodo expansible que representa la tabla Orders. Este nodo representa los pedidos relacionados para un cliente.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a>Para mostrar datos relacionados en dos controles DataRepeater  
  
1.  Arrastre dos <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controla desde el **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.  
  
2.  Arrastre los controladores de tamaño y posición para el tamaño de los controles y colocarlos en paralelo.  
  
3.  En el menú **Datos** , haga clic en **Mostrar orígenes de datos**.  
  
    > [!NOTE]
    >  Si el **orígenes de datos** ventana está vacía, agregue un origen de datos a él. Para obtener más información, vea [Agregar nuevos orígenes de datos](/visualstudio/data-tools/add-new-data-sources).  
  
4.  En el **orígenes de datos** ventana, seleccione el nodo de nivel superior de la tabla principal.  
  
5.  Cambie el tipo de colocación de la tabla maestra a detalles haciendo **detalles** en la lista desplegable en el nodo de tabla.  
  
6.  Arrastre el nodo de la tabla maestra a la región de la plantilla de elemento de la primera <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.  
  
7.  Expanda el nodo de la tabla principal y seleccione el nodo de detalle de la tabla relacionada.  
  
8.  Cambie el tipo de colocación de la tabla de detalles a detalles haciendo **detalles** en la lista desplegable en el nodo de tabla.  
  
9. Seleccione este nodo de tabla y arrástrelo a la región de la plantilla de elemento del segundo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Mostrar los datos enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Cómo: Mostrar datos relacionados en una aplicación de Windows Forms](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)

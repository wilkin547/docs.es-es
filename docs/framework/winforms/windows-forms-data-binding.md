---
title: Enlace de datos
description: Obtenga información sobre cómo usar el enlace de datos en Windows Forms para mostrar y realizar cambios en la información de un origen de datos en los controles del formulario.
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
ms.openlocfilehash: 3dfce24147caf9b138916ca8dc3b7a9010439f58
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325547"
---
# <a name="windows-forms-data-binding"></a>Enlace de datos en Windows Forms
El enlace de datos en Windows Forms proporciona los medios para mostrar y realizar cambios en la información de un origen de datos en los controles del formulario. Puede enlazar a orígenes de datos tradicionales y a casi cualquier estructura que contenga datos.  
  
## <a name="in-this-section"></a>En esta sección  
 [Enlace de datos y formularios Windows Forms](data-binding-and-windows-forms.md)  
 Proporciona información general del enlace de datos en Windows Forms.  
  
 [Orígenes de datos compatibles con formularios Windows Forms](data-sources-supported-by-windows-forms.md)  
 Describe los orígenes de datos que se pueden usar con Windows Forms.  
  
 [Interfaces relacionadas con el enlace de datos](interfaces-related-to-data-binding.md)  
 Describe algunas de las interfaces usadas con el enlace de datos de Windows Forms.  
  
 [Procedimiento para desplazarse por los datos en formularios Windows Forms](how-to-navigate-data-in-windows-forms.md)  
 Muestra cómo navegar por los elementos de un origen de datos.  
  
 [Notificación de cambios en el enlace de datos de Windows Forms](change-notification-in-windows-forms-data-binding.md)  
 Describe los diferentes tipos de notificación de cambios para el enlace de datos de Windows Forms.  
  
 [Procedimiento para implementar la interfaz INotifyPropertyChanged](how-to-implement-the-inotifypropertychanged-interface.md)  
 Muestra cómo implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>. La interfaz comunica a un control enlazado los cambios de propiedad en un objeto comercial.  
  
 [Procedimiento para aplicar el patrón PropertyNameChanged](how-to-apply-the-propertynamechanged-pattern.md)  
 Muestra cómo aplicar el patrón *PropertyName*Changed a las propiedades de un control de usuario Windows Forms.  
  
 [Procedimiento para implementar la interfaz ITypedList](how-to-implement-the-itypedlist-interface.md)  
 Muestra cómo habilitar la detección del esquema de una lista enlazable mediante la implementación de la interfaz <xref:System.ComponentModel.ITypedList>.  
  
 [Procedimiento para implementar la interfaz IListSource](how-to-implement-the-ilistsource-interface.md)  
 Muestra cómo la implementación de la interfaz <xref:System.ComponentModel.IListSource> para crear una clase enlazable no implementa <xref:System.Collections.IList>, sino que proporciona una lista de otra ubicación.  
  
 [Procedimiento para garantizar que varios controles enlazados al mismo origen de datos permanezcan sincronizados](multiple-controls-bound-to-data-source-synchronized.md)  
 Muestra cómo controlar el evento <xref:System.Windows.Forms.BindingSource.BindingComplete> para asegurarse de que todos los controles enlazados a un origen de datos permanezcan sincronizados.  
  
 [Procedimiento para garantizar que la fila seleccionada de una tabla secundaria conserve la posición correcta](ensure-the-selected-row-in-a-child-table-correct.md)  
 Muestra cómo asegurarse de que no cambie la fila seleccionada de una tabla secundaria cuando se realice un cambio en un campo de la tabla primaria.  
  
 Vea también [interfaces relacionadas con el enlace de datos](interfaces-related-to-data-binding.md), [Cómo: navegar por los datos en Windows Forms](how-to-navigate-data-in-windows-forms.md)y [Cómo: crear un control de enlace simple en Windows Forms](how-to-create-a-simple-bound-control-on-a-windows-form.md).  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 Describe la clase que representa el enlace entre un componente enlazable y un origen de datos.  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 Describe la clase que encapsula un origen de datos para el enlace a controles.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Componente BindingSource](./controls/bindingsource-component.md)  
 Contiene una lista de los temas que muestran cómo usar el componente <xref:System.Windows.Forms.BindingSource>.  
  
 [Control DataGridView](./controls/datagridview-control-windows-forms.md)  
 Proporciona una lista de temas que muestran cómo usar un control datagrid enlazable.  
  
 Vea también el [acceso a los datos en Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).

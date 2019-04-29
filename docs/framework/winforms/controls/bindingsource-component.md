---
title: Componente BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], Windows Forms
- Windows Forms, data binding control
- BindingSource component [Windows Forms]
ms.assetid: 3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9
ms.openlocfilehash: 54639edb512a8bc6c5909282d5e4c210439e2a6e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683423"
---
# <a name="bindingsource-component"></a>Componente BindingSource
Encapsula un origen de datos para el enlace a controles.  
  
 El componente <xref:System.Windows.Forms.BindingSource> sirve para dos propósitos. Primero, proporciona una capa de direccionamiento indirecto cuando los controles de un formulario se enlazan a datos. Esto se logra enlazando el componente <xref:System.Windows.Forms.BindingSource> a su origen de datos y, después, enlazando los controles del formulario al componente <xref:System.Windows.Forms.BindingSource>. Toda interacción posterior con los datos, incluida la navegación, la ordenación, el filtrado y la actualización, se lleva a cabo mediante llamadas al componente <xref:System.Windows.Forms.BindingSource>.  
  
 Segundo, el componente <xref:System.Windows.Forms.BindingSource> puede actuar como un origen de datos fuertemente tipados. Al agregar un tipo al componente <xref:System.Windows.Forms.BindingSource> con el método <xref:System.Windows.Forms.BindingSource.Add%2A> se crea una lista de ese tipo.  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre el componente BindingSource](bindingsource-component-overview.md)  
 Presenta los conceptos generales del componente <xref:System.Windows.Forms.BindingSource>, que permite enlazar un origen de datos a un control.  
  
 [Cómo: Enlazar controles de formularios Windows Forms a valores de la base de datos DBNull](how-to-bind-windows-forms-controls-to-dbnull-database-values.md)  
 Muestra cómo controlar un valor <xref:System.DBNull> desde el origen de datos mediante el componente <xref:System.Windows.Forms.BindingSource>.  
  
 [Cómo: Ordenar y filtrar datos ADO.NET con el Windows Forms BindingSource (componente)](sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)  
 Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> para aplicar ordenaciones y filtros a los datos mostrados.  
  
 [Cómo: Enlazar a un servicio Web mediante el componente BindingSource de formularios de Windows](how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource.md)  
 Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> para enlazar a un servicio Web.  
  
 [Cómo: Controlar errores y excepciones que se producen con el enlace de datos](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> para controlar correctamente los errores que ocurren en una operación de enlace de datos.  
  
 [Cómo: Enlazar un Control de Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md)  
 Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para enlazar a un tipo.  
  
 [Cómo: Enlazar un Control de Windows Forms a un objeto Factory](how-to-bind-a-windows-forms-control-to-a-factory-object.md)  
 Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para enlazar a un objeto o método de generador.  
  
 [Cómo: Personalizar elemento con el componente BindingSource de Windows Forms](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)  
 Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para crear nuevos elementos y agregarlos a un origen de datos.  
  
 [Cómo: Provocar notificaciones de cambios mediante el método BindingSource ResetItem](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)  
 Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para generar eventos de notificación de cambios para orígenes de datos que no admiten la notificación de cambios.  
  
 [Cómo: Provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged](raise-change-notifications--bindingsource.md)  
 Muestra cómo usar un tipo que hereda de la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> con un control <xref:System.Windows.Forms.BindingSource>.  
  
 [Cómo: Reflejar las actualizaciones del origen de datos en un Control de Windows Forms con BindingSource](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)  
 Muestra cómo responder a los cambios en el origen de datos mediante el componente <xref:System.Windows.Forms.BindingSource>.  
  
 [Cómo: Compartir datos enlazados entre formularios mediante el componente BindingSource](how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> enlazar varios formularios al mismo origen de datos.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.BindingSource>  
 Proporciona documentación de referencia para el componente <xref:System.Windows.Forms.BindingSource>.  
  
 <xref:System.Windows.Forms.BindingNavigator>  
 Proporciona documentación de referencia para el control <xref:System.Windows.Forms.BindingNavigator>.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Enlace de datos en Windows Forms](../windows-forms-data-binding.md)  
 Contiene vínculos a temas que describen la arquitectura de enlace de datos de Windows Forms.  
  
 Vea también [Enlazar controles a los datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).

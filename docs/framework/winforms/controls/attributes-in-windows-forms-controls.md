---
title: Atributos en controles
ms.date: 03/30/2017
helpviewer_keywords:
- attributes [Windows Forms]
- attributes [Windows Forms], data binding properties
- attributes [Windows Forms], control properties
- attributes [Windows Forms], classes
ms.assetid: 2c5640e9-6c6c-49d7-a5e4-a768f6be7853
ms.openlocfilehash: b32e4f87e953438a3bb11569445a9270e11c7922
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732134"
---
# <a name="attributes-in-windows-forms-controls"></a>Atributos en controles de Windows Forms
.NET Framework proporciona una variedad de atributos que puede aplicar a los miembros de sus controles y componentes personalizados. Algunos de estos atributos afectan al comportamiento en tiempo de ejecución de una clase y otros afectan al comportamiento en tiempo de diseño.  
  
## <a name="attributes-for-control-and-component-properties"></a>Atributos para las propiedades de controles y componentes  
 En la tabla siguiente se muestran los atributos que se pueden aplicar a las propiedades o a otros miembros de los controles y componentes personalizados. Para obtener un ejemplo que utiliza muchos de estos atributos, vea [Cómo: Aplicar atributos en controles de Windows Forms](how-to-apply-attributes-in-windows-forms-controls.md).  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|<xref:System.ComponentModel.AmbientValueAttribute>|Especifica el valor para pasar a una propiedad que hace que esta obtenga su valor de otro origen. Esto se conoce como *ambiente*.|  
|<xref:System.ComponentModel.BrowsableAttribute>|Especifica si una propiedad o un evento se debería mostrar en una ventana **Propiedades**.|  
|<xref:System.ComponentModel.CategoryAttribute>|Especifica el nombre de la categoría en la que se va a agrupar la propiedad o el evento cuando se muestra en un control de <xref:System.Windows.Forms.PropertyGrid> establecido en el modo de <xref:System.Windows.Forms.PropertySort.Categorized>.|  
|<xref:System.ComponentModel.DefaultValueAttribute>|Especifica el valor predeterminado de una propiedad.|  
|<xref:System.ComponentModel.DescriptionAttribute>|Especifica una descripción para una propiedad o evento.|  
|<xref:System.ComponentModel.DisplayNameAttribute>|Especifica el nombre para mostrar de una propiedad, evento o método `public void` que no toma ningún argumento.|  
|<xref:System.ComponentModel.EditorAttribute>|Especifica el editor que se va a utilizar para cambiar una propiedad.|  
|<xref:System.ComponentModel.EditorBrowsableAttribute>|Especifica que una propiedad o un método son visibles en un editor.|  
|<xref:System.ComponentModel.Design.HelpKeywordAttribute>|Especifica la palabra clave de contexto para una clase o miembro.|  
|<xref:System.ComponentModel.LocalizableAttribute>|Especifica si se debería localizar una propiedad.|  
|<xref:System.ComponentModel.PasswordPropertyTextAttribute>|Indica los caracteres que ocultan la representación del texto de un objeto, como asteriscos.|  
|<xref:System.ComponentModel.ReadOnlyAttribute>|Especifica si la propiedad a la que se enlaza este atributo es de solo lectura o de lectura y escritura en tiempo de diseño.|  
|<xref:System.ComponentModel.RefreshPropertiesAttribute>|Indica que la cuadrícula de la propiedad debería actualizarse cuando cambia el valor de propiedad asociado.|  
|<xref:System.ComponentModel.TypeConverterAttribute>|Especifica el tipo que se debe utilizar como convertidor para el objeto al que está enlazado este atributo.|  
  
## <a name="attributes-for-data-binding-properties"></a>Atributos para las propiedades de enlaces de datos  
 En la tabla siguiente se muestran los atributos que se pueden aplicar para especificar cómo los controles y componentes personalizados interactúan con enlace de datos.  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|<xref:System.ComponentModel.BindableAttribute>|Especifica si una propiedad se utiliza normalmente para enlace.|  
|<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|Especifica las propiedades del origen de datos y del miembro de datos para un componente.|  
|<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|Especifica la propiedad de enlace predeterminada para un componente.|  
|<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|Especifica las propiedades del origen de datos y del miembro de datos para un componente.|  
|<xref:System.ComponentModel.AttributeProviderAttribute>|Habilita la redirección del atributo.|  
  
## <a name="attributes-for-classes"></a>Atributos para las clases  
 En la tabla siguiente se muestran los atributos que se pueden aplicar para especificar en tiempo de diseño el comportamiento de los controles y componentes personalizados.  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|<xref:System.ComponentModel.DefaultEventAttribute>|Especifica el evento predeterminado para un componente.|  
|<xref:System.ComponentModel.DefaultPropertyAttribute>|Especifica la propiedad predeterminada para un componente.|  
|<xref:System.ComponentModel.DesignerAttribute>|Especifica la clase utilizada para implementar, en tiempo de diseño, los servicios para un componente.|  
|<xref:System.ComponentModel.DesignerCategoryAttribute>|Especifica que el diseñador de una clase pertenece a una categoría determinada.|  
|<xref:System.ComponentModel.ToolboxItemAttribute>|Representa un atributo de un elemento del cuadro de herramientas.|  
|<xref:System.ComponentModel.ToolboxItemFilterAttribute>|Especifica la cadena del filtro y el tipo de filtro que se va a utilizar para un elemento del cuadro de herramientas.|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Attribute>
- [Aplicar atributos en controles de Windows Forms](how-to-apply-attributes-in-windows-forms-controls.md)
- [Ampliar compatibilidad en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))
- [Desarrollar controles personalizados de Windows Forms con .NET Framework](developing-custom-windows-forms-controls.md)

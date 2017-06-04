---
title: "Atributos en controles de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "atributos [Windows Forms]"
  - "atributos [Windows Forms], clases"
  - "atributos [Windows Forms], propiedades de control"
  - "atributos [Windows Forms], propiedades de enlace de datos"
ms.assetid: 2c5640e9-6c6c-49d7-a5e4-a768f6be7853
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Atributos en controles de formularios Windows Forms
.NET Framework proporciona una variedad de atributos que puede aplicar a los miembros de sus controles y componentes personalizados.  Algunos de estos atributos afectan al comportamiento en tiempo de ejecución de una clase y otros afectan al comportamiento en tiempo de diseño.  
  
## Atributos para las propiedades de controles y componentes  
 En la tabla siguiente se muestran los atributos que se pueden aplicar a las propiedades o a otros miembros de los controles y componentes personalizados.  Para obtener un ejemplo que utiliza muchos de estos atributos, vea [Cómo: Aplicar atributos en controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|<xref:System.ComponentModel.AmbientValueAttribute>|Especifica el valor para pasar a una propiedad que hace que la propiedad obtenga su valor de otro origen.  Esto se conoce como *ambiente*.|  
|<xref:System.ComponentModel.BrowsableAttribute>|Especifica si una propiedad o evento se debería mostrar en una ventana **Propiedades**.|  
|<xref:System.ComponentModel.CategoryAttribute>|Especifica el nombre de la categoría donde se va a agrupar la propiedad o evento cuando se muestre en un control <xref:System.Windows.Forms.PropertyGrid> establecido en modo <xref:System.Windows.Forms.PropertySort>.|  
|<xref:System.ComponentModel.DefaultValueAttribute>|Especifica el valor predeterminado para una propiedad.|  
|<xref:System.ComponentModel.DescriptionAttribute>|Especifica una descripción para una propiedad o evento.|  
|<xref:System.ComponentModel.DisplayNameAttribute>|Especifica el nombre para mostrar de una propiedad, evento o método `public``void` que no toma ningún argumento.|  
|<xref:System.ComponentModel.EditorAttribute>|Especifica el editor que se va a utilizar para cambiar una propiedad.|  
|<xref:System.ComponentModel.EditorBrowsableAttribute>|Especifica que una propiedad o método es visible en un editor.|  
|<xref:System.ComponentModel.Design.HelpKeywordAttribute>|Especifica la palabra clave de contexto para una clase o miembro.|  
|<xref:System.ComponentModel.LocalizableAttribute>|Especifica si se debería localizar una propiedad.|  
|<xref:System.ComponentModel.PasswordPropertyTextAttribute>|Indica los caracteres que ocultan la representación del texto de un objeto, como asteriscos.|  
|<xref:System.ComponentModel.ReadOnlyAttribute>|Especifica si la propiedad a la que se enlaza este atributo es de sólo lectura o de lectura y escritura en tiempo de diseño.|  
|<xref:System.ComponentModel.RefreshPropertiesAttribute>|Indica que la cuadrícula de la propiedad debería actualizarse cuando cambia el valor de propiedad asociado.|  
|<xref:System.ComponentModel.TypeConverterAttribute>|Especifica qué tipo utilizar como convertidor para el objeto al que está enlazado este atributo.|  
  
## Atributos para las propiedades de enlaces de datos  
 En la tabla siguiente se muestran los atributos que se pueden aplicar para especificar cómo los controles y componentes personalizados interactúan con enlace de datos.  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|<xref:System.ComponentModel.BindableAttribute>|Especifica si una propiedad se utiliza normalmente para enlace.|  
|<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|Especifica las propiedades del origen de datos y del miembro de datos para un componente.|  
|<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|Especifica la propiedad de enlace predeterminada para un componente.|  
|<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|Especifica las propiedades del origen de datos y del miembro de datos para un componente.|  
|<xref:System.ComponentModel.AttributeProviderAttribute>|Habilita la redirección del atributo.|  
  
## Atributos para las clases  
 En la tabla siguiente se muestran los atributos que se pueden aplicar para especificar en tiempo de diseño el comportamiento de los controles y componentes personalizados.  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|<xref:System.ComponentModel.DefaultEventAttribute>|Especifica el evento predeterminado del componente.|  
|<xref:System.ComponentModel.DefaultPropertyAttribute>|Especifica la propiedad predeterminada del componente.|  
|<xref:System.ComponentModel.DesignerAttribute>|Especifica la clase utilizada para implementar, en tiempo de diseño, los servicios para un componente.|  
|<xref:System.ComponentModel.DesignerCategoryAttribute>|Especifica que el diseñador de una clase pertenece a una categoría determinada.|  
|<xref:System.ComponentModel.ToolboxItemAttribute>|Representa un atributo de un elemento del cuadro de herramientas.|  
|<xref:System.ComponentModel.ToolboxItemFilterAttribute>|Especifica la cadena del filtro y el tipo de filtro que se va a utilizar para un elemento del cuadro de herramientas.|  
  
## Vea también  
 <xref:System.Attribute>   
 [Cómo: Aplicar atributos en controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)   
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)   
 [Desarrollar controles personalizados de formularios Windows Forms con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
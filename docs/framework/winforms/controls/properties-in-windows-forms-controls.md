---
title: Propiedades de los controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
ms.openlocfilehash: 37db3f16a17acc7f3a6e594bd284ba368801e70a
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43867912"
---
# <a name="properties-in-windows-forms-controls"></a>Propiedades de los controles de formularios Windows Forms
Un control de Windows Forms hereda muchas formulario de propiedades de la clase base <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Estos incluyen propiedades como <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>y muchos otros. Para obtener más información acerca de las propiedades heredadas, vea <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
 Se pueden reemplazar las propiedades heredadas en un control, así como definir propiedades nuevas.  
  
## <a name="in-this-section"></a>En esta sección  
 [Definir una propiedad](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 Muestra cómo implementar una propiedad para un control o componente personalizado y cómo integrar la propiedad en el entorno de diseño.  
  
 [Definir valores predeterminados con los métodos ShouldSerialize y Reset](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 Muestra cómo definir valores de propiedad predeterminados de un control o componente personalizado.  
  
 [Eventos de cambio de propiedades](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 Describe cómo habilitar notificaciones de cambio de propiedad cuando cambia un valor de propiedad.  
  
 [Cómo: Exponer propiedades de controles constituyentes](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md)  
 Muestra cómo exponer propiedades de controles constituyentes en un control compuesto personalizado.  
  
 [Implementación de métodos en controles personalizados](../../../../docs/framework/winforms/controls/method-implementation-in-custom-controls.md)  
 Describe cómo implementar métodos en controles y componentes personalizados.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.UserControl>  
 Documenta la clase base para implementar controles compuestos.  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 Documenta el atributo que especifica el <xref:System.ComponentModel.TypeConverter> que se usará para un tipo de propiedad personalizada.  
  
 <xref:System.ComponentModel.EditorAttribute>  
 Documenta el atributo que especifica el <xref:System.Drawing.Design.UITypeEditor> que se usará para una propiedad personalizada.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Atributos en controles de Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 Describe los atributos que se puede aplicar a propiedades u otros miembros de los controles y componentes personalizados.  
  
 [Atributos en tiempo de diseño para componentes](https://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3)  
 Enumera los atributos de metadatos que se deben aplicar a componentes y controles para que se muestren correctamente en tiempo de diseño en diseñadores visuales.  
  
 [Ampliar compatibilidad en tiempo de diseño](https://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 Describe cómo implementar clases, como editores y diseñadores, que proporcionan compatibilidad en tiempo de diseño.

---
title: Propiedades de los controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
ms.openlocfilehash: e531b80cffabb94d2589383936a425b740c9cc07
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012515"
---
# <a name="properties-in-windows-forms-controls"></a>Propiedades de los controles de formularios Windows Forms
Un control de Windows Forms hereda muchas formulario de propiedades de la clase base <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Estos incluyen propiedades como <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>y muchos otros. Para obtener más información acerca de las propiedades heredadas, vea <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
 Se pueden reemplazar las propiedades heredadas en un control, así como definir propiedades nuevas.  
  
## <a name="in-this-section"></a>En esta sección  
 [Definir una propiedad](defining-a-property-in-windows-forms-controls.md)  
 Muestra cómo implementar una propiedad para un control o componente personalizado y cómo integrar la propiedad en el entorno de diseño.  
  
 [Definir valores predeterminados con los métodos ShouldSerialize y Reset](defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 Muestra cómo definir valores de propiedad predeterminados de un control o componente personalizado.  
  
 [Eventos de cambio de propiedades](property-changed-events.md)  
 Describe cómo habilitar notificaciones de cambio de propiedad cuando cambia un valor de propiedad.  
  
 [Cómo: Exponer propiedades de controles constituyentes](how-to-expose-properties-of-constituent-controls.md)  
 Muestra cómo exponer propiedades de controles constituyentes en un control compuesto personalizado.  
  
 [Implementación de métodos en controles personalizados](method-implementation-in-custom-controls.md)  
 Describe cómo implementar métodos en controles y componentes personalizados.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.UserControl>  
 Documenta la clase base para implementar controles compuestos.  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 Documenta el atributo que especifica el <xref:System.ComponentModel.TypeConverter> que se usará para un tipo de propiedad personalizada.  
  
 <xref:System.ComponentModel.EditorAttribute>  
 Documenta el atributo que especifica el <xref:System.Drawing.Design.UITypeEditor> que se usará para una propiedad personalizada.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Atributos en controles de Windows Forms](attributes-in-windows-forms-controls.md)  
 Describe los atributos que se puede aplicar a propiedades u otros miembros de los controles y componentes personalizados.  
  
 [Atributos en tiempo de diseño para componentes](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))  
 Enumera los atributos de metadatos que se deben aplicar a componentes y controles para que se muestren correctamente en tiempo de diseño en diseñadores visuales.  
  
 [Ampliar compatibilidad en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))  
 Describe cómo implementar clases, como editores y diseñadores, que proporcionan compatibilidad en tiempo de diseño.

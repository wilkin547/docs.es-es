---
title: Procedimiento para proporcionar un fondo transparente a un control
ms.date: 03/30/2017
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
ms.openlocfilehash: 671075973793d7fbf0b70ce77428a0a632305b9c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206101"
---
# <a name="how-to-give-your-control-a-transparent-background"></a>Procedimiento para proporcionar un fondo transparente a un control
En versiones anteriores de .NET Framework, los controles no admitían la opción de establecer fondos transparentes sin establecer primero el método <xref:System.Windows.Forms.Control.SetStyle%2A> en el constructor de formularios. En la versión actual de .NET Framework, el color de fondo de la mayoría de los controles se puede establecer como <xref:System.Drawing.Color.Transparent%2A> en la ventana **Propiedades** durante el tiempo de diseño o como código en el constructor del formulario.  
  
> [!NOTE]
>  Los controles de Windows Forms no admiten una transparencia real. El fondo de un control de Windows Forms transparente lo pinta su control primario.  
  
> [!NOTE]
>  El control <xref:System.Windows.Controls.Button> no admite un color de fondo transparente incluso si la propiedad <xref:System.Windows.Forms.ButtonBase.BackColor%2A> se estableció como <xref:System.Drawing.Color.Transparent%2A>.  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a>Proporcionar un fondo transparente a un control  
  
-   En la ventana Propiedades, elija la propiedad <xref:System.Windows.Forms.ButtonBase.BackColor%2A> y establézcala como <xref:System.Drawing.Color.Transparent%2A>  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Color.FromArgb%2A>
- [Desarrollar controles personalizados de Windows Forms con .NET Framework](developing-custom-windows-forms-controls.md)
- [Using Managed Graphics Classes](../advanced/using-managed-graphics-classes.md) (Usar clases gráficas administradas)
- [Cómo: Dibujar líneas opacas y semitransparentes](../advanced/how-to-draw-opaque-and-semitransparent-lines.md)

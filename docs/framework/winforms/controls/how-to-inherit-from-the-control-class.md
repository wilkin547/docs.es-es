---
title: 'Cómo: Heredar de una clase de control'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
ms.openlocfilehash: 1a0eea1930699ed85fcf0eaf184ba0aabe398d73
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46002702"
---
# <a name="how-to-inherit-from-the-control-class"></a>Cómo: Heredar de una clase de control
Si desea crear un control completamente personalizado para usar en un formulario de Windows, debe heredar la <xref:System.Windows.Forms.Control> clase. Al heredar el <xref:System.Windows.Forms.Control> clase requiere que realice más planeación e implementación, también proporciona con la mayor variedad de opciones. Al heredar de <xref:System.Windows.Forms.Control>, hereda la funcionalidad básica que hace funcionar los controles. La funcionalidad inherente a la <xref:System.Windows.Forms.Control> clase controla la entrada de usuario a través del teclado y mouse, define los límites y el tamaño del control, proporciona un identificador de windows y proporciona seguridad y control de mensajes. No incorpora ningún dibujo, que en este caso es la representación real de la interfaz gráfica del control, ni cualquier funcionalidad de interacción de usuario específico. Debe proporcionar todos estos elementos por medio del código personalizado.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-custom-control"></a>Para crear un color personalizado  
  
1.  Cree un nuevo proyecto **Aplicación Windows** o **Biblioteca de controles de Windows**.  
  
2.  En el menú **Proyecto**, elija **Agregar clase**.  
  
3.  En el cuadro de diálogo **Agregar nuevo elemento**, haga clic en **Control personalizado**.  
  
     Se agrega un nuevo control personalizado al proyecto.  
  
4.  Presione F7 para abrir el **Editor de código** para el control personalizado.  
  
5.  Busque el <xref:System.Windows.Forms.Control.OnPaint%2A> método, que estará vacío salvo por una llamada a la <xref:System.Windows.Forms.Control.OnPaint%2A> método de la clase base.  
  
6.  Modifique el código para incorporar el dibujo personalizado que desee para su control.  
  
     Para información sobre cómo escribir código para representar gráficos para los controles, vea [Dibujo y representación personalizados de controles](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
7.  Implemente los métodos, propiedades o eventos personalizados que vaya a incorporar el control.  
  
8.  Guarde y pruebe el control.  
  
## <a name="see-also"></a>Vea también  
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [cómo: Heredar de la clase UserControl](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [Cómo: Heredar de controles de Windows Forms existentes](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [Cómo: Crear controles para Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [Solucionar problemas de controladores de eventos heredados en Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [Desarrollar controles de Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)

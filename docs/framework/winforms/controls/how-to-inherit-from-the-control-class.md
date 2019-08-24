---
title: Procedimiento para heredar de la clase Control
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 02c40e310778bd476742f62ee8b9d8598b084a53
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015854"
---
# <a name="how-to-inherit-from-the-control-class"></a>Procedimiento para heredar de la clase Control

Si desea crear un control completamente personalizado para usarlo en Windows Forms, debe heredar de la <xref:System.Windows.Forms.Control> clase. Aunque la herencia de la <xref:System.Windows.Forms.Control> clase requiere que realice más planeación e implementación, también proporciona el mayor número de opciones. Al heredar de <xref:System.Windows.Forms.Control>, se hereda la funcionalidad muy básica que hace que los controles funcionen. La funcionalidad inherente en la <xref:System.Windows.Forms.Control> clase controla los datos proporcionados por el usuario a través del teclado y el mouse, define los límites y el tamaño del control, proporciona un identificador de Windows y proporciona seguridad y control de mensajes. No incorpora ningún dibujo, que en este caso es la representación real de la interfaz gráfica del control, ni cualquier funcionalidad de interacción de usuario específico. Debe proporcionar todos estos elementos por medio del código personalizado.

## <a name="to-create-a-custom-control"></a>Para crear un color personalizado

1. En Visual Studio, cree una nueva **aplicación de Windows** o un proyecto de **biblioteca de controles de Windows** .

2. En el menú **Proyecto**, elija **Agregar clase**.

3. En el cuadro de diálogo **Agregar nuevo elemento**, haga clic en **Control personalizado**.

   Se agrega un nuevo control personalizado al proyecto.

4. Presione **F7** para abrir el **Editor de código** para el control personalizado.

5. Busque el <xref:System.Windows.Forms.Control.OnPaint%2A> método, que estará vacío excepto para una llamada <xref:System.Windows.Forms.Control.OnPaint%2A> al método de la clase base.

6. Modifique el código para incorporar el dibujo personalizado que desee para su control.

   Para información sobre cómo escribir código para representar gráficos para los controles, vea [Dibujo y representación personalizados de controles](custom-control-painting-and-rendering.md).

7. Implemente los métodos, propiedades o eventos personalizados que vaya a incorporar el control.

8. Guarde y pruebe el control.

## <a name="see-also"></a>Vea también

- [Variedades de controles personalizados](varieties-of-custom-controls.md)
- [Cómo: Heredar de la clase UserControl](how-to-inherit-from-the-usercontrol-class.md)
- [Cómo: Heredar de controles de Windows Forms existentes](how-to-inherit-from-existing-windows-forms-controls.md)
- [Procedimientos: Controles de autor para Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Solucionar problemas de controladores de eventos heredados en Visual Basic](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Desarrollar controles de Windows Forms en tiempo de diseño](developing-windows-forms-controls-at-design-time.md)

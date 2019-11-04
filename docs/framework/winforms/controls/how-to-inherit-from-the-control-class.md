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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7af7d1fe8f14c71dfc90836d84023b98feb44961
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458384"
---
# <a name="how-to-inherit-from-the-control-class"></a>Cómo: Heredar de una clase de control

Si desea crear un control completamente personalizado para usarlo en Windows Forms, debe heredar de la clase <xref:System.Windows.Forms.Control>. Aunque la herencia de la clase <xref:System.Windows.Forms.Control> requiere que realice más planeación e implementación, también proporciona la mayor variedad de opciones. Al heredar de <xref:System.Windows.Forms.Control>, hereda la funcionalidad muy básica que hace que los controles funcionen. La funcionalidad inherente en la clase <xref:System.Windows.Forms.Control> controla los datos proporcionados por el usuario a través del teclado y el mouse, define los límites y el tamaño del control, proporciona un identificador de Windows y proporciona seguridad y control de los mensajes. No incorpora ningún dibujo, que en este caso es la representación real de la interfaz gráfica del control, ni cualquier funcionalidad de interacción de usuario específico. Debe proporcionar todos estos elementos por medio del código personalizado.

## <a name="to-create-a-custom-control"></a>Para crear un color personalizado

1. En Visual Studio, cree una nueva **aplicación de Windows** o un proyecto de **biblioteca de controles de Windows** .

2. En el menú **Proyecto**, elija **Agregar clase**.

3. En el cuadro de diálogo **Agregar nuevo elemento**, haga clic en **Control personalizado**.

   Se agrega un nuevo control personalizado al proyecto.

4. Presione **F7** para abrir el **Editor de código** para el control personalizado.

5. Busque el método <xref:System.Windows.Forms.Control.OnPaint%2A>, que estará vacío excepto para una llamada al método <xref:System.Windows.Forms.Control.OnPaint%2A> de la clase base.

6. Modifique el código para incorporar el dibujo personalizado que desee para su control.

   Para información sobre cómo escribir código para representar gráficos para los controles, vea [Dibujo y representación personalizados de controles](custom-control-painting-and-rendering.md).

7. Implemente los métodos, propiedades o eventos personalizados que vaya a incorporar el control.

8. Guarde y pruebe el control.

## <a name="see-also"></a>Vea también

- [Variedades de controles personalizados](varieties-of-custom-controls.md)
- [Cómo: Heredar de una clase UserControl](how-to-inherit-from-the-usercontrol-class.md)
- [Cómo: Heredar de controles de Windows Forms existentes](how-to-inherit-from-existing-windows-forms-controls.md)
- [Cómo: Crear controles de Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Solucionar problemas de controladores de eventos heredados en Visual Basic](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Desarrollar controles de Windows Forms en tiempo de diseño](developing-windows-forms-controls-at-design-time.md)

---
title: Procedimiento para heredar de la clase UserControl
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7f4055c2374103b7df941d9a9bef24ed5e6cb27c
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015840"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a>Procedimiento para heredar de la clase UserControl

Para combinar la funcionalidad de uno o más controles de Windows Forms con código personalizado, puede crear un *control de usuario*. Los controles de usuario combinan el desarrollo rápido de controles, la funcionalidad de los controles de Windows Forms estándar y la versatilidad de los métodos y las propiedades personalizados. Al comenzar a crear un control de usuario, se le presentará un diseñador visible en el que puede colocar los controles de Windows Forms estándar. Estos controles conservan toda su funcionalidad inherente, así como la apariencia y el comportamiento (apariencia) de los controles estándar. Una vez que estos controles están integrados en el control de usuario, dejan de estar disponibles en el código. El control de usuario realiza su propio dibujo y controla también toda la funcionalidad básica asociada a los controles.

## <a name="to-create-a-user-control"></a>Crear un control de usuario

1. Cree un nuevo proyecto de **biblioteca de controles de Windows** en Visual Studio.

   Se crea un nuevo proyecto con un control de usuario en blanco.

2. Arrastre controles desde la pestaña **Windows Forms** de **Cuadro de herramientas** en el diseñador.

3. Estos controles deben estar situados y diseñados como desee que aparezcan en el control de usuario final. Si desea permitir a los desarrolladores tener acceso a los controles constituyentes, deberá declararlos públicos o exponer de forma selectiva las propiedades del control constituyente. Para obtener más detalles, vea [Cómo: Exponga las propiedades de los](how-to-expose-properties-of-constituent-controls.md)controles constituyentes.

4. Implemente los métodos o propiedades personalizados que vaya a incorporar el control.

5. Presione **F5** para compilar el proyecto y ejecutar el control en **UserControl Test Container**. Para obtener más información, consulte [Cómo Pruebe el comportamiento en tiempo de ejecución de un](how-to-test-the-run-time-behavior-of-a-usercontrol.md)control UserControl.

## <a name="see-also"></a>Vea también

- [Variedades de controles personalizados](varieties-of-custom-controls.md)
- [Cómo: Heredar de la clase control](how-to-inherit-from-the-control-class.md)
- [Cómo: Heredar de controles de Windows Forms existentes](how-to-inherit-from-existing-windows-forms-controls.md)
- [Cómo: Controles de autor para Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Solucionar problemas de controladores de eventos heredados en Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Cómo: Probar el comportamiento en tiempo de ejecución de un control UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

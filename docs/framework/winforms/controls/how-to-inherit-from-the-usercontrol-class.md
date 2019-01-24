---
title: Procedimiento Heredar de la clase UserControl
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
ms.openlocfilehash: 4c3f3d6775f3fdf511e59b360d6c356e2d4fabee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532102"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a>Procedimiento Heredar de la clase UserControl
Para combinar la funcionalidad de uno o más controles de Windows Forms con código personalizado, puede crear un *control de usuario*. Los controles de usuario combinan el desarrollo rápido de controles, la funcionalidad de los controles de Windows Forms estándar y la versatilidad de los métodos y las propiedades personalizados. Al comenzar a crear un control de usuario, se le presentará un diseñador visible en el que puede colocar los controles de Windows Forms estándar. Estos controles conservan toda su funcionalidad inherente, así como la apariencia y el comportamiento (apariencia) de los controles estándar. Una vez que estos controles están integrados en el control de usuario, dejan de estar disponibles en el código. El control de usuario realiza su propio dibujo y controla también toda la funcionalidad básica asociada a los controles.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-user-control"></a>Crear un control de usuario  
  
1.  Cree un nuevo proyecto de tipo **Biblioteca de controles de Windows**.  
  
     Se crea un nuevo proyecto con un control de usuario en blanco.  
  
2.  Arrastre controles desde la pestaña **Windows Forms** de **Cuadro de herramientas** en el diseñador.  
  
3.  Estos controles deben estar situados y diseñados como desee que aparezcan en el control de usuario final. Si desea permitir a los desarrolladores tener acceso a los controles constituyentes, deberá declararlos públicos o exponer de forma selectiva las propiedades del control constituyente. Para obtener más información, vea [Cómo: Exponer propiedades de controles constituyentes](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md).  
  
4.  Implemente los métodos o propiedades personalizados que vaya a incorporar el control.  
  
5.  Presione F5 para compilar el proyecto y ejecutar el control en **UserControl Test Container**. Para obtener más información, vea [Cómo: Probar el comportamiento de tiempo de ejecución de una clase UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
## <a name="see-also"></a>Vea también
- [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
- [Cómo: Heredar de la clase de Control](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)
- [Cómo: Heredar de Windows existente controles de formularios](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)
- [Cómo: Crear controles de Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)
- [Solucionar problemas de controladores de eventos heredados en Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Cómo: Probar el comportamiento de tiempo de ejecución de una clase UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)

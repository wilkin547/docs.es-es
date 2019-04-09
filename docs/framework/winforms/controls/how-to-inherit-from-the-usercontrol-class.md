---
title: Filtrar para heredar de la clase UserControl
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
ms.openlocfilehash: 1b5d69bda08b94ae00ce022d0d323ad4561ff6b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174803"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a>Filtrar para heredar de la clase UserControl
Para combinar la funcionalidad de uno o más controles de Windows Forms con código personalizado, puede crear un *control de usuario*. Los controles de usuario combinan el desarrollo rápido de controles, la funcionalidad de los controles de Windows Forms estándar y la versatilidad de los métodos y las propiedades personalizados. Al comenzar a crear un control de usuario, se le presentará un diseñador visible en el que puede colocar los controles de Windows Forms estándar. Estos controles conservan toda su funcionalidad inherente, así como la apariencia y el comportamiento (apariencia) de los controles estándar. Una vez que estos controles están integrados en el control de usuario, dejan de estar disponibles en el código. El control de usuario realiza su propio dibujo y controla también toda la funcionalidad básica asociada a los controles.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-user-control"></a>Crear un control de usuario  
  
1.  Cree un nuevo proyecto de tipo **Biblioteca de controles de Windows**.  
  
     Se crea un nuevo proyecto con un control de usuario en blanco.  
  
2.  Arrastre controles desde la pestaña **Windows Forms** de **Cuadro de herramientas** en el diseñador.  
  
3.  Estos controles deben estar situados y diseñados como desee que aparezcan en el control de usuario final. Si desea permitir a los desarrolladores tener acceso a los controles constituyentes, deberá declararlos públicos o exponer de forma selectiva las propiedades del control constituyente. Para obtener más detalles, vea [Cómo: Exponer propiedades de controles constituyentes](how-to-expose-properties-of-constituent-controls.md).  
  
4.  Implemente los métodos o propiedades personalizados que vaya a incorporar el control.  
  
5.  Presione F5 para compilar el proyecto y ejecutar el control en **UserControl Test Container**. Para obtener más información, vea [Cómo: Probar el comportamiento de tiempo de ejecución de una clase UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
## <a name="see-also"></a>Vea también

- [Variedades de controles personalizados](varieties-of-custom-controls.md)
- [Filtrar para heredar de la clase Control](how-to-inherit-from-the-control-class.md)
- [Filtrar para heredar de controles de formularios Windows Forms existentes](how-to-inherit-from-existing-windows-forms-controls.md)
- [Filtrar para crear controles de formularios Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Solucionar problemas de controladores de eventos heredados en Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Filtrar para comprobar el comportamiento de UserControl en tiempo de ejecución](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

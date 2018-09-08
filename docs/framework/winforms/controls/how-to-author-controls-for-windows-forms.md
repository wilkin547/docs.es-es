---
title: 'Cómo: Crear controles de formularios Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], creating
- UserControl class [Windows Forms], Windows Forms
- custom controls [Windows Forms], creating
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
ms.openlocfilehash: 844e38fc62fc9fb04a723c1a4a8ad834e957c8ce
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44132701"
---
# <a name="how-to-author-controls-for-windows-forms"></a>Cómo: Crear controles de formularios Windows Forms
Un control representa un vínculo gráfico entre el usuario y el programa. Un control puede proporcionar o procesar datos, aceptar datos proporcionados por el usuario, responder a eventos o ejecutar cualquier otra función que conecte al usuario con la aplicación. Dado que los controles son básicamente componentes con una interfaz gráfica, pueden ejecutar las mismas funciones que realizan los componentes, así como proporcionar interacción con los usuarios. Los controles se crean con un propósito específico; la creación de controles no es más que una tarea de programación como otra cualquiera. Teniendo esto en cuenta, los pasos siguientes representan información general sobre el proceso de creación de controles. Los vínculos proporcionan información adicional sobre cada paso.  
  
> [!NOTE]
>  Si desea crear un control personalizado para usarlo en formularios Web Forms, vea [Desarrollar controles de servidor ASP.NET personalizados](https://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).  
>   
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-author-a-control"></a>Para crear un control  
  
1.  Determine qué desea que haga el control o qué función desempeñará en la aplicación. Debe tener en cuenta los siguientes factores:  
  
    -   ¿Qué tipo de interfaz gráfica necesita?  
  
    -   ¿De qué interacciones específicas con el usuario se ocupará este control?  
  
    -   ¿Existe algún control que proporcione la funcionalidad que necesita?  
  
    -   ¿Puede obtener la funcionalidad necesaria mediante la combinación de varios controles de Windows Forms?  
  
2.  Si necesita un modelo de objetos para el control, determine cómo se distribuirá la funcionalidad a través del modelo de objetos y divídala entre el control y los objetos secundarios. Un modelo de objetos puede resultar útil si piensa crear un control complejo o desea incorporar varias funcionalidades.  
  
3.  Determine el tipo de control (por ejemplo, un control de usuario, un control personalizado o un control heredado de Windows Forms) que necesita. Para más información, consulte [Recomendaciones sobre tipos de controles](../../../../docs/framework/winforms/controls/control-type-recommendations.md) y [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).  
  
4.  Exprese la funcionalidad en forma de propiedades, métodos y eventos del control y sus objetos secundarios o estructuras subsidiarias, y asigne los niveles de acceso adecuados (por ejemplo, público, protegido, etc.).  
  
5.  Si necesita que el control utilice una representación personalizada, agregue el código necesario. Para información detallada, vea [Dibujo y representación personalizados de controles](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
6.  Si el control hereda de <xref:System.Windows.Forms.UserControl>, puede probar su comportamiento en tiempo de ejecución mediante la creación del proyecto de control y se ejecuta en el **UserControl Test Container**. Para más información, consulte [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
7.  También puede probar y depurar el control creando un nuevo proyecto, como una Aplicación Windows, y colocándola en un contenedor. Este proceso se muestra como parte del [Tutorial: Crear un control compuesto con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md).  
  
8.  A medida que agrega cada característica, agregue características al proyecto de prueba para ejecutar la nueva funcionalidad.  
  
9. Repita este proceso para refinar el diseño.  
  
10. Empaquete e implemente el control. Para información detallada, vea [Implementar aplicaciones, servicios y componentes](https://msdn.microsoft.com/library/wtzawcsz).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Crear un control compuesto con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [Tutorial: Heredar de un control de Windows Forms con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [cómo: Heredar de la clase UserControl](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [Cómo: Heredar de la clase control](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [Cómo: Heredar de controles de Windows Forms existentes](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [Cómo: Comprobar el comportamiento de una clase UserControl en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)

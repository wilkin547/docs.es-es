---
title: Procedimiento para crear controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], creating
- UserControl class [Windows Forms], Windows Forms
- custom controls [Windows Forms], creating
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
ms.openlocfilehash: 0804b9824b84a32bdd79c763031a3de4ffa54099
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039874"
---
# <a name="how-to-author-controls-for-windows-forms"></a>Procedimiento para crear controles de formularios Windows Forms

Un control representa un vínculo gráfico entre el usuario y el programa. Un control puede proporcionar o procesar datos, aceptar datos proporcionados por el usuario, responder a eventos o ejecutar cualquier otra función que conecte al usuario con la aplicación. Dado que los controles son básicamente componentes con una interfaz gráfica, pueden ejecutar las mismas funciones que realizan los componentes, así como proporcionar interacción con los usuarios. Los controles se crean con un propósito específico; la creación de controles no es más que una tarea de programación como otra cualquiera. Teniendo esto en cuenta, los pasos siguientes representan información general sobre el proceso de creación de controles. Los vínculos proporcionan información adicional sobre cada paso.

> [!NOTE]
> Si desea crear un control personalizado para usarlo en formularios Web Forms, vea [Desarrollar controles de servidor ASP.NET personalizados](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).

## <a name="to-author-a-control"></a>Para crear un control

1. Determine qué desea que haga el control o qué función desempeñará en la aplicación. Debe tener en cuenta los siguientes factores:

    - ¿Qué tipo de interfaz gráfica necesita?

    - ¿De qué interacciones específicas con el usuario se ocupará este control?

    - ¿Existe algún control que proporcione la funcionalidad que necesita?

    - ¿Puede obtener la funcionalidad necesaria mediante la combinación de varios controles de Windows Forms?

2. Si necesita un modelo de objetos para el control, determine cómo se distribuirá la funcionalidad a través del modelo de objetos y divídala entre el control y los objetos secundarios. Un modelo de objetos puede resultar útil si piensa crear un control complejo o desea incorporar varias funcionalidades.

3. Determine el tipo de control (por ejemplo, un control de usuario, un control personalizado o un control heredado de Windows Forms) que necesita. Para más información, consulte [Recomendaciones sobre tipos de controles](control-type-recommendations.md) y [Variedades de controles personalizados](varieties-of-custom-controls.md).

4. Exprese la funcionalidad en forma de propiedades, métodos y eventos del control y sus objetos secundarios o estructuras subsidiarias, y asigne los niveles de acceso adecuados (por ejemplo, público, protegido, etc.).

5. Si necesita que el control utilice una representación personalizada, agregue el código necesario. Para información detallada, vea [Dibujo y representación personalizados de controles](custom-control-painting-and-rendering.md).

6. Si el control hereda de, <xref:System.Windows.Forms.UserControl>puede probar su comportamiento en tiempo de ejecución mediante la compilación del proyecto de control y su ejecución en el **contenedor de prueba UserControl**. Para obtener más información, consulte [Cómo Pruebe el comportamiento en tiempo de ejecución de un](how-to-test-the-run-time-behavior-of-a-usercontrol.md)control UserControl.

7. También puede probar y depurar el control creando un nuevo proyecto, como una Aplicación Windows, y colocándola en un contenedor. Este proceso se muestra como parte del [Tutorial: Crear un control compuesto con Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md).

8. A medida que agrega cada característica, agregue características al proyecto de prueba para ejecutar la nueva funcionalidad.

9. Repita este proceso para refinar el diseño.

10. Empaquete e implemente el control. Para obtener más información, vea [primer vistazo a la implementación en Visual Studio](/visualstudio/deployment/deploying-applications-services-and-components).

## <a name="see-also"></a>Vea también

- [Tutorial: Crear un control compuesto con Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [Tutorial: Heredar de un control Windows Forms con Visual Basic](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [Cómo: Heredar de la clase UserControl](how-to-inherit-from-the-usercontrol-class.md)
- [Cómo: Heredar de la clase control](how-to-inherit-from-the-control-class.md)
- [Procedimientos: Heredar de controles de Windows Forms existentes](how-to-inherit-from-existing-windows-forms-controls.md)
- [Cómo: Probar el comportamiento en tiempo de ejecución de un control UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [Variedades de controles personalizados](varieties-of-custom-controls.md)

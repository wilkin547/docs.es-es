---
title: 'Cómo: crear controles'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], creating
- UserControl class [Windows Forms], Windows Forms
- custom controls [Windows Forms], creating
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 169104f51898f9bda08efa08685207e50406a7ff
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746722"
---
# <a name="how-to-author-controls-for-windows-forms"></a>Cómo: crear controles para Windows Forms

Un control representa un vínculo gráfico entre el usuario y el programa. Un control puede proporcionar o procesar datos, aceptar datos proporcionados por el usuario, responder a eventos o ejecutar cualquier otra función que conecte al usuario con la aplicación. Dado que los controles son básicamente componentes con una interfaz gráfica, pueden ejecutar las mismas funciones que realizan los componentes, así como proporcionar interacción con los usuarios. Los controles se crean con un propósito específico; la creación de controles no es más que una tarea de programación como otra cualquiera. Teniendo esto en cuenta, los pasos siguientes representan información general sobre el proceso de creación de controles. Los vínculos proporcionan información adicional sobre cada paso.

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

6. Si el control hereda de <xref:System.Windows.Forms.UserControl>, puede probar su comportamiento en tiempo de ejecución compilando el proyecto de control y ejecutando en el **contenedor de pruebas de UserControl**. Para más información, consulte [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](how-to-test-the-run-time-behavior-of-a-usercontrol.md).

7. También puede probar y depurar el control creando un nuevo proyecto, como una Aplicación Windows, y colocándola en un contenedor. Este proceso se muestra como parte del [Tutorial: crear un control compuesto](walkthrough-authoring-a-composite-control-with-visual-csharp.md).

8. A medida que agrega cada característica, agregue características al proyecto de prueba para ejecutar la nueva funcionalidad.

9. Repita este proceso para refinar el diseño.

10. Empaquete e implemente el control. Para obtener más información, vea [primer vistazo a la implementación en Visual Studio](/visualstudio/deployment/deploying-applications-services-and-components).

## <a name="see-also"></a>Vea también

- [Cómo: Heredar de una clase UserControl](how-to-inherit-from-the-usercontrol-class.md)
- [Cómo: Heredar de la clase control](how-to-inherit-from-the-control-class.md)
- [Cómo: Heredar de controles de Windows Forms existentes](how-to-inherit-from-existing-windows-forms-controls.md)
- [Cómo: Comprobar el comportamiento de una clase UserControl en tiempo de ejecución](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [Variedades de controles personalizados](varieties-of-custom-controls.md)

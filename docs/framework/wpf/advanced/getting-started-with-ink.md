---
title: Crear InkCanvas en Visual Studio
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: b8087d6db04f7024b9ee48f28002bee04045a14b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737887"
---
# <a name="get-started-with-ink-in-wpf"></a>Introducción a la entrada manuscrita en WPF

Windows Presentation Foundation (WPF) tiene una característica de entrada manuscrita que facilita la incorporación de tinta digital a la aplicación.

## <a name="prerequisites"></a>Prerequisites

Para usar los ejemplos siguientes, primero instale [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019). También ayuda a saber cómo escribir aplicaciones WPF básicas. Para obtener ayuda para empezar a trabajar con WPF, vea [Tutorial: mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="quick-start"></a>Inicio rápido

Esta sección le ayuda a escribir una aplicación WPF sencilla que recopila entradas manuscritas.

### <a name="got-ink"></a>¿Tiene tinta?

Para crear una aplicación de WPF que admita la entrada de lápiz:

1. Abra Visual Studio.

2. Cree una nueva **aplicación WPF**.

   En el cuadro de diálogo **nuevo proyecto** , expanda la categoría **instalado** > **Visual C#**  o **Visual Basic** > **escritorio de Windows** . A continuación, seleccione la plantilla aplicación de **WPF (.NET Framework)** . Escriba un nombre y seleccione **Aceptar**.

   Visual Studio crea el proyecto y *MainWindow. Xaml* se abre en el diseñador.

3. Escriba `<InkCanvas/>` entre las etiquetas de `<Grid>`.

   ![Diseñador XAML con etiqueta InkCanvas](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. Presione **F5** para iniciar la aplicación en el depurador.

5. Con un lápiz o un mouse, escriba **Hello World** en la ventana.

Ha escrito el equivalente de tinta de una aplicación "Hola mundo" con solo 12 pulsaciones de teclas.

### <a name="spice-up-your-app"></a>Enriquecer su aplicación

Vamos a aprovechar algunas características de WPF. Reemplace todo el código entre las etiquetas de apertura y cierre \<> por el marcado siguiente:

```xaml
<Page>
  <InkCanvas Name="myInkCanvas" MouseRightButtonUp="RightMouseUpHandler">
    <InkCanvas.Background>
      <LinearGradientBrush>
        <GradientStop Color="Yellow" Offset="0.0" />
          <GradientStop Color="Blue" Offset="0.5" />
            <GradientStop Color="HotPink" Offset="1.0" />
              </LinearGradientBrush>
    </InkCanvas.Background>
  </InkCanvas>
</Page>
```

Este código XAML crea un fondo de pincel de degradado en la superficie de entrada manuscrita.

![Colores de degradado en la superficie de entrada manuscrita en la aplicación WPF](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a>Agregar código detrás de XAML

Aunque XAML facilita enormemente el diseño de la interfaz de usuario, cualquier aplicación real necesita agregar código para controlar eventos. Este es un ejemplo sencillo que acerca la tinta en respuesta a un clic con el botón secundario del mouse.

1. Establezca el controlador de `MouseRightButtonUp` en el código XAML:

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. En **Explorador de soluciones**, expanda MainWindow. XAML y abra el archivo de código subyacente (MainWindow.Xaml.cs o MainWindow. Xaml. VB). Agregue el siguiente código de controlador de eventos:

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. Ejecute la aplicación. Agregue una entrada de lápiz y, a continuación, haga clic con el botón secundario del mouse o realice un equivalente de mantener presionado con un lápiz.

   La pantalla se acerca cada vez que se hace clic con el botón secundario del mouse.

### <a name="use-procedural-code-instead-of-xaml"></a>Usar código de procedimientos en lugar de XAML

Puede tener acceso a todas las características de WPF desde código de procedimientos. Siga estos pasos para crear una aplicación "Hello Ink World" para WPF que no use ningún XAML.

1. Cree un nuevo proyecto de aplicación de consola en Visual Studio.

   En el cuadro de diálogo **nuevo proyecto** , expanda la categoría **instalado** > **Visual C#**  o **Visual Basic** > **escritorio de Windows** . A continuación, seleccione la plantilla aplicación de **consola (.NET Framework)** . Escriba un nombre y seleccione **Aceptar**.

1. Pegue el código siguiente en el archivo Program.cs o Program. VB:

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. Agregue referencias a los ensamblados PresentationCore, PresentationFramework y WindowsBase; para ello, haga clic con el botón derecho en **referencias** en **Explorador de soluciones** y elija **Agregar referencia**.

   ![Administrador de referencias que muestra PresentationCore y PresentationFramework](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. Para compilar la aplicación, presione **F5**.

## <a name="see-also"></a>Consulte también

- [Entrada de lápiz digital](digital-ink.md)
- [Recopilación de entradas de lápiz](collecting-ink.md)
- [Reconocimiento de escritura a mano](handwriting-recognition.md)
- [Almacenamiento de entradas de lápiz](storing-ink.md)

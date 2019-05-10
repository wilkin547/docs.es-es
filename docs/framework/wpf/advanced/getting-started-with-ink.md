---
title: Crear un objeto InkCanvas en una aplicación WPF en Visual Studio
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: d633111c5abc572b0fc27c1a5b32050681504073
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753008"
---
# <a name="get-started-with-ink-in-wpf"></a>Empezar a trabajar con entradas manuscritas en WPF

Windows Presentation Foundation (WPF) tiene una característica de tinta que facilita la tarea incorporar la entrada de lápiz digital en su aplicación.

## <a name="prerequisites"></a>Requisitos previos

Para usar los ejemplos siguientes, en primer lugar instale [Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019). También ayuda a saber cómo escribir aplicaciones básicas de WPF. Para obtener ayuda de introducción a WPF, consulte [Tutorial: Mi primera aplicación de escritorio de WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="quick-start"></a>Guía de inicio rápido

En esta sección le ayuda a escribir una aplicación WPF sencilla que recopila entradas de lápiz.

### <a name="got-ink"></a>¿Tiene la entrada de lápiz?

Para crear una aplicación WPF que admite la entrada de lápiz:

1. Abra Visual Studio.

2. Cree un nuevo **aplicación WPF**.

   En el **nuevo proyecto** cuadro de diálogo, expanda el **instalado** > **Visual C#** o **Visual Basic**  >   **Windows Desktop** categoría. A continuación, seleccione el **aplicación de WPF (.NET Framework)** plantilla de aplicación. Escriba un nombre y, a continuación, seleccione **Aceptar**.

   Visual Studio crea el proyecto, y *MainWindow.xaml* se abre en el diseñador.

3. Tipo `<InkCanvas/>` entre el `<Grid>` etiquetas.

   ![Diseñador XAML con la etiqueta a InkCanvas](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. Presione **F5** para iniciar la aplicación en el depurador.

5. Con un lápiz o un mouse, escribir **Hola mundo** en la ventana.

Ha escrito el equivalente de tinta de una aplicación "hello world" con tan sólo 12 pulsaciones de teclas.

### <a name="spice-up-your-app"></a>Anime la aplicación

Vamos a sacar partido de algunas características de WPF. Reemplace todo entre la apertura y cierre \<Ventana > etiquetas con el marcado siguiente:

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

Este XAML crea un fondo de pincel de degradado en la superficie de escritura a mano.

![Colores de degradado en la superficie de la aplicación WPF de tinta](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a>Agregar código detrás del XAML

Aunque XAML hace muy fácil de diseñar la interfaz de usuario, debe agregar código para controlar los eventos de cualquier aplicación del mundo real. Este es un ejemplo sencillo que amplía la tinta en respuesta a un secundario de un mouse.

1. Establecer el `MouseRightButtonUp` controlador en el XAML:

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. En **el Explorador de soluciones**, expanda MainWindow.xaml y abra el archivo de código subyacente (MainWindow.xaml.cs o MainWindow.xaml.vb). Agregue el siguiente código de controlador de eventos:

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. Ejecute la aplicación. Agregar algo de tinta y, a continuación, haga doble clic con el mouse o presione y mantenga equivalente de hacer con un lápiz óptico.

   La presentación acerca cada vez que haga clic con el botón secundario del mouse.

### <a name="use-procedural-code-instead-of-xaml"></a>Usar código de procedimientos en lugar de XAML

Puede tener acceso a todas las características WPF del código de procedimientos. Siga estos pasos para crear una aplicación "Hello Ink World" para WPF que no usa ningún XAML en absoluto.

1. Crear un nuevo proyecto de aplicación de consola en Visual Studio.

   En el **nuevo proyecto** cuadro de diálogo, expanda el **instalado** > **Visual C#** o **Visual Basic**  >   **Windows Desktop** categoría. A continuación, seleccione el **aplicación de consola (.NET Framework)** plantilla de aplicación. Escriba un nombre y, a continuación, seleccione **Aceptar**.

1. Pegue el código siguiente en el archivo Program.cs o Program.vb:

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. Agregue referencias a los ensamblados PresentationCore, PresentationFramework y WindowsBase haciendo clic en **referencias** en **el Explorador de soluciones** y eligiendo **Agregar referencia**.

   ![Administrador de referencias que muestra PresentationCore y PresentationFramework](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. Compile la aplicación presionando **F5**.

## <a name="see-also"></a>Vea también

- [Entrada de lápiz digital](digital-ink.md)
- [Recopilación de entradas de lápiz](collecting-ink.md)
- [Reconocimiento de escritura a mano](handwriting-recognition.md)
- [Almacenamiento de entradas de lápiz](storing-ink.md)

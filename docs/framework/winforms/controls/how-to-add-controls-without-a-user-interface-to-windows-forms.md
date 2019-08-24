---
title: Procedimiento para agregar controles sin una interfaz de usuario a formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: bc1f844e5a2cf4d4f3b64ebf20e935f36ff85e12
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987107"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a>Procedimiento para agregar controles sin una interfaz de usuario a formularios Windows Forms

Un control (o componente) no visual proporciona funcionalidad a la aplicación. A diferencia de otros controles, los componentes no proporcionan una interfaz de usuario al usuario y, por tanto, no es necesario que se muestren en la superficie de Diseñador de Windows Forms. Cuando se agrega un componente a un formulario, el Diseñador de Windows Forms muestra una bandeja de tamaño variable en la parte inferior del formulario donde se muestran todos los componentes. Una vez que se ha agregado un control a la bandeja de componentes, puede seleccionar el componente y establecer sus propiedades como lo haría con cualquier otro control del formulario.

## <a name="add-a-component-to-a-windows-form"></a>Agregar un componente a un Windows Form

1. Abra el formulario en Visual Studio. Para obtener más detalles, vea [Cómo: Mostrar Windows Forms en el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).

2. En el **cuadro de herramientas**, haga clic en un componente y arrástrelo al formulario.

     El componente aparecerá en la bandeja de componentes.

Además, los componentes se pueden agregar a un formulario en tiempo de ejecución. Se trata de un escenario común, especialmente porque los componentes no tienen una expresión visual, a diferencia de los controles que tienen una interfaz de usuario. En el ejemplo siguiente, se <xref:System.Windows.Forms.Timer> agrega un componente en tiempo de ejecución. (Tenga en cuenta que Visual Studio contiene varios temporizadores diferentes; en este caso, use un componente <xref:System.Windows.Forms.Timer> de Windows Forms. Para obtener más información sobre los diferentes temporizadores en Visual Studio, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).

> [!CAUTION]
> Los componentes suelen tener propiedades específicas del control que se deben establecer para que el componente funcione de forma eficaz. En el caso del <xref:System.Windows.Forms.Timer> componente siguiente, establezca la `Interval` propiedad. Asegúrese de que, al agregar componentes al proyecto, establezca las propiedades necesarias para ese componente.

## <a name="add-a-component-to-a-windows-form-programmatically"></a>Agregar un componente a un formulario de Windows Forms mediante programación

1. Cree una instancia de la <xref:System.Windows.Forms.Timer> clase en el código.

2. Establezca la `Interval` propiedad para determinar el tiempo entre los tics del temporizador.

3. Configure cualquier otra propiedad necesaria para el componente.

     En el código siguiente se muestra la creación <xref:System.Windows.Forms.Timer> de un `Interval` con su conjunto de propiedades.

    ```vb
    Public Sub CreateTimer()
       Dim timerKeepTrack As New System.Windows.Forms.Timer
       timerKeepTrack.Interval = 1000
    End Sub
    ```

    ```csharp
    public void createTimer()
    {
       System.Windows.Forms.Timer timerKeepTrack = new
           System.Windows.Forms.Timer();
       timerKeepTrack.Interval = 1000;
    }
    ```

    ```cpp
    public:
       void createTimer()
       {
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew
             System::Windows::Forms::Timer();
          timerKeepTrack->Interval = 1000;
       }
    ```

    > [!IMPORTANT]
    > Puede exponer el equipo local a un riesgo de seguridad a través de la red haciendo referencia a un UserControl malintencionado. Esto solo suponer un problema en el caso de que una persona malintencionada cree un control personalizado perjudicial y, después, lo agregue por error a su proyecto.

## <a name="see-also"></a>Vea también

- [Controles de formularios Windows Forms](index.md)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Cómo: Agregar controles ActiveX a Windows Forms](how-to-add-activex-controls-to-windows-forms.md)
- [Insertar controles en Windows Forms](putting-controls-on-windows-forms.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)

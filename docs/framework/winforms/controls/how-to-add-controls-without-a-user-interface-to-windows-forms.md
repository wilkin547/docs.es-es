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
ms.openlocfilehash: 0768f811653543b3370310ccc0b59890273baf52
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330108"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a>Procedimiento para agregar controles sin una interfaz de usuario a formularios Windows Forms
Un control no Visual (o componente) proporciona funcionalidad para la aplicación. A diferencia de otros controles, componentes no proporcionan una interfaz de usuario para el usuario y, por tanto, no es necesario que se mostrará en la superficie del Diseñador de formularios de Windows. Cuando se agrega un componente a un formulario, el Diseñador de Windows Forms muestra una bandeja de tamaño variable en la parte inferior del formulario donde se muestran todos los componentes. Una vez que un control se ha agregado a la Bandeja de componentes, puede seleccionar el componente y establezca sus propiedades como lo haría con cualquier otro control en el formulario.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-a-component-to-a-windows-form"></a>Para agregar un componente a un formulario de Windows  
  
1. Abra el formulario. Para obtener más detalles, vea [Cómo: Mostrar Windows Forms en el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).  
  
2. En el **cuadro de herramientas**, haga clic en un componente y arrástrelo al formulario.  
  
     El componente aparecerá en la Bandeja de componentes.  
  
 Además, se pueden agregar componentes a un formulario en tiempo de ejecución. Se trata de un escenario común, especialmente porque los componentes no tienen una expresión visual, a diferencia de los controles que tienen una interfaz de usuario. En el ejemplo siguiente, un <xref:System.Windows.Forms.Timer> se agrega el componente en tiempo de ejecución. (Tenga en cuenta que Visual Studio contiene un número de temporizadores diferentes; en este caso, utilice un formulario Windows Forms <xref:System.Windows.Forms.Timer> componente. Para obtener más información sobre los diferentes temporizadores en Visual Studio, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)  
  
> [!CAUTION]
>  A menudo, los componentes tienen propiedades específicas del control que se deben establecer para que el componente funcione de forma eficaz. En el caso de los <xref:System.Windows.Forms.Timer> componentes indicados a continuación, Establece el `Interval` propiedad. Asegúrese de, al agregar componentes al proyecto, Establece las propiedades necesarias para cada componente.  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a>Para agregar un componente a un formulario Windows Forms mediante programación  
  
1. Cree una instancia de la <xref:System.Windows.Forms.Timer> clase en código.  
  
2. Establecer el `Interval` propiedad para determinar el tiempo entre los pasos del temporizador.  
  
3. Configurar las otras propiedades necesarias para el componente.  
  
     El código siguiente muestra la creación de un <xref:System.Windows.Forms.Timer> con su `Interval` conjunto de propiedades.  
  
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
    >  Puede exponer el equipo local a un riesgo de seguridad a través de la red haciendo referencia a un control de usuario malintencionado. Esto solo sería un problema en el caso de una persona malintencionada cree un control personalizado perjudicial, seguido por el que se agregara a su proyecto.  
  
## <a name="see-also"></a>Vea también

- [Controles de formularios Windows Forms](index.md)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Cómo: Agregar controles ActiveX a formularios de Windows](how-to-add-activex-controls-to-windows-forms.md)
- [Cómo: Copiar controles entre formularios de Windows](how-to-copy-controls-between-windows-forms.md)
- [Insertar controles en Windows Forms](putting-controls-on-windows-forms.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)

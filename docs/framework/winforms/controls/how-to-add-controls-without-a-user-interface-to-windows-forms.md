---
title: Procedimiento Agregar controles sin una interfaz de usuario a Windows Forms
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
ms.openlocfilehash: 442a6175b1b378cf3489314e190c58312a327c01
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738594"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a>Procedimiento Agregar controles sin una interfaz de usuario a Windows Forms
Un control no Visual (o componente) proporciona funcionalidad para la aplicación. A diferencia de otros controles, componentes no proporcionan una interfaz de usuario para el usuario y, por tanto, no es necesario que se mostrará en la superficie del Diseñador de formularios de Windows. Cuando se agrega un componente a un formulario, el Diseñador de Windows Forms muestra una bandeja de tamaño variable en la parte inferior del formulario donde se muestran todos los componentes. Una vez que un control se ha agregado a la Bandeja de componentes, puede seleccionar el componente y establezca sus propiedades como lo haría con cualquier otro control en el formulario.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-a-component-to-a-windows-form"></a>Para agregar un componente a un formulario de Windows  
  
1.  Abra el formulario. Para obtener más información, vea [Cómo: Mostrar Windows Forms en el diseñador](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  En el **cuadro de herramientas**, haga clic en un componente y arrástrelo al formulario.  
  
     El componente aparecerá en la Bandeja de componentes.  
  
 Además, se pueden agregar componentes a un formulario en tiempo de ejecución. Se trata de un escenario común, especialmente porque los componentes no tienen una expresión visual, a diferencia de los controles que tienen una interfaz de usuario. En el ejemplo siguiente, un <xref:System.Windows.Forms.Timer> se agrega el componente en tiempo de ejecución. (Tenga en cuenta que Visual Studio contiene un número de temporizadores diferentes; en este caso, utilice un formulario Windows Forms <xref:System.Windows.Forms.Timer> componente. Para obtener más información sobre los diferentes temporizadores en Visual Studio, consulte [Introducción a los temporizadores basados en servidor](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)  
  
> [!CAUTION]
>  A menudo, los componentes tienen propiedades específicas del control que se deben establecer para que el componente funcione de forma eficaz. En el caso de los <xref:System.Windows.Forms.Timer> componentes indicados a continuación, Establece el `Interval` propiedad. Asegúrese de, al agregar componentes al proyecto, Establece las propiedades necesarias para cada componente.  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a>Para agregar un componente a un formulario Windows Forms mediante programación  
  
1.  Cree una instancia de la <xref:System.Windows.Forms.Timer> clase en código.  
  
2.  Establecer el `Interval` propiedad para determinar el tiempo entre los pasos del temporizador.  
  
3.  Configurar las otras propiedades necesarias para el componente.  
  
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
- [Controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/index.md)
- [Cómo: Agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
- [Cómo: Agregar controles ActiveX a formularios de Windows](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)
- [Cómo: Copiar controles entre formularios de Windows](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)
- [Insertar controles en Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)

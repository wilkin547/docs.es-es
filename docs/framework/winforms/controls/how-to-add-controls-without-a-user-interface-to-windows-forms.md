---
title: "C&#243;mo: Agregar controles sin una interfaz de usuario a formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "NonVisualSelection"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles [Windows Forms], no visuales"
  - "controles invisibles"
  - "controles no visuales"
  - "controles de Windows Forms, agregar a un formulario"
  - "controles de Windows Forms, no visuales"
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Agregar controles sin una interfaz de usuario a formularios Windows Forms
Un control \(o componente\) no visual proporciona funcionalidad a la aplicación.  A diferencia de otros controles, los componentes no proporcionan una interfaz de usuario y, por lo tanto, no es necesario mostrarlos en la superficie del Diseñador de Windows Forms.  Cuando se agrega un componente a un formulario, el Diseñador de Windows Forms muestra una bandeja de tamaño variable en la parte inferior del formulario, donde se muestran todos los componentes.  Una vez que se agrega un control a la bandeja de componentes, puede seleccionarlo y establecer sus propiedades igual que con cualquier otro control en el formulario.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para agregar un componente a un Windows Form  
  
1.  Abra el formulario.  Para obtener información detallada, vea [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/es-es/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  En el **Cuadro de herramientas**, haga clic en un componente y arrástrelo al formulario.  
  
     El componente aparecerá en la bandeja de componentes.  
  
 Además, puede agregar componentes a un formulario en tiempo de ejecución.  Éste es un escenario común, sobre todo porque los componentes no tienen una expresión visual, a diferencia de los controles que tienen una interfaz de usuario.  En el ejemplo siguiente, se agrega un componente <xref:System.Windows.Forms.Timer> en tiempo de ejecución.  Tenga en cuenta que [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] contiene una serie de temporizadores diferentes; en este caso, utilice un componente <xref:System.Windows.Forms.Timer> de formularios Windows Forms.  Para obtener más información sobre los diferentes temporizadores de [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], vea [Introduction to Server\-Based Timers](http://msdn.microsoft.com/es-es/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).\)  
  
> [!CAUTION]
>  A menudo, los componentes tienen propiedades específicas del control que es necesario establecer para que el componente funcione de un modo eficaz.  En el caso del siguiente componente <xref:System.Windows.Forms.Timer>, deberá establecer la propiedad `Interval`.  Asegúrese, cuando agregue componentes al proyecto, de establecer las propiedades necesarias para cada componente.  
  
#### Para agregar un componente a un Windows Form mediante programación  
  
1.  Cree una instancia de la clase <xref:System.Windows.Forms.Timer> en código.  
  
2.  Defina la propiedad `Interval` para determinar el tiempo entre marcas de paso del temporizador.  
  
3.  Configure el resto de las propiedades necesarias para el componente.  
  
     El código siguiente muestra la creación de un objeto <xref:System.Windows.Forms.Timer> con la propiedad `Interval` definida.  
  
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
    >  Puede exponer el equipo local a un riesgo de seguridad a través de la red si hace referencia a un UserControl creado con fines malintencionados.  El problema se puede presentar en el caso de que una persona malintencionada cree un control personalizado perjudicial que, a continuación, se agregue por error a su proyecto.  
  
## Vea también  
 [Controles de Windows Forms](../../../../docs/framework/winforms/controls/index.md)   
 [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)   
 [Cómo: Agregar controles ActiveX a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)   
 [Cómo: Copiar controles entre formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)   
 [Insertar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)   
 [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Controles de formularios Windows Forms por función](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
---
title: Procedimiento Heredar Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: 29b32cd91cefe80f2f0a331f901fcabe55aa9c60
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558987"
---
# <a name="how-to-inherit-windows-forms"></a>Procedimiento Heredar Windows Forms
Crear nuevos Windows Forms heredando de formularios base es una forma práctica de aprovechar el trabajo ya hecho sin tener que pasar por todo el proceso de crear un formulario cada vez que lo necesite.  
  
 Para obtener más información acerca de la herencia de formularios en tiempo de diseño mediante el **selector de herencia** cuadro de diálogo y cómo distinguir visualmente los niveles de seguridad de los controles heredados, vea [Cómo: Heredar formularios mediante el cuadro de diálogo Selector de herencia](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).  
  
 **Nota**: Para heredar de un formulario, el archivo o el espacio de nombres que contiene el formulario debe haberse compilado en un archivo ejecutable o DLL. Para compilar el proyecto, elija **Compilar** en el menú **Compilar**. Además, debe agregarse una referencia al espacio de nombres a la clase que hereda el formulario. Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-inherit-a-form-programmatically"></a>Para heredar un formulario mediante programación  
  
1.  En la clase, agregue una referencia al espacio de nombres que contiene el formulario del que desea heredar.  
  
2.  En la definición de la clase, agregue una referencia al formulario del que se va a heredar. La referencia debe incluir el espacio de nombres que contiene el formulario, seguido por un punto y del nombre del propio formulario base.  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
    ```  
  
 Al heredar formularios, tenga en cuenta que pueden surgir problemas por controladores de eventos a los que se llama dos veces, porque cada evento está siendo controlado por la clase base y por la clase heredada. Para más información acerca de cómo evitar este problema, vea [Solución de problemas de controladores de eventos heredados en Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).  
  
## <a name="see-also"></a>Vea también
- [Inherits (instrucción)](~/docs/visual-basic/language-reference/statements/inherits-statement.md)
- [Imports (instrucción), espacio de nombres y tipo .NET](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [using](~/docs/csharp/language-reference/keywords/using.md)
- [Efectos de modificar la apariencia de un formulario base](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)
- [Herencia visual de Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)

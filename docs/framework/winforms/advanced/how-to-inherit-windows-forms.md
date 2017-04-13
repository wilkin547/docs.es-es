---
title: "C&#243;mo: Heredar formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "herencia, formularios"
  - "formularios heredados, crear en tiempo de ejecución"
  - "Windows Forms, herencia"
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Heredar formularios Windows Forms
Crear nuevos Windows Forms heredando de formularios base es una forma práctica de aprovechar el trabajo ya hecho sin tener que pasar por todo el proceso de crear un formulario cada vez que lo necesite.  
  
 Para obtener más información acerca de la herencia de formularios en tiempo de diseño mediante el cuadro de diálogo **Selector de herencia**, y cómo distinguir visualmente los niveles de seguridad de los controles heredados, consulte [Cómo: Heredar formularios mediante el cuadro de diálogo Selector de herencia](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).  
  
 **Nota** Para heredar de un formulario, el archivo o el espacio de nombres que contiene el formulario debe haberse compilado en un archivo ejecutable o DLL.  Para compilar el proyecto, elija **Compilar** en el menú **Compilar**.  Además, debe agregarse una referencia al espacio de nombres a la clase que hereda el formulario.  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas**.  Para obtener más información, consulte [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para heredar un formulario mediante programación  
  
1.  En la clase, agregue una referencia al espacio de nombres que contiene el formulario del que desea heredar.  
  
2.  En la definición de la clase, agregue una referencia al formulario del que se va a heredar.  La referencia debe incluir el espacio de nombres que contiene el formulario, seguido por un punto y del nombre del propio formulario base.  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
  
    ```  
  
 Al heredar formularios, tenga en cuenta que pueden surgir problemas por controladores de eventos a los que se llama dos veces, porque cada evento está siendo controlado por la clase base y por la clase heredada.  Para obtener más información acerca de cómo evitar este problema, consulte [Solución de problemas de controladores de eventos heredados en Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md).  
  
## Vea también  
 [Inherits \(Instrucción\)](../../../../ocs/visual-basic/language-reference/statements/inherits-statement.md)   
 [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../../ocs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [utilizar](../Topic/using%20\(C%23%20Reference\).md)   
 [Efectos de modificar la apariencia de un formulario base](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)   
 [Herencia visual de formularios Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
---
title: 'Tutorial: Incrustar información de tipos de ensamblados de Microsoft Office en Visual Studio (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 26b44286-5066-4ad4-8e6a-c24902be347c
ms.openlocfilehash: bc8f7585964bdd60bac5d5a466f6276fab288c78
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44188662"
---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-visual-basic"></a>Tutorial: Incrustar información de tipos de ensamblados de Microsoft Office en Visual Studio (Visual Basic)
Si inserta la de tipos en una aplicación que hace referencia a objetos COM, puede eliminar la necesidad de un ensamblado de interoperabilidad primario (PIA). Además, la información de tipo incrustada permite que la versión de la aplicación gane en independencia. Es decir, el programa puede escribirse de modo que use tipos de varias versiones de una biblioteca COM sin necesidad de requerir un PIA específico para cada versión. Se trata de un escenario común para las aplicaciones que usan objetos de las bibliotecas de Microsoft Office. La inserción de la información de tipos permite que la misma compilación de un programa funcione con distintas versiones de Microsoft Office en equipos diferentes sin necesidad de volver a implementar el programa o el PIA para cada versión de Microsoft Office.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Requisitos previos  
 En este tutorial se requiere lo siguiente:  
  
-   Un equipo en el que estén instalados Visual Studio y Microsoft Excel.  
  
-   Un segundo equipo en el que estén instalados .NET Framework 4 o superior y una versión diferente de Excel.  
  
##  <a name="BKMK_createapp"></a> Para crear una aplicación que funcione con varias versiones de Microsoft Office  
  
1.  Inicie Visual Studio en un equipo en el que esté instalado Excel.  
  
2.  En el menú **Archivo** , elija **Nuevo**, **Proyecto**.  
  
3.  En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**. Seleccione **Aplicación de consola** en el panel **Plantillas**. En el cuadro **Nombre**, escriba `CreateExcelWorkbook` y seleccione el botón **Aceptar**. Se crea el proyecto.  
  
4.  Abra el menú contextual del proyecto CreateExcelWorkbook y, a continuación, elija **propiedades**. Elija la **referencias** ficha. Elija el botón de **Agregar** .  
  
5.  En la pestaña **.NET**, elija la versión más reciente de `Microsoft.Office.Interop.Excel`. Por ejemplo, **Microsoft.Office.Interop.Excel 14.0.0.0**. Elija el botón **Aceptar** .  
  
6.  En la lista de referencias para el proyecto **CreateExcelWorkbook**, seleccione la referencia para `Microsoft.Office.Interop.Excel` que agregó en el paso anterior. En la ventana **Propiedades**, asegúrese de que la propiedad `Embed Interop Types` esté establecida en `True`.  
  
    > [!NOTE]
    >  La aplicación creada en este tutorial se ejecuta con distintas versiones de Microsoft Office debido a la información de tipo de interoperabilidad insertada. Si la propiedad `Embed Interop Types` está establecida en `False`, debe incluir un PIA para cada versión de Microsoft Office con la que se ejecute la aplicación.  
  
7.  Abra el archivo Module1.vb. Reemplace el código de este archivo por el código siguiente:  
  
    ```vb  
    Imports Excel = Microsoft.Office.Interop.Excel  
  
    Module Module1  
  
        Sub Main()  
            Dim values = {4, 6, 18, 2, 1, 76, 0, 3, 11}  
  
            CreateWorkbook(values, "C:\SampleFolder\SampleWorkbook.xls")  
        End Sub  
  
        Sub CreateWorkbook(ByVal values As Integer(), ByVal filePath As String)  
            Dim excelApp As Excel.Application = Nothing  
            Dim wkbk As Excel.Workbook  
            Dim sheet As Excel.Worksheet  
  
            Try  
                ' Start Excel and create a workbook and worksheet.  
                excelApp = New Excel.Application  
                wkbk = excelApp.Workbooks.Add()  
                sheet = CType(wkbk.Sheets.Add(), Excel.Worksheet)  
                sheet.Name = "Sample Worksheet"  
  
                ' Write a column of values.  
                ' In the For loop, both the row index and array index start at 1.  
                ' Therefore the value of 4 at array index 0 is not included.  
                For i = 1 To values.Length - 1  
                    sheet.Cells(i, 1) = values(i)  
                Next  
  
                ' Suppress any alerts and save the file. Create the directory   
                ' if it does not exist. Overwrite the file if it exists.  
                excelApp.DisplayAlerts = False  
                Dim folderPath = My.Computer.FileSystem.GetParentPath(filePath)  
                If Not My.Computer.FileSystem.DirectoryExists(folderPath) Then  
                    My.Computer.FileSystem.CreateDirectory(folderPath)  
                End If  
                wkbk.SaveAs(filePath)  
        Catch  
  
            Finally  
                sheet = Nothing  
                wkbk = Nothing  
  
                ' Close Excel.  
                excelApp.Quit()  
                excelApp = Nothing  
            End Try  
  
        End Sub  
    End Module  
    ```  
  
8.  Guarde el proyecto.  
  
9. Pulse CTRL+F5 para compilar y ejecutar el proyecto. Compruebe que se ha creado un libro de Excel en la ubicación especificada en el código de ejemplo: C:\SampleFolder\SampleWorkbook.xls.  
  
##  <a name="BKMK_publishapp"></a> Para publicar la aplicación en un equipo en el que está instalada una versión diferente de Microsoft Office  
  
1.  Abra el proyecto creado mediante este tutorial en Visual Studio.  
  
2.  En el menú **Compilar**, elija **Publicar CreateExcelWorkbook**. Siga los pasos del Asistente para publicación para crear una versión instalable de la aplicación. Para obtener más información, vea [Asistente para publicación (Desarrollo de Office en Visual Studio)](/visualstudio/vsto/publish-wizard-office-development-in-visual-studio).  
  
3.  Instale la aplicación en un equipo en el que estén instalados .NET Framework 4 o superior y una versión diferente de Excel.  
  
4.  Cuando finalice la instalación, ejecute el programa instalado.  
  
5.  Compruebe que se ha creado un libro de Excel en la ubicación especificada en el código de ejemplo: C:\SampleFolder\SampleWorkbook.xls.  
  
## <a name="see-also"></a>Vea también

- [Tutorial: Incrustar los tipos de los ensamblados administrados en Visual Studio (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)  
- [/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)

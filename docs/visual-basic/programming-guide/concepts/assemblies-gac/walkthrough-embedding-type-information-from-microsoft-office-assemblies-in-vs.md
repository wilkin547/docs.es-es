---
title: "Tutorial: Incrustar información de tipos de ensamblados de Microsoft Office en Visual Studio (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 26b44286-5066-4ad4-8e6a-c24902be347c
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4347ba0e740419b53a1aa662c43933dead107e9c
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-visual-basic"></a>Tutorial: Incrustar información de tipos de ensamblados de Microsoft Office en Visual Studio (Visual Basic)
Si incrusta la información de tipo en una aplicación que hace referencia a objetos COM, puede eliminar la necesidad de un ensamblado de interoperabilidad primario (PIA). Además, la información de tipo incrustada permite conseguir la independencia de la versión de la aplicación. Es decir, el programa puede escribirse usar tipos de varias versiones de una biblioteca COM sin necesidad de un PIA específico para cada versión. Se trata de un escenario común para las aplicaciones que usan objetos de las bibliotecas de Microsoft Office. Incrustar información de tipos permite la misma versión de un programa para trabajar con distintas versiones de Microsoft Office en equipos diferentes sin necesidad de volver a implementar el programa o el PIA para cada versión de Microsoft Office.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="prerequisites"></a>Requisitos previos  
 En este tutorial se requiere lo siguiente:  
  
-   Un equipo en el que están instalado Visual Studio y Microsoft Excel.  
  
-   Un segundo equipo en el que están instalados .NET Framework 4 o superior y una versión diferente de Excel.  
  
##  <a name="BKMK_createapp"></a>Para crear una aplicación que funcione con varias versiones de Microsoft Office  
  
1.  Inicie Visual Studio en un equipo donde esté instalado Excel.  
  
2.  En el menú **Archivo** , elija **Nuevo**, **Proyecto**.  
  
3.  En el **nuevo proyecto** cuadro de diálogo el **tipos de proyecto** panel, asegúrese de que **Windows** está seleccionada. Seleccione **aplicación de consola** en el **plantillas** panel. En el **nombre** , escriba `CreateExcelWorkbook`y, a continuación, elija la **Aceptar** botón. Se crea el nuevo proyecto.  
  
4.  Abra el menú contextual para el proyecto CreateExcelWorkbook y, a continuación, elija **propiedades**. Elija la **referencias** ficha. Elija el botón de **Agregar** .  
  
5.  En el **.NET** ficha, elija la versión más reciente de `Microsoft.Office.Interop.Excel`. Por ejemplo, **Microsoft.Office.Interop.Excel 14.0.0.0**. Elija el botón **Aceptar** .  
  
6.  En la lista de referencias para el **CreateExcelWorkbook** de proyectos, seleccione la referencia para `Microsoft.Office.Interop.Excel` que agregó en el paso anterior. En el **propiedades** ventana, asegúrese de que el `Embed Interop Types` propiedad está establecida en `True`.  
  
    > [!NOTE]
    >  La aplicación creada en este tutorial se ejecuta con distintas versiones de Microsoft Office debido a la información de tipo de interoperabilidad incrustado. Si el `Embed Interop Types` propiedad se establece en `False`, debe incluir un PIA para cada versión de Microsoft Office que la aplicación se ejecutará con.  
  
7.  Abra el archivo Module1.vb. Reemplace el código en el archivo con el código siguiente:  
  
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
  
9. Presione CTRL + F5 para compilar y ejecutar el proyecto. Compruebe que se ha creado un libro de Excel en la ubicación especificada en el código de ejemplo: C:\SampleFolder\SampleWorkbook.xls.  
  
##  <a name="BKMK_publishapp"></a>Para publicar la aplicación en un equipo en el que se instala una versión diferente de Microsoft Office  
  
1.  Abra el proyecto creado por este tutorial en Visual Studio.  
  
2.  En el **crear** menú, elija **publicar CreateExcelWorkbook**. Siga los pasos del Asistente para publicación para crear una versión instalable de la aplicación. Para obtener más información, consulte [Asistente para publicación (desarrollo de Office en Visual Studio)](https://msdn.microsoft.com/library/bb625071).  
  
3.  Instalar la aplicación en un equipo en el que estén instalados .NET Framework 4 o superior y una versión diferente de Excel.  
  
4.  Cuando finalice la instalación, ejecute el programa de instalación.  
  
5.  Compruebe que se ha creado un libro de Excel en la ubicación especificada en el código de ejemplo: C:\SampleFolder\SampleWorkbook.xls.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Incrustar los tipos de los ensamblados administrados en Visual Studio (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)   
 [/Link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)


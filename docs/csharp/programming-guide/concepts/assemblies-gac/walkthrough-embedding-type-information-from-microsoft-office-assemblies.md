---
title: 'Tutorial: Insertar información de tipos de los ensamblados de Microsoft Office en Visual Studio (C#)'
ms.date: 07/20/2015
ms.assetid: 3320e866-01f1-4b7f-8932-049a7b2d2a9b
ms.openlocfilehash: 381173eedc209930e011dfa7f1711167f16d5ef6
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44187973"
---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-c"></a>Tutorial: Insertar información de tipos de los ensamblados de Microsoft Office en Visual Studio (C#)
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
  
4.  En el **Explorador de soluciones**, haga clic en el menú contextual de la carpeta **Referencias** y, después, seleccione **Agregar referencia**.  
  
5.  En la pestaña **.NET**, elija la versión más reciente de `Microsoft.Office.Interop.Excel`. Por ejemplo, **Microsoft.Office.Interop.Excel 14.0.0.0**. Elija el botón **Aceptar** .  
  
6.  En la lista de referencias para el proyecto **CreateExcelWorkbook**, seleccione la referencia para `Microsoft.Office.Interop.Excel` que agregó en el paso anterior. En la ventana **Propiedades**, asegúrese de que la propiedad `Embed Interop Types` esté establecida en `True`.  
  
    > [!NOTE]
    >  La aplicación creada en este tutorial se ejecuta con distintas versiones de Microsoft Office debido a la información de tipo de interoperabilidad insertada. Si la propiedad `Embed Interop Types` está establecida en `False`, debe incluir un PIA para cada versión de Microsoft Office con la que se ejecute la aplicación.  
  
7.  Abra el archivo **Program.cs**. Reemplace el código de este archivo por el código siguiente:  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.IO;  
    using Excel = Microsoft.Office.Interop.Excel;  
  
    namespace CreateExcelWorkbook  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                int[] values = {4, 6, 18, 2, 1, 76, 0, 3, 11};  
  
                CreateWorkbook(values, @"C:\SampleFolder\SampleWorkbook.xls");  
            }  
  
            static void CreateWorkbook(int[] values, string filePath)  
            {  
                Excel.Application excelApp = null;  
                Excel.Workbook wkbk;  
                Excel.Worksheet sheet;  
  
                try  
                {  
                        // Start Excel and create a workbook and worksheet.  
                        excelApp = new Excel.Application();  
                        wkbk = excelApp.Workbooks.Add();  
                        sheet = wkbk.Sheets.Add() as Excel.Worksheet;  
                        sheet.Name = "Sample Worksheet";  
  
                        // Write a column of values.  
                        // In the For loop, both the row index and array index start at 1.  
                        // Therefore the value of 4 at array index 0 is not included.  
                        for (int i = 1; i < values.Length; i++)  
                        {  
                            sheet.Cells[i, 1] = values[i];  
                        }  
  
                        // Suppress any alerts and save the file. Create the directory   
                        // if it does not exist. Overwrite the file if it exists.  
                        excelApp.DisplayAlerts = false;  
                        string folderPath = Path.GetDirectoryName(filePath);  
                        if (!Directory.Exists(folderPath))  
                        {  
                            Directory.CreateDirectory(folderPath);  
                        }  
                        wkbk.SaveAs(filePath);  
                }  
                catch  
                {  
                }  
                finally  
                {  
                    sheet = null;  
                    wkbk = null;  
  
                    // Close Excel.  
                    excelApp.Quit();  
                    excelApp = null;  
                }  
            }  
        }  
    }  
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

- [Tutorial: Incrustar los tipos de los ensamblados administrados en Visual Studio (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)  
- [/link (Opciones del compilador de C#)](../../../../csharp/language-reference/compiler-options/link-compiler-option.md)

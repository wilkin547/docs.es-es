---
title: "Tutorial: Insertar información de tipos de los ensamblados de Microsoft Office en Visual Studio (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 3320e866-01f1-4b7f-8932-049a7b2d2a9b
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 45ec4521da08a9a1f4bdc3b433d3f8d765960526
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-c"></a><span data-ttu-id="5e9ea-102">Tutorial: Insertar información de tipos de los ensamblados de Microsoft Office en Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="5e9ea-102">Walkthrough: Embedding Type Information from Microsoft Office Assemblies in Visual Studio (C#)</span></span>
<span data-ttu-id="5e9ea-103">Si inserta la de tipos en una aplicación que hace referencia a objetos COM, puede eliminar la necesidad de un ensamblado de interoperabilidad primario (PIA).</span><span class="sxs-lookup"><span data-stu-id="5e9ea-103">If you embed type information in an application that references COM objects, you can eliminate the need for a primary interop assembly (PIA).</span></span> <span data-ttu-id="5e9ea-104">Además, la información de tipo incrustada permite que la versión de la aplicación gane en independencia.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-104">Additionally, the embedded type information enables you to achieve version independence for your application.</span></span> <span data-ttu-id="5e9ea-105">Es decir, el programa puede escribirse de modo que use tipos de varias versiones de una biblioteca COM sin necesidad de requerir un PIA específico para cada versión.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-105">That is, your program can be written to use types from multiple versions of a COM library without requiring a specific PIA for each version.</span></span> <span data-ttu-id="5e9ea-106">Se trata de un escenario común para las aplicaciones que usan objetos de las bibliotecas de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-106">This is a common scenario for applications that use objects from Microsoft Office libraries.</span></span> <span data-ttu-id="5e9ea-107">La inserción de la información de tipos permite que la misma compilación de un programa funcione con distintas versiones de Microsoft Office en equipos diferentes sin necesidad de volver a implementar el programa o el PIA para cada versión de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-107">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers without the need to redeploy either the program or the PIA for each version of Microsoft Office.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a><span data-ttu-id="5e9ea-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5e9ea-108">Prerequisites</span></span>  
 <span data-ttu-id="5e9ea-109">En este tutorial se requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e9ea-109">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="5e9ea-110">Un equipo en el que estén instalados Visual Studio y Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-110">A computer on which Visual Studio and Microsoft Excel are installed.</span></span>  
  
-   <span data-ttu-id="5e9ea-111">Un segundo equipo en el que estén instalados .NET Framework 4 o superior y una versión diferente de Excel.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-111">A second computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
##  <span data-ttu-id="5e9ea-112"><a name="BKMK_createapp"></a> Para crear una aplicación que funcione con varias versiones de Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="5e9ea-112"><a name="BKMK_createapp"></a> To create an application that works with multiple versions of Microsoft Office</span></span>  
  
1.  <span data-ttu-id="5e9ea-113">Inicie Visual Studio en un equipo en el que esté instalado Excel.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-113">Start Visual Studio on a computer on which Excel is installed.</span></span>  
  
2.  <span data-ttu-id="5e9ea-114">En el menú **Archivo** , elija **Nuevo**, **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-114">On the **File** menu, choose **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="5e9ea-115">En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-115">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="5e9ea-116">Seleccione **Aplicación de consola** en el panel **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-116">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="5e9ea-117">En el cuadro **Nombre**, escriba `CreateExcelWorkbook` y seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-117">In the **Name** box, enter `CreateExcelWorkbook`, and then choose the **OK** button.</span></span> <span data-ttu-id="5e9ea-118">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-118">The new project is created.</span></span>  
  
4.  <span data-ttu-id="5e9ea-119">En el **Explorador de soluciones**, haga clic en el menú contextual de la carpeta **Referencias** y, después, seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-119">In **Solution Explorer**, open the shortcut menu for the **References** folder and then choose **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="5e9ea-120">En la pestaña **.NET**, elija la versión más reciente de `Microsoft.Office.Interop.Excel`.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-120">On the **.NET** tab, choose the most recent version of `Microsoft.Office.Interop.Excel`.</span></span> <span data-ttu-id="5e9ea-121">Por ejemplo, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-121">For example, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span></span> <span data-ttu-id="5e9ea-122">Elija el botón **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="5e9ea-122">Choose the **OK** button.</span></span>  
  
6.  <span data-ttu-id="5e9ea-123">En la lista de referencias para el proyecto **CreateExcelWorkbook**, seleccione la referencia para `Microsoft.Office.Interop.Excel` que agregó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-123">In the list of references for the **CreateExcelWorkbook** project, select the reference for `Microsoft.Office.Interop.Excel` that you added in the previous step.</span></span> <span data-ttu-id="5e9ea-124">En la ventana **Propiedades**, asegúrese de que la propiedad `Embed Interop Types` esté establecida en `True`.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-124">In the **Properties** window, make sure that the `Embed Interop Types` property is set to `True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e9ea-125">La aplicación creada en este tutorial se ejecuta con distintas versiones de Microsoft Office debido a la información de tipo de interoperabilidad insertada.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-125">The application created in this walkthrough runs with different versions of Microsoft Office because of the embedded interop type information.</span></span> <span data-ttu-id="5e9ea-126">Si la propiedad `Embed Interop Types` está establecida en `False`, debe incluir un PIA para cada versión de Microsoft Office con la que se ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-126">If the `Embed Interop Types` property is set to `False`, you must include a PIA for each version of Microsoft Office that the application will run with.</span></span>  
  
7.  <span data-ttu-id="5e9ea-127">Abra el archivo **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-127">Open the **Program.cs** file.</span></span> <span data-ttu-id="5e9ea-128">Reemplace el código de este archivo por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e9ea-128">Replace the code in the file with the following code:</span></span>  
  
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
  
8.  <span data-ttu-id="5e9ea-129">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-129">Save the project.</span></span>  
  
9. <span data-ttu-id="5e9ea-130">Pulse CTRL+F5 para compilar y ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-130">Press CTRL+F5 to build and run the project.</span></span> <span data-ttu-id="5e9ea-131">Compruebe que se ha creado un libro de Excel en la ubicación especificada en el código de ejemplo: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-131">Verify that an Excel workbook has been created at the location specified in the example code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
##  <span data-ttu-id="5e9ea-132"><a name="BKMK_publishapp"></a> Para publicar la aplicación en un equipo en el que está instalada una versión diferente de Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="5e9ea-132"><a name="BKMK_publishapp"></a> To publish the application to a computer on which a different version of Microsoft Office is installed</span></span>  
  
1.  <span data-ttu-id="5e9ea-133">Abra el proyecto creado mediante este tutorial en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-133">Open the project created by this walkthrough in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="5e9ea-134">En el menú **Compilar**, elija **Publicar CreateExcelWorkbook**.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-134">On the **Build** menu, choose **Publish CreateExcelWorkbook**.</span></span> <span data-ttu-id="5e9ea-135">Siga los pasos del Asistente para publicación para crear una versión instalable de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-135">Follow the steps of the Publish Wizard to create an installable version of the application.</span></span> <span data-ttu-id="5e9ea-136">Para obtener más información, vea [Asistente para publicación (Desarrollo de Office en Visual Studio)](https://msdn.microsoft.com/library/bb625071).</span><span class="sxs-lookup"><span data-stu-id="5e9ea-136">For more information, see [Publish Wizard (Office Development in Visual Studio)](https://msdn.microsoft.com/library/bb625071).</span></span>  
  
3.  <span data-ttu-id="5e9ea-137">Instale la aplicación en un equipo en el que estén instalados .NET Framework 4 o superior y una versión diferente de Excel.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-137">Install the application on a computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
4.  <span data-ttu-id="5e9ea-138">Cuando finalice la instalación, ejecute el programa instalado.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-138">When the installation is finished, run the installed program.</span></span>  
  
5.  <span data-ttu-id="5e9ea-139">Compruebe que se ha creado un libro de Excel en la ubicación especificada en el código de ejemplo: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="5e9ea-139">Verify that an Excel workbook has been created at the location specified in the sample code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e9ea-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e9ea-140">See Also</span></span>  
 [<span data-ttu-id="5e9ea-141">Tutorial: Incrustar los tipos de los ensamblados administrados en Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="5e9ea-141">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)  
 [<span data-ttu-id="5e9ea-142">/link (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="5e9ea-142">/link (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/link-compiler-option.md)

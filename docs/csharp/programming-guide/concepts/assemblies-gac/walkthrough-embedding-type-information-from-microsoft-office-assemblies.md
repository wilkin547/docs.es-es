---
title: 'Tutorial: Inserción de información de tipos de los ensamblados de Microsoft Office en Visual Studio (C#)'
ms.date: 07/20/2015
ms.assetid: 3320e866-01f1-4b7f-8932-049a7b2d2a9b
ms.openlocfilehash: 20ed45b1796062973a1d4a9bcaa86782655d3867
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732705"
---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-c"></a><span data-ttu-id="f7d1b-102">Tutorial: Inserción de información de tipos de los ensamblados de Microsoft Office en Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="f7d1b-102">Walkthrough: Embedding Type Information from Microsoft Office Assemblies in Visual Studio (C#)</span></span>
<span data-ttu-id="f7d1b-103">Si inserta la de tipos en una aplicación que hace referencia a objetos COM, puede eliminar la necesidad de un ensamblado de interoperabilidad primario (PIA).</span><span class="sxs-lookup"><span data-stu-id="f7d1b-103">If you embed type information in an application that references COM objects, you can eliminate the need for a primary interop assembly (PIA).</span></span> <span data-ttu-id="f7d1b-104">Además, la información de tipo incrustada permite que la versión de la aplicación gane en independencia.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-104">Additionally, the embedded type information enables you to achieve version independence for your application.</span></span> <span data-ttu-id="f7d1b-105">Es decir, el programa puede escribirse de modo que use tipos de varias versiones de una biblioteca COM sin necesidad de requerir un PIA específico para cada versión.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-105">That is, your program can be written to use types from multiple versions of a COM library without requiring a specific PIA for each version.</span></span> <span data-ttu-id="f7d1b-106">Se trata de un escenario común para las aplicaciones que usan objetos de las bibliotecas de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-106">This is a common scenario for applications that use objects from Microsoft Office libraries.</span></span> <span data-ttu-id="f7d1b-107">La inserción de la información de tipos permite que la misma compilación de un programa funcione con distintas versiones de Microsoft Office en equipos diferentes sin necesidad de volver a implementar el programa o el PIA para cada versión de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-107">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers without the need to redeploy either the program or the PIA for each version of Microsoft Office.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a><span data-ttu-id="f7d1b-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f7d1b-108">Prerequisites</span></span>  
 <span data-ttu-id="f7d1b-109">En este tutorial se requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7d1b-109">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="f7d1b-110">Un equipo en el que estén instalados Visual Studio y Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-110">A computer on which Visual Studio and Microsoft Excel are installed.</span></span>  
  
-   <span data-ttu-id="f7d1b-111">Un segundo equipo en el que estén instalados .NET Framework 4 o superior y una versión diferente de Excel.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-111">A second computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
##  <a name="BKMK_createapp"></a> <span data-ttu-id="f7d1b-112">Para crear una aplicación que funcione con varias versiones de Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="f7d1b-112">To create an application that works with multiple versions of Microsoft Office</span></span>  
  
1.  <span data-ttu-id="f7d1b-113">Inicie Visual Studio en un equipo en el que esté instalado Excel.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-113">Start Visual Studio on a computer on which Excel is installed.</span></span>  
  
2.  <span data-ttu-id="f7d1b-114">En el menú **Archivo** , elija **Nuevo**, **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-114">On the **File** menu, choose **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="f7d1b-115">En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-115">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="f7d1b-116">Seleccione **Aplicación de consola** en el panel **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-116">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="f7d1b-117">En el cuadro **Nombre**, escriba `CreateExcelWorkbook` y seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-117">In the **Name** box, enter `CreateExcelWorkbook`, and then choose the **OK** button.</span></span> <span data-ttu-id="f7d1b-118">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-118">The new project is created.</span></span>  
  
4.  <span data-ttu-id="f7d1b-119">En el **Explorador de soluciones**, haga clic en el menú contextual de la carpeta **Referencias** y, después, seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-119">In **Solution Explorer**, open the shortcut menu for the **References** folder and then choose **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="f7d1b-120">En la pestaña **.NET**, elija la versión más reciente de `Microsoft.Office.Interop.Excel`.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-120">On the **.NET** tab, choose the most recent version of `Microsoft.Office.Interop.Excel`.</span></span> <span data-ttu-id="f7d1b-121">Por ejemplo, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-121">For example, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span></span> <span data-ttu-id="f7d1b-122">Elija el botón **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="f7d1b-122">Choose the **OK** button.</span></span>  
  
6.  <span data-ttu-id="f7d1b-123">En la lista de referencias para el proyecto **CreateExcelWorkbook**, seleccione la referencia para `Microsoft.Office.Interop.Excel` que agregó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-123">In the list of references for the **CreateExcelWorkbook** project, select the reference for `Microsoft.Office.Interop.Excel` that you added in the previous step.</span></span> <span data-ttu-id="f7d1b-124">En la ventana **Propiedades**, asegúrese de que la propiedad `Embed Interop Types` esté establecida en `True`.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-124">In the **Properties** window, make sure that the `Embed Interop Types` property is set to `True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f7d1b-125">La aplicación creada en este tutorial se ejecuta con distintas versiones de Microsoft Office debido a la información de tipo de interoperabilidad insertada.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-125">The application created in this walkthrough runs with different versions of Microsoft Office because of the embedded interop type information.</span></span> <span data-ttu-id="f7d1b-126">Si la propiedad `Embed Interop Types` está establecida en `False`, debe incluir un PIA para cada versión de Microsoft Office con la que se ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-126">If the `Embed Interop Types` property is set to `False`, you must include a PIA for each version of Microsoft Office that the application will run with.</span></span>  
  
7.  <span data-ttu-id="f7d1b-127">Abra el archivo **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-127">Open the **Program.cs** file.</span></span> <span data-ttu-id="f7d1b-128">Reemplace el código de este archivo por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7d1b-128">Replace the code in the file with the following code:</span></span>  
  
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
  
8.  <span data-ttu-id="f7d1b-129">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-129">Save the project.</span></span>  
  
9. <span data-ttu-id="f7d1b-130">Pulse CTRL+F5 para compilar y ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-130">Press CTRL+F5 to build and run the project.</span></span> <span data-ttu-id="f7d1b-131">Compruebe que se ha creado un libro de Excel en la ubicación especificada en el código de ejemplo: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-131">Verify that an Excel workbook has been created at the location specified in the example code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
##  <a name="BKMK_publishapp"></a> <span data-ttu-id="f7d1b-132">Para publicar la aplicación en un equipo en el que está instalada una versión diferente de Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="f7d1b-132">To publish the application to a computer on which a different version of Microsoft Office is installed</span></span>  
  
1.  <span data-ttu-id="f7d1b-133">Abra el proyecto creado mediante este tutorial en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-133">Open the project created by this walkthrough in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="f7d1b-134">En el menú **Compilar**, elija **Publicar CreateExcelWorkbook**.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-134">On the **Build** menu, choose **Publish CreateExcelWorkbook**.</span></span> <span data-ttu-id="f7d1b-135">Siga los pasos del Asistente para publicación para crear una versión instalable de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-135">Follow the steps of the Publish Wizard to create an installable version of the application.</span></span> <span data-ttu-id="f7d1b-136">Para obtener más información, vea [Asistente para publicación (Desarrollo de Office en Visual Studio)](/visualstudio/vsto/publish-wizard-office-development-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="f7d1b-136">For more information, see [Publish Wizard (Office Development in Visual Studio)](/visualstudio/vsto/publish-wizard-office-development-in-visual-studio).</span></span>  
  
3.  <span data-ttu-id="f7d1b-137">Instale la aplicación en un equipo en el que estén instalados .NET Framework 4 o superior y una versión diferente de Excel.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-137">Install the application on a computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
4.  <span data-ttu-id="f7d1b-138">Cuando finalice la instalación, ejecute el programa instalado.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-138">When the installation is finished, run the installed program.</span></span>  
  
5.  <span data-ttu-id="f7d1b-139">Compruebe que se ha creado un libro de Excel en la ubicación especificada en el código de ejemplo: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="f7d1b-139">Verify that an Excel workbook has been created at the location specified in the sample code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7d1b-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7d1b-140">See also</span></span>

- [<span data-ttu-id="f7d1b-141">Tutorial: Incrustar los tipos de los ensamblados administrados en Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="f7d1b-141">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)
- [<span data-ttu-id="f7d1b-142">/link (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="f7d1b-142">/link (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/link-compiler-option.md)

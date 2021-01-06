---
title: Procedimiento para usar argumentos opcionales y con nombre en la programación de Office - Guía de programación de C#
description: Aprenda a usar argumentos con nombre y argumentos opcionales para facilitar el acceso a interfaces COM, como las API de automatización de Microsoft Office.
ms.date: 07/20/2015
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
ms.openlocfilehash: de0545131385c13a79fd35df74e3a04da98ad8fb
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512481"
---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a><span data-ttu-id="a8b3e-103">Procedimiento para usar argumentos opcionales y con nombre en la programación de Office (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="a8b3e-103">How to use named and optional arguments in Office programming (C# Programming Guide)</span></span>

<span data-ttu-id="a8b3e-104">Los argumentos con nombre y los argumentos opcionales, introducidos en C# 4, mejoran la comodidad, la flexibilidad y la legibilidad en la programación de C#.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-104">Named arguments and optional arguments, introduced in C# 4, enhance convenience, flexibility, and readability in C# programming.</span></span> <span data-ttu-id="a8b3e-105">Además, estas características facilitan enormemente el acceso a interfaces COM, como las API de automatización de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-105">In addition, these features greatly facilitate access to COM interfaces such as the Microsoft Office automation APIs.</span></span>

<span data-ttu-id="a8b3e-106">En el ejemplo siguiente, el método [ConvertToTable](<xref:Microsoft.Office.Interop.Word.Range.ConvertToTable%2A>) tiene dieciséis parámetros que representan las características de una tabla, como el número de columnas y filas, el formato, los bordes, las fuentes y los colores.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-106">In the following example, method [ConvertToTable](<xref:Microsoft.Office.Interop.Word.Range.ConvertToTable%2A>) has sixteen parameters that represent characteristics of a table, such as number of columns and rows, formatting, borders, fonts, and colors.</span></span> <span data-ttu-id="a8b3e-107">Los dieciséis parámetros son opcionales, ya que la mayoría de las veces no interesa especificar valores concretos para todos ellos.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-107">All sixteen parameters are optional, because most of the time you do not want to specify particular values for all of them.</span></span> <span data-ttu-id="a8b3e-108">Pero si no hay argumentos opcionales y con nombre, es necesario proporcionar un valor o un valor de marcador de posición para cada parámetro.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-108">However, without named and optional arguments, a value or a placeholder value has to be provided for each parameter.</span></span> <span data-ttu-id="a8b3e-109">Con los argumentos opcionales y con nombre, puede especificar valores solamente para los parámetros necesarios para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-109">With named and optional arguments, you specify values only for the parameters that are required for your project.</span></span>

<span data-ttu-id="a8b3e-110">Debe tener Microsoft Office Word instalado en el equipo para completar estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-110">You must have Microsoft Office Word installed on your computer to complete these procedures.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-new-console-application"></a><span data-ttu-id="a8b3e-111">Para crear una aplicación de consola nueva</span><span class="sxs-lookup"><span data-stu-id="a8b3e-111">To create a new console application</span></span>

1. <span data-ttu-id="a8b3e-112">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-112">Start Visual Studio.</span></span>

2. <span data-ttu-id="a8b3e-113">En el menú **Archivo** , elija **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-113">On the **File** menu, point to **New**, and then click **Project**.</span></span>

3. <span data-ttu-id="a8b3e-114">En el panel **Templates Categories** (Categorías de plantillas), expanda **Visual C#** y haga clic en **Windows**.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-114">In the **Templates Categories** pane, expand **Visual C#**, and then click **Windows**.</span></span>

4. <span data-ttu-id="a8b3e-115">En la parte superior del panel **Plantillas**, asegúrese de que **.NET Framework 4** aparece en el cuadro **Plataforma de destino**.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-115">Look in the top of the **Templates** pane to make sure that **.NET Framework 4** appears in the **Target Framework** box.</span></span>

5. <span data-ttu-id="a8b3e-116">En el panel **Plantillas**, haga clic en **Aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-116">In the **Templates** pane, click **Console Application**.</span></span>

6. <span data-ttu-id="a8b3e-117">Escriba un nombre para el proyecto en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-117">Type a name for your project in the **Name** field.</span></span>

7. <span data-ttu-id="a8b3e-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-118">Click **OK**.</span></span>

     <span data-ttu-id="a8b3e-119">El proyecto nuevo aparece en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-119">The new project appears in **Solution Explorer**.</span></span>

## <a name="to-add-a-reference"></a><span data-ttu-id="a8b3e-120">Para agregar una referencia</span><span class="sxs-lookup"><span data-stu-id="a8b3e-120">To add a reference</span></span>

1. <span data-ttu-id="a8b3e-121">En el **Explorador de soluciones**, haga clic con el botón derecho en el nombre del proyecto y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-121">In **Solution Explorer**, right-click your project's name and then click **Add Reference**.</span></span> <span data-ttu-id="a8b3e-122">Aparecerá el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-122">The **Add Reference** dialog box appears.</span></span>

2. <span data-ttu-id="a8b3e-123">En la página **.NET**, seleccione **Microsoft.Office.Interop.Word** en la lista **Nombre de componente**.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-123">On the **.NET** page, select **Microsoft.Office.Interop.Word** in the **Component Name** list.</span></span>

3. <span data-ttu-id="a8b3e-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-124">Click **OK**.</span></span>

## <a name="to-add-necessary-using-directives"></a><span data-ttu-id="a8b3e-125">Para agregar las directivas using necesarias</span><span class="sxs-lookup"><span data-stu-id="a8b3e-125">To add necessary using directives</span></span>

1. <span data-ttu-id="a8b3e-126">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *Program.cs* y, después, haga clic en **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-126">In **Solution Explorer**, right-click the *Program.cs* file and then click **View Code**.</span></span>

2. <span data-ttu-id="a8b3e-127">Agregue las directivas `using` siguientes a la parte superior del archivo de código:</span><span class="sxs-lookup"><span data-stu-id="a8b3e-127">Add the following `using` directives to the top of the code file:</span></span>

     [!code-csharp[csProgGuideNamedAndOptional#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#4)]

## <a name="to-display-text-in-a-word-document"></a><span data-ttu-id="a8b3e-128">Para mostrar texto en un documento de Word</span><span class="sxs-lookup"><span data-stu-id="a8b3e-128">To display text in a Word document</span></span>

1. <span data-ttu-id="a8b3e-129">En la clase `Program` en *Program.cs*, agregue el método siguiente para crear una aplicación de Word y un documento de Word.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-129">In the `Program` class in *Program.cs*, add the following method to create a Word application and a Word document.</span></span> <span data-ttu-id="a8b3e-130">El método [Add](<xref:Microsoft.Office.Interop.Word.Documents.Add%2A>) tiene cuatro parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-130">The [Add](<xref:Microsoft.Office.Interop.Word.Documents.Add%2A>) method has four optional parameters.</span></span> <span data-ttu-id="a8b3e-131">En este ejemplo se usan los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-131">This example uses their default values.</span></span> <span data-ttu-id="a8b3e-132">Por lo tanto, no se necesitan argumentos en la instrucción de llamada.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-132">Therefore, no arguments are necessary in the calling statement.</span></span>

     [!code-csharp[csProgGuideNamedAndOptional#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#6)]

2. <span data-ttu-id="a8b3e-133">Agregue el código siguiente al final del método para definir dónde se muestra texto en el documento y qué texto se muestra:</span><span class="sxs-lookup"><span data-stu-id="a8b3e-133">Add the following code at the end of the method to define where to display text in the document, and what text to display:</span></span>

     [!code-csharp[csProgGuideNamedAndOptional#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#7)]

## <a name="to-run-the-application"></a><span data-ttu-id="a8b3e-134">Para ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="a8b3e-134">To run the application</span></span>

1. <span data-ttu-id="a8b3e-135">Agregue la instrucción siguiente a Principal:</span><span class="sxs-lookup"><span data-stu-id="a8b3e-135">Add the following statement to Main:</span></span>

     [!code-csharp[csProgGuideNamedAndOptional#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#8)]

2. <span data-ttu-id="a8b3e-136">Presione <kbd>CTRL</kbd>+<kbd>F5</kbd> para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-136">Press <kbd>CTRL</kbd>+<kbd>F5</kbd> to run the project.</span></span> <span data-ttu-id="a8b3e-137">Aparecerá un documento de Word con el texto especificado.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-137">A Word document appears that contains the specified text.</span></span>

## <a name="to-change-the-text-to-a-table"></a><span data-ttu-id="a8b3e-138">Para convertir el texto en tabla</span><span class="sxs-lookup"><span data-stu-id="a8b3e-138">To change the text to a table</span></span>
  
1. <span data-ttu-id="a8b3e-139">Use el método `ConvertToTable` para incluir el texto en una tabla.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-139">Use the `ConvertToTable` method to enclose the text in a table.</span></span> <span data-ttu-id="a8b3e-140">El método tiene 16 parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-140">The method has sixteen optional parameters.</span></span> <span data-ttu-id="a8b3e-141">IntelliSense coloca los parámetros opcionales entre corchetes, tal como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-141">IntelliSense encloses optional parameters in brackets, as shown in the following illustration.</span></span>

     ![Lista de parámetros para el método ConvertToTable](./media/how-to-use-named-and-optional-arguments-in-office-programming/convert-table-parameters.png)

     <span data-ttu-id="a8b3e-143">Los argumentos opcionales y con nombre permiten especificar valores solo para los parámetros que quiere cambiar.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-143">Named and optional arguments enable you to specify values for only the parameters that you want to change.</span></span> <span data-ttu-id="a8b3e-144">Agregue el código siguiente al final del método `DisplayInWord` para crear una tabla simple.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-144">Add the following code to the end of method `DisplayInWord` to create a simple table.</span></span> <span data-ttu-id="a8b3e-145">El argumento especifica que las comas de la cadena de texto de `range` separan las celdas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-145">The argument specifies that the commas in the text string in `range` separate the cells of the table.</span></span>

     [!code-csharp[csProgGuideNamedAndOptional#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#9)]

     <span data-ttu-id="a8b3e-146">En versiones anteriores de C#, la llamada a `ConvertToTable` requiere un argumento de referencia para cada parámetro, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8b3e-146">In earlier versions of C#, the call to `ConvertToTable` requires a reference argument for each parameter, as shown in the following code:</span></span>
  
     [!code-csharp[csProgGuideNamedAndOptional#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#14)]

2. <span data-ttu-id="a8b3e-147">Presione <kbd>CTRL</kbd>+<kbd>F5</kbd> para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-147">Press <kbd>CTRL</kbd>+<kbd>F5</kbd> to run the project.</span></span>

## <a name="to-experiment-with-other-parameters"></a><span data-ttu-id="a8b3e-148">Para experimentar con otros parámetros</span><span class="sxs-lookup"><span data-stu-id="a8b3e-148">To experiment with other parameters</span></span>

1. <span data-ttu-id="a8b3e-149">Para cambiar la tabla de modo que tenga una columna y tres filas, reemplace la última línea de `DisplayInWord` por la instrucción siguiente y escriba <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-149">To change the table so that it has one column and three rows, replace the last line in `DisplayInWord` with the following statement and then type <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span></span>  

     [!code-csharp[csProgGuideNamedAndOptional#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#10)]

2. <span data-ttu-id="a8b3e-150">Para especificar un formato predefinido para la tabla, reemplace la última línea de `DisplayInWord` por la instrucción siguiente y escriba <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a8b3e-150">To specify a predefined format for the table, replace the last line in `DisplayInWord` with the following statement and then type <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span></span> <span data-ttu-id="a8b3e-151">El formato puede ser cualquiera de las constantes [WdTableFormat](<xref:Microsoft.Office.Interop.Word.WdTableFormat>).</span><span class="sxs-lookup"><span data-stu-id="a8b3e-151">The format can be any of the [WdTableFormat](<xref:Microsoft.Office.Interop.Word.WdTableFormat>) constants.</span></span>

     [!code-csharp[csProgGuideNamedAndOptional#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#11)]

## <a name="example"></a><span data-ttu-id="a8b3e-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8b3e-152">Example</span></span>

<span data-ttu-id="a8b3e-153">En el código siguiente se incluye el ejemplo completo:</span><span class="sxs-lookup"><span data-stu-id="a8b3e-153">The following code includes the full example:</span></span>

 [!code-csharp[csProgGuideNamedAndOptional#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#12)]

## <a name="see-also"></a><span data-ttu-id="a8b3e-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8b3e-154">See also</span></span>

- [<span data-ttu-id="a8b3e-155">Argumentos opcionales y con nombre</span><span class="sxs-lookup"><span data-stu-id="a8b3e-155">Named and Optional Arguments</span></span>](./named-and-optional-arguments.md)

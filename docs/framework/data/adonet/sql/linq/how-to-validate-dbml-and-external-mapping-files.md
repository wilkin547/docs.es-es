---
description: 'Más información acerca de cómo: validar archivos DBML y de asignación externa'
title: Procedimiento para validar archivos DBML y de asignación externa
ms.date: 03/30/2017
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
ms.openlocfilehash: 46e5c787bef8e152020fc97631ef8c1c4928fe74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785788"
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a><span data-ttu-id="cf191-103">Procedimiento para validar archivos DBML y de asignación externa</span><span class="sxs-lookup"><span data-stu-id="cf191-103">How to: Validate DBML and External Mapping Files</span></span>

<span data-ttu-id="cf191-104">Los archivos de asignación externa y los archivos .dbml que se modifican se deben validar con sus respectivas definiciones de esquema.</span><span class="sxs-lookup"><span data-stu-id="cf191-104">External mapping files and .dbml files that you modify must be validated against their respective schema definitions.</span></span> <span data-ttu-id="cf191-105">En este tema se proporciona a los usuarios de Visual Studio los pasos necesarios para implementar el proceso de validación.</span><span class="sxs-lookup"><span data-stu-id="cf191-105">This topic provides Visual Studio users with the steps to implement the validation process.</span></span>

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

### <a name="to-validate-a-dbml-or-xml-file"></a><span data-ttu-id="cf191-106">Para validar un archivo .dbml o XML</span><span class="sxs-lookup"><span data-stu-id="cf191-106">To validate a .dbml or XML file</span></span>

1. <span data-ttu-id="cf191-107">En el menú **archivo** de Visual Studio, elija **abrir** y, a continuación, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="cf191-107">On the Visual Studio **File** menu, point to **Open**, and then click **File**.</span></span>

2. <span data-ttu-id="cf191-108">En el cuadro de diálogo **Abrir archivo** , haga clic en el archivo de asignación. DBML o XML que desea validar.</span><span class="sxs-lookup"><span data-stu-id="cf191-108">In the **Open File** dialog box, click the .dbml or XML mapping file that you want to validate.</span></span>

    <span data-ttu-id="cf191-109">El archivo se abre en el **Editor XML**.</span><span class="sxs-lookup"><span data-stu-id="cf191-109">The file opens in the **XML Editor**.</span></span>

3. <span data-ttu-id="cf191-110">Haga clic con el botón secundario en la ventana y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cf191-110">Right-click the window, and then click **Properties**.</span></span>

4. <span data-ttu-id="cf191-111">En la ventana **propiedades** , haga clic en los puntos suspensivos de la propiedad **schemas** .</span><span class="sxs-lookup"><span data-stu-id="cf191-111">In the **Properties** window, click the ellipsis for the **Schemas** property.</span></span>

    <span data-ttu-id="cf191-112">Se abrirá el cuadro de diálogo **esquemas XML** .</span><span class="sxs-lookup"><span data-stu-id="cf191-112">The **XML Schemas** dialog box opens.</span></span>

5. <span data-ttu-id="cf191-113">Observe cuál es la definición de esquema adecuada para lo que desea.</span><span class="sxs-lookup"><span data-stu-id="cf191-113">Note the appropriate schema definition for your purpose.</span></span>

    - <span data-ttu-id="cf191-114">DbmlSchema.xsd es la definición de esquema para validar un archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="cf191-114">DbmlSchema.xsd is the schema definition for validating a .dbml file.</span></span> <span data-ttu-id="cf191-115">Para obtener más información, vea [generación de código en LINQ to SQL](code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="cf191-115">For more information, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md).</span></span>

    - <span data-ttu-id="cf191-116">LinqToSqlMapping.xsd es la definición de esquema para validar un archivo XML de asignación externa.</span><span class="sxs-lookup"><span data-stu-id="cf191-116">LinqToSqlMapping.xsd is the schema definition for validating an external XML mapping file.</span></span> <span data-ttu-id="cf191-117">Para obtener más información, consulte [asignación externa](external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="cf191-117">For more information, see [External Mapping](external-mapping.md).</span></span>

6. <span data-ttu-id="cf191-118">En la columna **usar** de la fila definición de esquema deseada, haga clic para abrir el cuadro desplegable y, a continuación, haga clic en **usar este esquema**.</span><span class="sxs-lookup"><span data-stu-id="cf191-118">In the **Use** column of the desired schema definition row, click to open the drop-down box, and then click **Use this schema**.</span></span>

    <span data-ttu-id="cf191-119">El archivo de definición de esquema está asociado ahora con su archivo de asignación DBML o XML.</span><span class="sxs-lookup"><span data-stu-id="cf191-119">The schema definition file is now associated with your DBML or XML mapping file.</span></span>

    <span data-ttu-id="cf191-120">Asegúrese de que no hay otras definiciones de esquema seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="cf191-120">Make sure no other schema definitions are selected.</span></span>

7. <span data-ttu-id="cf191-121">En el menú **Ver** , haga clic en **Lista de errores**.</span><span class="sxs-lookup"><span data-stu-id="cf191-121">On the **View** menu, click **Error List**.</span></span>

    <span data-ttu-id="cf191-122">Determine si se han generado errores, advertencias o mensajes.</span><span class="sxs-lookup"><span data-stu-id="cf191-122">Determine whether errors, warnings, or messages have been generated.</span></span> <span data-ttu-id="cf191-123">Si no, el archivo XML es válido respecto a la definición de esquema.</span><span class="sxs-lookup"><span data-stu-id="cf191-123">If not, the XML file is valid against the schema definition.</span></span>

## <a name="alternate-method-for-supplying-schema-definition"></a><span data-ttu-id="cf191-124">Método alternativo para proporcionar la definición de esquema</span><span class="sxs-lookup"><span data-stu-id="cf191-124">Alternate Method for Supplying Schema Definition</span></span>

<span data-ttu-id="cf191-125">Si, por alguna razón, el archivo. xsd correspondiente no aparece en el cuadro de diálogo **esquemas XML** , puede descargar el archivo. xsd de un tema de ayuda.</span><span class="sxs-lookup"><span data-stu-id="cf191-125">If for some reason the appropriate .xsd file does not appear in the **XML Schemas** dialog box, you can download the .xsd file from a Help topic.</span></span> <span data-ttu-id="cf191-126">Los siguientes pasos le ayudarán a guardar el archivo descargado en el formato Unicode requerido por el editor XML de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cf191-126">The following steps help you save the downloaded file in the Unicode format required by the Visual Studio XML Editor.</span></span>

#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a><span data-ttu-id="cf191-127">Para copiar un archivo de definición de esquema de un tema de Ayuda</span><span class="sxs-lookup"><span data-stu-id="cf191-127">To copy a schema definition file from a Help topic</span></span>

1. <span data-ttu-id="cf191-128">Busque el tema de Ayuda que contiene la definición de esquema tal como se ha descrito anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="cf191-128">Locate the Help topic that contains the schema definition as described earlier in this topic.</span></span>

    - <span data-ttu-id="cf191-129">Para los archivos. dbml, vea [generación de código en LINQ to SQL](code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="cf191-129">For .dbml files, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md).</span></span>

    - <span data-ttu-id="cf191-130">Para los archivos de asignación externa, consulte [asignación externa](external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="cf191-130">For external mapping files, see [External Mapping](external-mapping.md).</span></span>

2. <span data-ttu-id="cf191-131">Haga clic en **Copiar código** para copiar el archivo de código en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="cf191-131">Click **Copy Code** to copy the code file to the Clipboard.</span></span>

3. <span data-ttu-id="cf191-132">Inicie Bloc de notas para crear un nuevo archivo.</span><span class="sxs-lookup"><span data-stu-id="cf191-132">Start Notepad to create a new file.</span></span>

4. <span data-ttu-id="cf191-133">Pegue el código del Portapapeles en el archivo del Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="cf191-133">Paste the code from the clipboard into Notepad file.</span></span>

5. <span data-ttu-id="cf191-134">En el menú **archivo** del Bloc de notas, haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="cf191-134">On the Notepad **File** menu, click **Save As**.</span></span>

6. <span data-ttu-id="cf191-135">En el cuadro **codificación** , seleccione **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="cf191-135">In the **Encoding** box, select **Unicode**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cf191-136">Esta selección garantiza que el marcador de orden de bytes Unicode-16 (`FFFE`) se antepone al archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="cf191-136">This selection guarantees that the Unicode-16 byte-order marker (`FFFE`) is prepended to the text file.</span></span>

7. <span data-ttu-id="cf191-137">En el cuadro **nombre de archivo** , cree un nombre de archivo con la extensión. xsd.</span><span class="sxs-lookup"><span data-stu-id="cf191-137">In the **File name** box, create a file name with an .xsd extension.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf191-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf191-138">See also</span></span>

- [<span data-ttu-id="cf191-139">Referencia</span><span class="sxs-lookup"><span data-stu-id="cf191-139">Reference</span></span>](reference.md)

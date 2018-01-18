---
title: "Cómo: Validar archivos DBML y de asignación externa"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 7724586c33c19654c3657a5a4604a3c74f2c8756
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a><span data-ttu-id="4789e-102">Cómo: Validar archivos DBML y de asignación externa</span><span class="sxs-lookup"><span data-stu-id="4789e-102">How to: Validate DBML and External Mapping Files</span></span>
<span data-ttu-id="4789e-103">Los archivos de asignación externa y los archivos .dbml que se modifican se deben validar con sus respectivas definiciones de esquema.</span><span class="sxs-lookup"><span data-stu-id="4789e-103">External mapping files and .dbml files that you modify must be validated against their respective schema definitions.</span></span> <span data-ttu-id="4789e-104">En este tema se proporciona a los usuarios de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] los pasos necesarios para implementar el proceso de validación.</span><span class="sxs-lookup"><span data-stu-id="4789e-104">This topic provides [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] users with the steps to implement the validation process.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a><span data-ttu-id="4789e-105">Para validar un archivo .dbml o XML</span><span class="sxs-lookup"><span data-stu-id="4789e-105">To validate a .dbml or XML file</span></span>  
  
1.  <span data-ttu-id="4789e-106">En Visual Studio **archivo** menú, elija **abiertos**y, a continuación, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="4789e-106">On the Visual Studio **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="4789e-107">En el **archivos abiertos** diálogo cuadro, haga clic en el archivo .dbml o XML asignación que desea validar.</span><span class="sxs-lookup"><span data-stu-id="4789e-107">In the **Open File** dialog box, click the .dbml or XML mapping file that you want to validate.</span></span>  
  
     <span data-ttu-id="4789e-108">El archivo se abre en el **Editor XML**.</span><span class="sxs-lookup"><span data-stu-id="4789e-108">The file opens in the **XML Editor**.</span></span>  
  
3.  <span data-ttu-id="4789e-109">Haga clic en la ventana y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4789e-109">Right-click the window, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="4789e-110">En el **propiedades** ventana, haga clic en el botón de puntos suspensivos para la **esquemas** propiedad.</span><span class="sxs-lookup"><span data-stu-id="4789e-110">In the **Properties** window, click the ellipsis for the **Schemas** property.</span></span>  
  
     <span data-ttu-id="4789e-111">El **esquemas XML** abre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4789e-111">The **XML Schemas** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="4789e-112">Observe cuál es la definición de esquema adecuada para lo que desea.</span><span class="sxs-lookup"><span data-stu-id="4789e-112">Note the appropriate schema definition for your purpose.</span></span>  
  
    -   <span data-ttu-id="4789e-113">DbmlSchema.xsd es la definición de esquema para validar un archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="4789e-113">DbmlSchema.xsd is the schema definition for validating a .dbml file.</span></span> <span data-ttu-id="4789e-114">Para obtener más información, consulte [generación de código en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="4789e-114">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="4789e-115">LinqToSqlMapping.xsd es la definición de esquema para validar un archivo XML de asignación externa.</span><span class="sxs-lookup"><span data-stu-id="4789e-115">LinqToSqlMapping.xsd is the schema definition for validating an external XML mapping file.</span></span> <span data-ttu-id="4789e-116">Para obtener más información, consulte [asignación externa](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="4789e-116">For more information, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
6.  <span data-ttu-id="4789e-117">En el **Use** columna de la fila de la definición de esquema que desee, haga clic para abrir el cuadro de lista desplegable y, a continuación, haga clic en **utilizar este esquema**.</span><span class="sxs-lookup"><span data-stu-id="4789e-117">In the **Use** column of the desired schema definition row, click to open the drop-down box, and then click **Use this schema**.</span></span>  
  
     <span data-ttu-id="4789e-118">El archivo de definición de esquema está asociado ahora con su archivo de asignación DBML o XML.</span><span class="sxs-lookup"><span data-stu-id="4789e-118">The schema definition file is now associated with your DBML or XML mapping file.</span></span>  
  
     <span data-ttu-id="4789e-119">Asegúrese de que no hay otras definiciones de esquema seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="4789e-119">Make sure no other schema definitions are selected.</span></span>  
  
7.  <span data-ttu-id="4789e-120">En el **vista** menú, haga clic en **lista de errores**.</span><span class="sxs-lookup"><span data-stu-id="4789e-120">On the **View** menu, click **Error List**.</span></span>  
  
     <span data-ttu-id="4789e-121">Determine si se han generado errores, advertencias o mensajes.</span><span class="sxs-lookup"><span data-stu-id="4789e-121">Determine whether errors, warnings, or messages have been generated.</span></span> <span data-ttu-id="4789e-122">Si no, el archivo XML es válido respecto a la definición de esquema.</span><span class="sxs-lookup"><span data-stu-id="4789e-122">If not, the XML file is valid against the schema definition.</span></span>  
  
## <a name="alternate-method-for-supplying-schema-definition"></a><span data-ttu-id="4789e-123">Método alternativo para proporcionar la definición de esquema</span><span class="sxs-lookup"><span data-stu-id="4789e-123">Alternate Method for Supplying Schema Definition</span></span>  
 <span data-ttu-id="4789e-124">Si por alguna razón el .xsd adecuado archivo no aparece en la **esquemas XML** cuadro de diálogo, puede descargar el archivo .xsd de un tema de ayuda.</span><span class="sxs-lookup"><span data-stu-id="4789e-124">If for some reason the appropriate .xsd file does not appear in the **XML Schemas** dialog box, you can download the .xsd file from a Help topic.</span></span> <span data-ttu-id="4789e-125">Los pasos siguientes le indicarán cómo guardar el archivo descargado en el formato Unicode que requiere el Editor XML de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4789e-125">The following steps help you save the downloaded file in the Unicode format required by the [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] XML Editor.</span></span>  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a><span data-ttu-id="4789e-126">Para copiar un archivo de definición de esquema de un tema de Ayuda</span><span class="sxs-lookup"><span data-stu-id="4789e-126">To copy a schema definition file from a Help topic</span></span>  
  
1.  <span data-ttu-id="4789e-127">Busque el tema de Ayuda que contiene la definición de esquema tal como se ha descrito anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="4789e-127">Locate the Help topic that contains the schema definition as described earlier in this topic.</span></span>  
  
    -   <span data-ttu-id="4789e-128">Para los archivos .dbml, consulte [generación de código en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="4789e-128">For .dbml files, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="4789e-129">Para los archivos de asignación externo, vea [asignación externa](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="4789e-129">For external mapping files, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
2.  <span data-ttu-id="4789e-130">Haga clic en **copiar código** para copiar el archivo de código en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="4789e-130">Click **Copy Code** to copy the code file to the Clipboard.</span></span>  
  
3.  <span data-ttu-id="4789e-131">Inicie Bloc de notas para crear un nuevo archivo.</span><span class="sxs-lookup"><span data-stu-id="4789e-131">Start Notepad to create a new file.</span></span>  
  
4.  <span data-ttu-id="4789e-132">Pegue el código del Portapapeles en el archivo del Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="4789e-132">Paste the code from the clipboard into Notepad file.</span></span>  
  
5.  <span data-ttu-id="4789e-133">En el Bloc de notas **archivo** menú, haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="4789e-133">On the Notepad **File** menu, click **Save As**.</span></span>  
  
6.  <span data-ttu-id="4789e-134">En el **codificación** cuadro, seleccione **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="4789e-134">In the **Encoding** box, select **Unicode**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4789e-135">Esta selección garantiza que el marcador de orden de bytes Unicode-16 (`FFFE`) se antepone al archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4789e-135">This selection guarantees that the Unicode-16 byte-order marker (`FFFE`) is prepended to the text file.</span></span>  
  
7.  <span data-ttu-id="4789e-136">En el **nombre de archivo** cuadro, cree un nombre de archivo con una extensión .xsd.</span><span class="sxs-lookup"><span data-stu-id="4789e-136">In the **File name** box, create a file name with an .xsd extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4789e-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="4789e-137">See Also</span></span>  
 [<span data-ttu-id="4789e-138">Referencia</span><span class="sxs-lookup"><span data-stu-id="4789e-138">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)

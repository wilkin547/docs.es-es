---
title: "Cómo: Generar el modelo de objetos en Visual Basic o C#"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6ff5a314fb4264f57f1db3e8475a2e3105897f19
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a><span data-ttu-id="9774b-102">Cómo: Generar el modelo de objetos en Visual Basic o C#</span><span class="sxs-lookup"><span data-stu-id="9774b-102">How to: Generate the Object Model in Visual Basic or C#</span></span> #
<span data-ttu-id="9774b-103">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], un modelo de objetos en un lenguaje de programación se asigna a una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="9774b-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], an object model in your own programming language is mapped to a relational database.</span></span> <span data-ttu-id="9774b-104">Existen dos herramientas para generar automáticamente un [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] o un modelo de C# de los metadatos de una base de datos existente.</span><span class="sxs-lookup"><span data-stu-id="9774b-104">Two tools are available for automatically generating a [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# model from the metadata of an existing database.</span></span>  
  
-   <span data-ttu-id="9774b-105">Si programa en [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], puede utilizar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para generar un modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="9774b-105">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to generate an object model.</span></span> <span data-ttu-id="9774b-106">El [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] proporciona una interfaz de usuario enriquecida para ayudarle a generar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="9774b-106">The [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] provides a rich user interface to help you generate a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="9774b-107">Para obtener más información, vea [Linq to SQL Tools en Visual Studio](https://docs.microsoft.com/en-us/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="9774b-107">For more information see, [Linq to SQL Tools in Visual Studio](https://docs.microsoft.com/en-us/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>
  
-   <span data-ttu-id="9774b-108">Herramienta de línea de comandos SQLMetal</span><span class="sxs-lookup"><span data-stu-id="9774b-108">The SQLMetal command-line tool.</span></span> <span data-ttu-id="9774b-109">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="9774b-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9774b-110">Si no tiene una base de datos existente y desear crear una a partir de un modelo de objetos, puede crear el modelo de objetos mediante el editor de código y <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span><span class="sxs-lookup"><span data-stu-id="9774b-110">If you do not have an existing database and want to create one from an object model, you can create your object model by using your code editor and <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span></span> <span data-ttu-id="9774b-111">Para obtener más información, consulte [Cómo: crear dinámicamente una base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="9774b-111">For more information, see [How to: Dynamically Create a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).</span></span>  
  
 <span data-ttu-id="9774b-112">Documentación para el [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] se proporcionan ejemplos de cómo generar un [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] o modelo de objetos de C# mediante el uso de la [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9774b-112">Documentation for the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] provides examples of how to generate a [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# object model by using the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)].</span></span> <span data-ttu-id="9774b-113">En la información siguiente se proporcionan ejemplos del uso de la herramienta de línea de comandos de SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="9774b-113">The following information provide examples of how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="9774b-114">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="9774b-114">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9774b-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9774b-115">Example</span></span>  
 <span data-ttu-id="9774b-116">La línea de comandos de SQLMetal mostrada en el ejemplo siguiente genera código de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] como el modelo de objetos basado en atributos de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="9774b-116">The SQLMetal command line shown in the following example produces [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="9774b-117">Se presentan también los procedimientos almacenados y las funciones.</span><span class="sxs-lookup"><span data-stu-id="9774b-117">Stored procedures and functions are also rendered.</span></span>  
  
```  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a><span data-ttu-id="9774b-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9774b-118">Example</span></span>  
 <span data-ttu-id="9774b-119">La línea de comandos de SQLMetal mostrada en el ejemplo siguiente genera código de C# como el modelo de objetos basado en atributos de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="9774b-119">The SQLMetal command line shown in the following example produces C# code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="9774b-120">Se presentan también los procedimientos almacenados y las funciones, y los nombres de tabla se pluralizan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9774b-120">Stored procedures and functions are also rendered, and table names are automatically pluralized.</span></span>  
  
```  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a><span data-ttu-id="9774b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9774b-121">See Also</span></span>  
 [<span data-ttu-id="9774b-122">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="9774b-122">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 [<span data-ttu-id="9774b-123">El modelo de LINQ to SQL objeto</span><span class="sxs-lookup"><span data-stu-id="9774b-123">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="9774b-124">Aprender con tutoriales</span><span class="sxs-lookup"><span data-stu-id="9774b-124">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)  
 [<span data-ttu-id="9774b-125">Cómo: personalizar clases de entidad mediante el Editor de código</span><span class="sxs-lookup"><span data-stu-id="9774b-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 [<span data-ttu-id="9774b-126">Asignación basada en atributos</span><span class="sxs-lookup"><span data-stu-id="9774b-126">Attribute-Based Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)  
 [<span data-ttu-id="9774b-127">SqlMetal.exe (Herramienta de generación de código)</span><span class="sxs-lookup"><span data-stu-id="9774b-127">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [<span data-ttu-id="9774b-128">Asignación externa</span><span class="sxs-lookup"><span data-stu-id="9774b-128">External Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)  
 [<span data-ttu-id="9774b-129">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9774b-129">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="9774b-130">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="9774b-130">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)

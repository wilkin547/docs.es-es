---
description: 'Más información acerca de cómo: generar el modelo de objetos en Visual Basic o C #'
title: Procedimiento para generar el modelo de objetos en Visual Basic o C#
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: d842a646f9f6186d252d10297618ddc2cb137e70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785970"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a><span data-ttu-id="90689-103">Cómo: generar el modelo de objetos en Visual Basic o C\#</span><span class="sxs-lookup"><span data-stu-id="90689-103">How to: Generate the Object Model in Visual Basic or C\#</span></span>

<span data-ttu-id="90689-104">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], un modelo de objetos en un lenguaje de programación se asigna a una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="90689-104">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], an object model in your own programming language is mapped to a relational database.</span></span> <span data-ttu-id="90689-105">Hay dos herramientas disponibles para generar automáticamente un Visual Basic o un modelo de C# a partir de los metadatos de una base de datos existente.</span><span class="sxs-lookup"><span data-stu-id="90689-105">Two tools are available for automatically generating a Visual Basic or C# model from the metadata of an existing database.</span></span>  
  
- <span data-ttu-id="90689-106">Si usa Visual Studio, puede usar la Object Relational Designer para generar un modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="90689-106">If you are using Visual Studio, you can use the Object Relational Designer to generate an object model.</span></span> <span data-ttu-id="90689-107">Object Relational Designer proporciona una interfaz de usuario enriquecida para ayudarle a generar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="90689-107">The O/R Designer provides a rich user interface to help you generate a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="90689-108">Para obtener más información, vea [herramientas de LINQ to SQL en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="90689-108">For more information see, [Linq to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>
  
- <span data-ttu-id="90689-109">Herramienta de línea de comandos SQLMetal</span><span class="sxs-lookup"><span data-stu-id="90689-109">The SQLMetal command-line tool.</span></span> <span data-ttu-id="90689-110">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="90689-110">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="90689-111">Si no tiene una base de datos existente y desear crear una a partir de un modelo de objetos, puede crear el modelo de objetos mediante el editor de código y <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span><span class="sxs-lookup"><span data-stu-id="90689-111">If you do not have an existing database and want to create one from an object model, you can create your object model by using your code editor and <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span></span> <span data-ttu-id="90689-112">Para obtener más información, consulte [Cómo: crear dinámicamente una base de datos](how-to-dynamically-create-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="90689-112">For more information, see [How to: Dynamically Create a Database](how-to-dynamically-create-a-database.md).</span></span>  
  
 <span data-ttu-id="90689-113">En la documentación de O/R Designer se proporcionan ejemplos de cómo generar un modelo de objetos de Visual Basic o C# con Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="90689-113">Documentation for the O/R Designer provides examples of how to generate a Visual Basic or C# object model by using the O/R Designer.</span></span> <span data-ttu-id="90689-114">En la información siguiente se proporcionan ejemplos del uso de la herramienta de línea de comandos de SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="90689-114">The following information provide examples of how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="90689-115">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="90689-115">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="90689-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="90689-116">Example</span></span>  

 <span data-ttu-id="90689-117">La línea de comandos de SQLMetal mostrada en el ejemplo siguiente genera código Visual Basic como el modelo de objetos basado en atributos de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="90689-117">The SQLMetal command line shown in the following example produces Visual Basic code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="90689-118">Se presentan también los procedimientos almacenados y las funciones.</span><span class="sxs-lookup"><span data-stu-id="90689-118">Stored procedures and functions are also rendered.</span></span>  
  
```console  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a><span data-ttu-id="90689-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="90689-119">Example</span></span>  

 <span data-ttu-id="90689-120">La línea de comandos de SQLMetal mostrada en el ejemplo siguiente genera código de C# como el modelo de objetos basado en atributos de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="90689-120">The SQLMetal command line shown in the following example produces C# code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="90689-121">Se presentan también los procedimientos almacenados y las funciones, y los nombres de tabla se pluralizan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="90689-121">Stored procedures and functions are also rendered, and table names are automatically pluralized.</span></span>  
  
```console  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a><span data-ttu-id="90689-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="90689-122">See also</span></span>

- [<span data-ttu-id="90689-123">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="90689-123">Programming Guide</span></span>](programming-guide.md)
- [<span data-ttu-id="90689-124">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="90689-124">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="90689-125">Aprender con tutoriales</span><span class="sxs-lookup"><span data-stu-id="90689-125">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
- [<span data-ttu-id="90689-126">Procedimiento para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="90689-126">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [<span data-ttu-id="90689-127">Asignación basada en atributos</span><span class="sxs-lookup"><span data-stu-id="90689-127">Attribute-Based Mapping</span></span>](attribute-based-mapping.md)
- [<span data-ttu-id="90689-128">SqlMetal.exe (Herramienta de generación de código)</span><span class="sxs-lookup"><span data-stu-id="90689-128">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="90689-129">Asignación externa</span><span class="sxs-lookup"><span data-stu-id="90689-129">External Mapping</span></span>](external-mapping.md)
- [<span data-ttu-id="90689-130">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="90689-130">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="90689-131">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="90689-131">Creating the Object Model</span></span>](creating-the-object-model.md)

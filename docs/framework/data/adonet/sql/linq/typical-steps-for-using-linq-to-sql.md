---
title: Pasos habituales para usar LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 9a88bd51-bd74-48f7-a9b1-f650e8d55a3e
ms.openlocfilehash: dc8c4be1e895ee5c4c7947e6311e5bf71008490f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164265"
---
# <a name="typical-steps-for-using-linq-to-sql"></a><span data-ttu-id="2c742-102">Pasos habituales para usar LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2c742-102">Typical Steps for Using LINQ to SQL</span></span>

<span data-ttu-id="2c742-103">Para implementar una aplicación [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], debe seguir los pasos que se describen más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="2c742-103">To implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application, you follow the steps described later in this topic.</span></span> <span data-ttu-id="2c742-104">Observe que muchos pasos son opcionales.</span><span class="sxs-lookup"><span data-stu-id="2c742-104">Note that many steps are optional.</span></span> <span data-ttu-id="2c742-105">Es muy posible que pueda utilizar su modelo de objetos en su estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2c742-105">It is very possible that you can use your object model in its default state.</span></span>  
  
 <span data-ttu-id="2c742-106">Para un inicio muy rápido, use el Object Relational Designer para crear el modelo de objetos y comenzar a codificar las consultas.</span><span class="sxs-lookup"><span data-stu-id="2c742-106">For a really fast start, use the Object Relational Designer to create your object model and start coding your queries.</span></span>  
  
## <a name="creating-the-object-model"></a><span data-ttu-id="2c742-107">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="2c742-107">Creating the Object Model</span></span>  

 <span data-ttu-id="2c742-108">El primer paso es crear un modelo de objetos a partir de los metadatos de una base de datos relacional existente.</span><span class="sxs-lookup"><span data-stu-id="2c742-108">The first step is to create an object model from the metadata of an existing relational database.</span></span> <span data-ttu-id="2c742-109">El modelo de objetos representa la base de datos según el lenguaje de programación del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="2c742-109">The object model represents the database according to the programming language of the developer.</span></span> <span data-ttu-id="2c742-110">Para obtener más información, vea [el LINQ to SQL modelo de objetos](the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="2c742-110">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
### <a name="1-select-a-tool-to-create-the-model"></a><span data-ttu-id="2c742-111">1. Seleccione una herramienta para crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="2c742-111">1. Select a tool to create the model.</span></span>  

 <span data-ttu-id="2c742-112">Tres herramientas están disponibles para crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="2c742-112">Three tools are available for creating the model.</span></span>  
  
- <span data-ttu-id="2c742-113">El Object Relational Designer</span><span class="sxs-lookup"><span data-stu-id="2c742-113">The Object Relational Designer</span></span>  
  
     <span data-ttu-id="2c742-114">Este diseñador proporciona una interfaz de usuario completa para crear un modelo de objetos a partir de una base de datos existente.</span><span class="sxs-lookup"><span data-stu-id="2c742-114">This designer provides a rich user interface for creating an object model from an existing database.</span></span> <span data-ttu-id="2c742-115">Esta herramienta forma parte del IDE de Visual Studio y se adapta mejor a las bases de datos pequeñas o medianas.</span><span class="sxs-lookup"><span data-stu-id="2c742-115">This tool is part of the Visual Studio IDE, and is best suited to small or medium databases.</span></span>  
  
- <span data-ttu-id="2c742-116">Herramienta de generación de código SQLMetal</span><span class="sxs-lookup"><span data-stu-id="2c742-116">The SQLMetal code-generation tool</span></span>  
  
     <span data-ttu-id="2c742-117">Esta utilidad de línea de comandos proporciona un conjunto de opciones ligeramente diferente de Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="2c742-117">This command-line utility provides a slightly different set of options from the O/R Designer.</span></span> <span data-ttu-id="2c742-118">Las bases de datos grandes se modelan mejor con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="2c742-118">Modeling large databases is best done by using this tool.</span></span> <span data-ttu-id="2c742-119">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2c742-119">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
- <span data-ttu-id="2c742-120">Editor de código</span><span class="sxs-lookup"><span data-stu-id="2c742-120">A code editor</span></span>  
  
     <span data-ttu-id="2c742-121">Puede escribir su propio código mediante el editor de código de Visual Studio o cualquier otro editor.</span><span class="sxs-lookup"><span data-stu-id="2c742-121">You can write your own code by using either the Visual Studio code editor or another editor.</span></span> <span data-ttu-id="2c742-122">No se recomienda este enfoque, que puede ser propenso a errores, si tiene una base de datos existente y puede usar Object Relational Designer o la herramienta SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="2c742-122">We do not recommend this approach, which can be prone to errors, when you have an existing database and can use either the O/R Designer or the SQLMetal tool.</span></span> <span data-ttu-id="2c742-123">Sin embargo, el editor de código puede ser muy útil para perfeccionar o modificar el código ya generado con otras herramientas.</span><span class="sxs-lookup"><span data-stu-id="2c742-123">However, the code editor can be valuable for refining or modifying code you have already generated by using other tools.</span></span> <span data-ttu-id="2c742-124">Para obtener más información, vea [Cómo: personalizar clases de entidad mediante el editor de código](how-to-customize-entity-classes-by-using-the-code-editor.md).</span><span class="sxs-lookup"><span data-stu-id="2c742-124">For more information, see [How to: Customize Entity Classes by Using the Code Editor](how-to-customize-entity-classes-by-using-the-code-editor.md).</span></span>  
  
### <a name="2-select-the-kind-of-code-you-want-to-generate"></a><span data-ttu-id="2c742-125">2. Seleccione el tipo de código que desea generar.</span><span class="sxs-lookup"><span data-stu-id="2c742-125">2. Select the kind of code you want to generate.</span></span>  
  
- <span data-ttu-id="2c742-126">Un archivo de código fuente de C# o Visual Basic para la asignación basada en atributos.</span><span class="sxs-lookup"><span data-stu-id="2c742-126">A C# or Visual Basic source code file for attribute-based mapping.</span></span>  
  
     <span data-ttu-id="2c742-127">Después, incluya este archivo de código en el proyecto de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2c742-127">You then include this code file in your Visual Studio project.</span></span> <span data-ttu-id="2c742-128">Para obtener más información, consulte [asignación basada en atributos](attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="2c742-128">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="2c742-129">Un archivo XML para la asignación externa.</span><span class="sxs-lookup"><span data-stu-id="2c742-129">An XML file for external mapping.</span></span>  
  
     <span data-ttu-id="2c742-130">Con este enfoque puede mantener los metadatos de la asignación fuera del código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c742-130">By using this approach, you can keep the mapping metadata out of your application code.</span></span> <span data-ttu-id="2c742-131">Para obtener más información, consulte [asignación externa](external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="2c742-131">For more information, see [External Mapping](external-mapping.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2c742-132">Object Relational Designer no admite la generación de archivos de asignación externos.</span><span class="sxs-lookup"><span data-stu-id="2c742-132">The O/R Designer does not support the generation of external mapping files.</span></span> <span data-ttu-id="2c742-133">Debe utilizar la herramienta SQLMetal para implementar esta característica.</span><span class="sxs-lookup"><span data-stu-id="2c742-133">You must use the SQLMetal tool to implement this feature.</span></span>  
  
- <span data-ttu-id="2c742-134">Un archivo DBML, que se puede modificar antes de generar el archivo de código definitivo.</span><span class="sxs-lookup"><span data-stu-id="2c742-134">A DBML file, which you can modify before generating a final code file.</span></span>  
  
     <span data-ttu-id="2c742-135">Ésta es una característica avanzada.</span><span class="sxs-lookup"><span data-stu-id="2c742-135">This is an advanced feature.</span></span>  
  
### <a name="3-refine-the-code-file-to-reflect-the-needs-of-your-application"></a><span data-ttu-id="2c742-136">3. Refine el archivo de código para reflejar las necesidades de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c742-136">3. Refine the code file to reflect the needs of your application.</span></span>  

 <span data-ttu-id="2c742-137">Para este propósito, puede utilizar el Object Relational Designer o el editor de código.</span><span class="sxs-lookup"><span data-stu-id="2c742-137">For this purpose, you can use either the O/R Designer or the code editor.</span></span>  
  
## <a name="using-the-object-model"></a><span data-ttu-id="2c742-138">Usar el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="2c742-138">Using the Object Model</span></span>  

 <span data-ttu-id="2c742-139">La ilustración siguiente muestra la relación entre el programador y los datos en un escenario de dos niveles.</span><span class="sxs-lookup"><span data-stu-id="2c742-139">The following illustration shows the relationship between the developer and the data in a two-tier scenario.</span></span> <span data-ttu-id="2c742-140">Para otros escenarios, consulte [aplicaciones de N niveles y remotas con LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="2c742-140">For other scenarios, see [N-Tier and Remote Applications with LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md).</span></span>  
  
 ![Captura de pantalla que muestra el modelo de objetos de Linq.](./media/the-linq-to-sql-object-model/linq-object-model-two-tier.png)  
  
 <span data-ttu-id="2c742-142">Ahora que tiene un modelo de objetos, debe describir las solicitudes de información y manipular los datos dentro de ese modelo.</span><span class="sxs-lookup"><span data-stu-id="2c742-142">Now that you have the object model, you describe information requests and manipulate data within that model.</span></span> <span data-ttu-id="2c742-143">Debe pensar en términos de los objetos y las propiedades del modelo de objetos, y no en términos de las filas y columnas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2c742-143">You think in terms of the objects and properties in your object model and not in terms of the rows and columns of the database.</span></span> <span data-ttu-id="2c742-144">No tratará directamente con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2c742-144">You do not deal directly with the database.</span></span>  
  
 <span data-ttu-id="2c742-145">Al indicar [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] a que ejecute una consulta que ha descrito o que llame a `SubmitChanges()` en los datos que ha manipulado, se [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] comunica con la base de datos en el idioma de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2c742-145">When you instruct [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to either execute a query that you have described or call `SubmitChanges()` on data that you have manipulated, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] communicates with the database in the language of the database.</span></span>  
  
 <span data-ttu-id="2c742-146">A continuación, se presentan los pasos típicos para utilizar el modelo de objetos creado.</span><span class="sxs-lookup"><span data-stu-id="2c742-146">The following represents typical steps for using the object model that you have created.</span></span>  
  
### <a name="1-create-queries-to-retrieve-information-from-the-database"></a><span data-ttu-id="2c742-147">1. cree consultas para recuperar información de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2c742-147">1. Create queries to retrieve information from the database.</span></span>  

 <span data-ttu-id="2c742-148">Para obtener más información, vea [conceptos de consultas](query-concepts.md) y ejemplos de [consultas](query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="2c742-148">For more information, see [Query Concepts](query-concepts.md) and [Query Examples](query-examples.md).</span></span>  
  
### <a name="2-override-default-behaviors-for-insert-update-and-delete"></a><span data-ttu-id="2c742-149">2. invalidar los comportamientos predeterminados para INSERT, Update y DELETE.</span><span class="sxs-lookup"><span data-stu-id="2c742-149">2. Override default behaviors for Insert, Update, and Delete.</span></span>  

 <span data-ttu-id="2c742-150">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="2c742-150">This step is optional.</span></span> <span data-ttu-id="2c742-151">Para obtener más información, vea [personalizar las operaciones de inserción, actualización y eliminación](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="2c742-151">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>  
  
### <a name="3-set-appropriate-options-to-detect-and-report-concurrency-conflicts"></a><span data-ttu-id="2c742-152">3. establezca las opciones adecuadas para detectar y notificar conflictos de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="2c742-152">3. Set appropriate options to detect and report concurrency conflicts.</span></span>  

 <span data-ttu-id="2c742-153">Puede mantener la configuración de administración de conflictos de simultaneidad predeterminada del modelo o puede cambiarla para ajustarla sus fines concretos.</span><span class="sxs-lookup"><span data-stu-id="2c742-153">You can leave your model with its default values for handling concurrency conflicts, or you can change it to suit your purposes.</span></span> <span data-ttu-id="2c742-154">Para obtener más información, vea [Cómo: especificar en qué miembros se comprueban los conflictos de simultaneidad](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) y [Cómo: especificar Cuándo se inician las excepciones de simultaneidad](how-to-specify-when-concurrency-exceptions-are-thrown.md).</span><span class="sxs-lookup"><span data-stu-id="2c742-154">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) and [How to: Specify When Concurrency Exceptions are Thrown](how-to-specify-when-concurrency-exceptions-are-thrown.md).</span></span>  
  
### <a name="4-establish-an-inheritance-hierarchy"></a><span data-ttu-id="2c742-155">4. establezca una jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="2c742-155">4. Establish an inheritance hierarchy.</span></span>  

 <span data-ttu-id="2c742-156">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="2c742-156">This step is optional.</span></span> <span data-ttu-id="2c742-157">Para obtener más información, consulte [compatibilidad con la herencia](inheritance-support.md).</span><span class="sxs-lookup"><span data-stu-id="2c742-157">For more information, see [Inheritance Support](inheritance-support.md).</span></span>  
  
### <a name="5-provide-an-appropriate-user-interface"></a><span data-ttu-id="2c742-158">5. proporcione una interfaz de usuario adecuada.</span><span class="sxs-lookup"><span data-stu-id="2c742-158">5. Provide an appropriate user interface.</span></span>  

 <span data-ttu-id="2c742-159">Este paso es opcional y depende de cómo se vaya a utilizar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c742-159">This step is optional, and depends on how your application will be used.</span></span>  
  
### <a name="6-debug-and-test-your-application"></a><span data-ttu-id="2c742-160">6. depurar y probar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c742-160">6. Debug and test your application.</span></span>  

 <span data-ttu-id="2c742-161">Para obtener más información, consulte [compatibilidad con la depuración](debugging-support.md).</span><span class="sxs-lookup"><span data-stu-id="2c742-161">For more information, see [Debugging Support](debugging-support.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c742-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c742-162">See also</span></span>

- [<span data-ttu-id="2c742-163">Introducción</span><span class="sxs-lookup"><span data-stu-id="2c742-163">Getting Started</span></span>](getting-started.md)
- [<span data-ttu-id="2c742-164">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="2c742-164">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="2c742-165">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="2c742-165">Stored Procedures</span></span>](stored-procedures.md)

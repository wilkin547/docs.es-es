---
title: 'Tutorial: Realizar consultas en varias relaciones (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: a7da43e3-769f-4e07-bcd6-552b8bde66f4
ms.openlocfilehash: ce5323b4ecd7bd0c4337d4632eff209e4d0ebd42
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163991"
---
# <a name="walkthrough-querying-across-relationships-visual-basic"></a><span data-ttu-id="da107-102">Tutorial: Realizar consultas en varias relaciones (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da107-102">Walkthrough: Querying Across Relationships (Visual Basic)</span></span>

<span data-ttu-id="da107-103">En este tutorial se muestra el uso de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *asociaciones* para representar relaciones de clave externa en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="da107-103">This walkthrough demonstrates the use of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *associations* to represent foreign-key relationships in the database.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="da107-104">Este tutorial se escribió con la configuración de desarrollo de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="da107-104">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="da107-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="da107-105">Prerequisites</span></span>  

 <span data-ttu-id="da107-106">Debe haber completado el [Tutorial: modelo de objetos simple y consulta (Visual Basic)](walkthrough-simple-object-model-and-query-visual-basic.md).</span><span class="sxs-lookup"><span data-stu-id="da107-106">You must have completed [Walkthrough: Simple Object Model and Query (Visual Basic)](walkthrough-simple-object-model-and-query-visual-basic.md).</span></span> <span data-ttu-id="da107-107">Este tutorial se basa en el tutorial mencionado, incluida la presencia del archivo northwnd.mdf en c:\linqtest.</span><span class="sxs-lookup"><span data-stu-id="da107-107">This walkthrough builds on that one, including the presence of the northwnd.mdf file in c:\linqtest.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="da107-108">Información general</span><span class="sxs-lookup"><span data-stu-id="da107-108">Overview</span></span>  

 <span data-ttu-id="da107-109">Este tutorial conlleva tres tareas principales:</span><span class="sxs-lookup"><span data-stu-id="da107-109">This walkthrough consists of three main tasks:</span></span>  
  
- <span data-ttu-id="da107-110">Agregar una clase de entidad para representar la tabla Orders en la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="da107-110">Adding an entity class to represent the Orders table in the sample Northwind database.</span></span>  
  
- <span data-ttu-id="da107-111">Complementar las anotaciones de la clase `Customer` para mejorar la relación entre las clases `Customer` y `Order`.</span><span class="sxs-lookup"><span data-stu-id="da107-111">Supplementing annotations to the `Customer` class to enhance the relationship between the `Customer` and `Order` classes.</span></span>  
  
- <span data-ttu-id="da107-112">Crear y ejecutar una consulta para probar el proceso de obtener información de `Order` mediante la clase `Customer`.</span><span class="sxs-lookup"><span data-stu-id="da107-112">Creating and running a query to test the process of obtaining `Order` information by using the `Customer` class.</span></span>  
  
## <a name="mapping-relationships-across-tables"></a><span data-ttu-id="da107-113">Asignar relaciones entre tablas</span><span class="sxs-lookup"><span data-stu-id="da107-113">Mapping Relationships across Tables</span></span>  

 <span data-ttu-id="da107-114">Después de la definición de la clase `Customer`, cree la definición de la clase de entidad `Order`, que incluye el código siguiente, que indica que `Orders.Customer` se relaciona como clave externa con `Customers.CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="da107-114">After the `Customer` class definition, create the `Order` entity class definition that includes the following code, which indicates that `Orders.Customer` relates as a foreign key to `Customers.CustomerID`.</span></span>  
  
#### <a name="to-add-the-order-entity-class"></a><span data-ttu-id="da107-115">Para agregar la clase de entidad Order</span><span class="sxs-lookup"><span data-stu-id="da107-115">To add the Order entity class</span></span>  
  
- <span data-ttu-id="da107-116">Escriba o pegue el código siguiente después de la clase `Customer`:</span><span class="sxs-lookup"><span data-stu-id="da107-116">Type or paste the following code after the `Customer` class:</span></span>  
  
     [!code-vb[DLinqWalk2VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#1)]  
  
## <a name="annotating-the-customer-class"></a><span data-ttu-id="da107-117">Anotar la clase Customer</span><span class="sxs-lookup"><span data-stu-id="da107-117">Annotating the Customer Class</span></span>  

 <span data-ttu-id="da107-118">En este paso, anotará la clase `Customer` para indicar su relación con la clase `Order`.</span><span class="sxs-lookup"><span data-stu-id="da107-118">In this step, you annotate the `Customer` class to indicate its relationship to the `Order` class.</span></span> <span data-ttu-id="da107-119">(Esta adición no es estrictamente necesaria, porque para crear el vínculo basta con definir la relación en cualquier dirección.</span><span class="sxs-lookup"><span data-stu-id="da107-119">(This addition is not strictly necessary, because defining the relationship in either direction is sufficient to create the link.</span></span> <span data-ttu-id="da107-120">Sin embargo, al agregar esta anotación, se puede navegar con facilidad por los objetos en cualquier dirección.)</span><span class="sxs-lookup"><span data-stu-id="da107-120">But adding this annotation does enable you to easily navigate objects in either direction.)</span></span>  
  
#### <a name="to-annotate-the-customer-class"></a><span data-ttu-id="da107-121">Para anotar la clase Customer</span><span class="sxs-lookup"><span data-stu-id="da107-121">To annotate the Customer class</span></span>  
  
- <span data-ttu-id="da107-122">Escriba o pegue el código siguiente en la clase `Customer`:</span><span class="sxs-lookup"><span data-stu-id="da107-122">Type or paste the following code into the `Customer` class:</span></span>  
  
     [!code-vb[DLinqWalk2VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#2)]  
  
## <a name="creating-and-running-a-query-across-the-customer-order-relationship"></a><span data-ttu-id="da107-123">Crear y ejecutar una consulta en la relación Customer-Order</span><span class="sxs-lookup"><span data-stu-id="da107-123">Creating and Running a Query across the Customer-Order Relationship</span></span>  

 <span data-ttu-id="da107-124">Ahora puede tener acceso a los objetos `Order` directamente desde los objetos `Customer`, o a la inversa.</span><span class="sxs-lookup"><span data-stu-id="da107-124">You can now access `Order` objects directly from the `Customer` objects, or in the opposite order.</span></span> <span data-ttu-id="da107-125">No necesita una *combinación* explícita entre clientes y pedidos.</span><span class="sxs-lookup"><span data-stu-id="da107-125">You do not need an explicit *join* between customers and orders.</span></span>  
  
#### <a name="to-access-order-objects-by-using-customer-objects"></a><span data-ttu-id="da107-126">Para tener acceso a los objetos Order a través de los objetos Customer</span><span class="sxs-lookup"><span data-stu-id="da107-126">To access Order objects by using Customer objects</span></span>  
  
1. <span data-ttu-id="da107-127">Modifique el método `Sub Main`; para ello, escriba o pegue el código siguiente en el método:</span><span class="sxs-lookup"><span data-stu-id="da107-127">Modify the `Sub Main` method by typing or pasting the following code into the method:</span></span>  
  
     [!code-vb[DLinqWalk2VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#3)]  
  
2. <span data-ttu-id="da107-128">Presione F5 para depurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="da107-128">Press F5 to debug your application.</span></span>  
  
     <span data-ttu-id="da107-129">En el cuadro de mensaje aparecen dos nombres y la ventana Consola muestra el código SQL generado.</span><span class="sxs-lookup"><span data-stu-id="da107-129">Two names appear in the message box, and the Console window shows the generated SQL code.</span></span>  
  
3. <span data-ttu-id="da107-130">Cierre el cuadro de mensaje para detener la depuración.</span><span class="sxs-lookup"><span data-stu-id="da107-130">Close the message box to stop debugging.</span></span>  
  
## <a name="creating-a-strongly-typed-view-of-your-database"></a><span data-ttu-id="da107-131">Crear una vista de la base de datos fuertemente tipados</span><span class="sxs-lookup"><span data-stu-id="da107-131">Creating a Strongly Typed View of Your Database</span></span>  

 <span data-ttu-id="da107-132">Es mucho más fácil empezar por una vista fuertemente tipada de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="da107-132">It is much easier to start with a strongly typed view of your database.</span></span> <span data-ttu-id="da107-133">Si el objeto <xref:System.Data.Linq.DataContext> está fuertemente tipado, no es necesario realizar llamadas a <xref:System.Data.Linq.DataContext.GetTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="da107-133">By strongly typing the <xref:System.Data.Linq.DataContext> object, you do not need calls to <xref:System.Data.Linq.DataContext.GetTable%2A>.</span></span> <span data-ttu-id="da107-134">Puede utilizar tablas fuertemente tipadas en todas sus consultas al utilizar el objeto <xref:System.Data.Linq.DataContext> fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="da107-134">You can use strongly typed tables in all your queries when you use the strongly typed <xref:System.Data.Linq.DataContext> object.</span></span>  
  
 <span data-ttu-id="da107-135">En los pasos siguientes, creará `Customers` como una tabla fuertemente tipada que está asignada a la tabla Customers de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="da107-135">In the following steps, you will create `Customers` as a strongly typed table that maps to the Customers table in the database.</span></span>  
  
#### <a name="to-strongly-type-the-datacontext-object"></a><span data-ttu-id="da107-136">Para que el objeto DataContext esté fuertemente tipado</span><span class="sxs-lookup"><span data-stu-id="da107-136">To strongly type the DataContext object</span></span>  
  
1. <span data-ttu-id="da107-137">Agregue el siguiente código encima de la declaración de la clase `Customer`.</span><span class="sxs-lookup"><span data-stu-id="da107-137">Add the following code above the `Customer` class declaration.</span></span>  
  
     [!code-vb[DLinqWalk2VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#4)]  
  
2. <span data-ttu-id="da107-138">Modifique `Sub Main` para que utilice el objeto <xref:System.Data.Linq.DataContext> fuertemente tipado de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="da107-138">Modify `Sub Main` to use the strongly typed <xref:System.Data.Linq.DataContext> as follows:</span></span>  
  
     [!code-vb[DLinqWalk2VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#5)]  
  
3. <span data-ttu-id="da107-139">Presione F5 para depurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="da107-139">Press F5 to debug your application.</span></span>  
  
     <span data-ttu-id="da107-140">El resultado en la ventana Consola es:</span><span class="sxs-lookup"><span data-stu-id="da107-140">The Console window output is:</span></span>  
  
     `ID=WHITC`  
  
4. <span data-ttu-id="da107-141">Presione Entrar en la ventana Consola para cerrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="da107-141">Press Enter in the Console window to close the application.</span></span>  
  
5. <span data-ttu-id="da107-142">En el menú **archivo** , haga clic en **guardar todo** si desea guardar esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="da107-142">On the **File** menu, click **Save All** if you want to save this application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="da107-143">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="da107-143">Next Steps</span></span>  

 <span data-ttu-id="da107-144">En el siguiente tutorial ([Tutorial: manipular datos (Visual Basic)](walkthrough-manipulating-data-visual-basic.md)) se muestra cómo manipular los datos.</span><span class="sxs-lookup"><span data-stu-id="da107-144">The next walkthrough ([Walkthrough: Manipulating Data (Visual Basic)](walkthrough-manipulating-data-visual-basic.md)) demonstrates how to manipulate data.</span></span> <span data-ttu-id="da107-145">Este tutorial no requiere que guarde los dos tutoriales ya completados de esta serie.</span><span class="sxs-lookup"><span data-stu-id="da107-145">That walkthrough does not require that you save the two walkthroughs in this series that you have already completed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da107-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="da107-146">See also</span></span>

- [<span data-ttu-id="da107-147">Aprender con tutoriales</span><span class="sxs-lookup"><span data-stu-id="da107-147">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)

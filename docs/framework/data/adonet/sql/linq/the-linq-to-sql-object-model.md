---
description: 'Más información sobre: el modelo de objetos de LINQ to SQL'
title: El modelo de objetos de LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 81dd0c37-e2a4-4694-83b0-f2e49e693810
ms.openlocfilehash: be4021019d09d1479364b25268eefda50b6eaa6f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681271"
---
# <a name="the-linq-to-sql-object-model"></a><span data-ttu-id="0fc2d-103">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0fc2d-103">The LINQ to SQL Object Model</span></span>

<span data-ttu-id="0fc2d-104">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , un modelo de objetos expresado en el lenguaje de programación del programador se asigna al modelo de datos de una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-104">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], an object model expressed in the programming language of the developer is mapped to the data model of a relational database.</span></span> <span data-ttu-id="0fc2d-105">Así, las operaciones con los datos se realizan según el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-105">Operations on the data are then conducted according to the object model.</span></span>  
  
 <span data-ttu-id="0fc2d-106">En este escenario, no ejecuta comandos de base de datos (como `INSERT`) en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-106">In this scenario, you do not issue database commands (for example, `INSERT`) to the database.</span></span> <span data-ttu-id="0fc2d-107">En su lugar, cambia los valores y ejecuta los métodos de su modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-107">Instead, you change values and execute methods within your object model.</span></span> <span data-ttu-id="0fc2d-108">Si desea consultar la base de datos o enviar cambios, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte sus solicitudes en los comandos SQL correctos y los envía a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-108">When you want to query the database or send it changes, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates your requests into the correct SQL commands and sends those commands to the database.</span></span>  
  
 ![Captura de pantalla que muestra el modelo de objetos de Linq.](./media/the-linq-to-sql-object-model/linq-object-model-two-tier.png)  
  
 <span data-ttu-id="0fc2d-110">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]En la tabla siguiente se resumen los elementos más fundamentales del modelo de objetos y su relación con los elementos del modelo de datos relacional:</span><span class="sxs-lookup"><span data-stu-id="0fc2d-110">The most fundamental elements in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model and their relationship to elements in the relational data model are summarized in the following table:</span></span>  
  
|<span data-ttu-id="0fc2d-111">Modelo de objetos LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0fc2d-111">LINQ to SQL Object Model</span></span>|<span data-ttu-id="0fc2d-112">Modelo de datos relacionales</span><span class="sxs-lookup"><span data-stu-id="0fc2d-112">Relational Data Model</span></span>|  
|------------------------------|---------------------------|  
|<span data-ttu-id="0fc2d-113">Clase de entidad</span><span class="sxs-lookup"><span data-stu-id="0fc2d-113">Entity class</span></span>|<span data-ttu-id="0fc2d-114">Tabla</span><span class="sxs-lookup"><span data-stu-id="0fc2d-114">Table</span></span>|  
|<span data-ttu-id="0fc2d-115">Miembro de clase</span><span class="sxs-lookup"><span data-stu-id="0fc2d-115">Class member</span></span>|<span data-ttu-id="0fc2d-116">Columna</span><span class="sxs-lookup"><span data-stu-id="0fc2d-116">Column</span></span>|  
|<span data-ttu-id="0fc2d-117">Asociación</span><span class="sxs-lookup"><span data-stu-id="0fc2d-117">Association</span></span>|<span data-ttu-id="0fc2d-118">Relación de clave externa</span><span class="sxs-lookup"><span data-stu-id="0fc2d-118">Foreign-key relationship</span></span>|  
|<span data-ttu-id="0fc2d-119">Método</span><span class="sxs-lookup"><span data-stu-id="0fc2d-119">Method</span></span>|<span data-ttu-id="0fc2d-120">Procedimiento almacenado o función</span><span class="sxs-lookup"><span data-stu-id="0fc2d-120">Stored Procedure or Function</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="0fc2d-121">En las líneas siguientes se asume que tiene conocimientos básicos del modelo de datos relacionales y sus reglas.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-121">The following descriptions assume that you have a basic knowledge of the relational data model and rules.</span></span>  
  
## <a name="linq-to-sql-entity-classes-and-database-tables"></a><span data-ttu-id="0fc2d-122">Tablas de base de datos y clases de entidad en LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0fc2d-122">LINQ to SQL Entity Classes and Database Tables</span></span>  

 <span data-ttu-id="0fc2d-123">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , una tabla de base de datos se representa mediante una *clase de entidad*.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-123">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], a database table is represented by an *entity class*.</span></span> <span data-ttu-id="0fc2d-124">Una clase de entidad es como cualquier otra clase que se pueda crear, con la salvedad de que se anota utilizando información especial que asocia la clase a una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-124">An entity class is like any other class you might create except that you annotate the class by using special information that associates the class with a database table.</span></span> <span data-ttu-id="0fc2d-125">Para realizar esta anotación, se agrega un atributo personalizado (<xref:System.Data.Linq.Mapping.TableAttribute>) a la declaración de clase, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0fc2d-125">You make this annotation by adding a custom attribute (<xref:System.Data.Linq.Mapping.TableAttribute>) to your class declaration, as in the following example:</span></span>  
  
### <a name="example"></a><span data-ttu-id="0fc2d-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0fc2d-126">Example</span></span>  

 [!code-csharp[DLinqObjectModel#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#1)]
 [!code-vb[DLinqObjectModel#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#1)]  
  
 <span data-ttu-id="0fc2d-127">Solo las instancias de clases declaradas como tablas (es decir, clases de entidad) pueden guardarse en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-127">Only instances of classes declared as tables (that is, entity classes) can be saved to the database.</span></span>  
  
 <span data-ttu-id="0fc2d-128">Para obtener más información, vea la sección atributo de tabla de [asignación basada en atributos](attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="0fc2d-128">For more information, see the Table Attribute section of [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
## <a name="linq-to-sql-class-members-and-database-columns"></a><span data-ttu-id="0fc2d-129">Miembros de clase y columnas de base de datos en LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0fc2d-129">LINQ to SQL Class Members and Database Columns</span></span>  

 <span data-ttu-id="0fc2d-130">Además de asociar clases a tablas, se designan campos o propiedades para representar columnas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-130">In addition to associating classes with tables, you designate fields or properties to represent database columns.</span></span> <span data-ttu-id="0fc2d-131">Para este propósito, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] define el atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0fc2d-131">For this purpose, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] defines the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute, as in the following example:</span></span>  
  
### <a name="example"></a><span data-ttu-id="0fc2d-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0fc2d-132">Example</span></span>  

 [!code-csharp[DLinqObjectModel#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#2)]
 [!code-vb[DLinqObjectModel#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#2)]  
  
 <span data-ttu-id="0fc2d-133">Solo los campos y las propiedades que estén asignados a columnas se conservan en la base de datos o se recuperan de ella.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-133">Only fields and properties mapped to columns are persisted to or retrieved from the database.</span></span> <span data-ttu-id="0fc2d-134">Si no se han declarado como columnas, se consideran partes transitorias de la lógica de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-134">Those not declared as columns are considered as transient parts of your application logic.</span></span>  
  
 <span data-ttu-id="0fc2d-135">El atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> tiene varias propiedades que se pueden utilizar para personalizar los miembros que representan columnas (por ejemplo, para designar un miembro como representativo de una columna de clave principal).</span><span class="sxs-lookup"><span data-stu-id="0fc2d-135">The <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute has a variety of properties that you can use to customize these members that represent columns (for example, designating a member as representing a primary key column).</span></span> <span data-ttu-id="0fc2d-136">Para obtener más información, vea la sección atributo de columna de [asignación basada en atributos](attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="0fc2d-136">For more information, see the Column Attribute section of [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
## <a name="linq-to-sql-associations-and-database-foreign-key-relationships"></a><span data-ttu-id="0fc2d-137">Asociaciones y relaciones de clave externa de base de datos en LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0fc2d-137">LINQ to SQL Associations and Database Foreign-key Relationships</span></span>  

 <span data-ttu-id="0fc2d-138">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , las asociaciones de base de datos (como las relaciones de clave externa y clave principal) se representan mediante la aplicación del <xref:System.Data.Linq.Mapping.AssociationAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-138">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you represent database associations (such as foreign-key to primary-key relationships) by applying the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span> <span data-ttu-id="0fc2d-139">En el segmento de código siguiente, la `Order` clase contiene una `Customer` propiedad que tiene un <xref:System.Data.Linq.Mapping.AssociationAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-139">In the following segment of code, the `Order` class contains a `Customer` property that has an <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span> <span data-ttu-id="0fc2d-140">Esta propiedad y su atributo proporcionan a la clase `Order` una relación con la clase `Customer`.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-140">This property and its attribute provide the `Order` class with a relationship to the `Customer` class.</span></span>  
  
 <span data-ttu-id="0fc2d-141">En el ejemplo de código siguiente se muestra la propiedad `Customer` de la clase `Order`.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-141">The following code example shows the `Customer` property from the `Order` class.</span></span>  
  
### <a name="example"></a><span data-ttu-id="0fc2d-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0fc2d-142">Example</span></span>  

 [!code-csharp[DLinqObjectModel#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#3)]
 [!code-vb[DLinqObjectModel#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#3)]  
  
 <span data-ttu-id="0fc2d-143">Para obtener más información, vea la sección relativa al atributo de Asociación de [asignación basada en atributos](attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="0fc2d-143">For more information, see the Association Attribute section of [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
## <a name="linq-to-sql-methods-and-database-stored-procedures"></a><span data-ttu-id="0fc2d-144">Métodos y procedimientos almacenados de base de datos en LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0fc2d-144">LINQ to SQL Methods and Database Stored Procedures</span></span>  

 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0fc2d-145">admite los procedimientos almacenados y las funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-145">supports stored procedures and user-defined functions.</span></span> <span data-ttu-id="0fc2d-146">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , se asignan estas abstracciones definidas por la base de datos a objetos de cliente para que se pueda tener acceso a ellas de forma fuertemente tipada a partir del código de cliente.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-146">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you map these database-defined abstractions to client objects so that you can access them in a strongly typed manner from client code.</span></span> <span data-ttu-id="0fc2d-147">Las firmas de método guardan la máxima similitud con las firmas de los procedimientos y funciones que se definen en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-147">The method signatures resemble as closely as possible the signatures of the procedures and functions defined in the database.</span></span> <span data-ttu-id="0fc2d-148">Puede utilizar IntelliSense para detectar estos métodos.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-148">You can use IntelliSense to discover these methods.</span></span>  
  
 <span data-ttu-id="0fc2d-149">Un conjunto de resultados devuelto por una llamada a un procedimiento asignado es una colección fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-149">A result set that is returned by a call to a mapped procedure is a strongly typed collection.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0fc2d-150">asigna los procedimientos almacenados y las funciones a los métodos utilizando los atributos <xref:System.Data.Linq.Mapping.FunctionAttribute> y <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-150">maps stored procedures and functions to methods by using the <xref:System.Data.Linq.Mapping.FunctionAttribute> and <xref:System.Data.Linq.Mapping.ParameterAttribute> attributes.</span></span> <span data-ttu-id="0fc2d-151">Los métodos que representan procedimientos almacenados se distinguen de los que representan funciones definidas por el usuario mediante la propiedad <xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A>.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-151">Methods representing stored procedures are distinguished from those representing user-defined functions by the <xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A> property.</span></span> <span data-ttu-id="0fc2d-152">Si esta propiedad se establece en `false` (valor predeterminado), el método representa un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-152">If this property is set to `false` (the default), the method represents a stored procedure.</span></span> <span data-ttu-id="0fc2d-153">Si se establece en `true`, el método representa una función de base de datos.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-153">If it is set to `true`, the method represents a database function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fc2d-154">Si usa Visual Studio, puede usar la Object Relational Designer para crear métodos asignados a procedimientos almacenados y funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="0fc2d-154">If you are using Visual Studio, you can use the Object Relational Designer to create methods mapped to stored procedures and user-defined functions.</span></span>  
  
### <a name="example"></a><span data-ttu-id="0fc2d-155">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0fc2d-155">Example</span></span>  

 [!code-csharp[DLinqObjectModel#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#4)]
 [!code-vb[DLinqObjectModel#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#4)]  
  
 <span data-ttu-id="0fc2d-156">Para obtener más información, vea las secciones atributo de función, atributo de procedimiento almacenado y atributo de parámetro de [asignación basada en atributos](attribute-based-mapping.md) y [procedimientos almacenados](stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="0fc2d-156">For more information, see the Function Attribute, Stored Procedure Attribute, and Parameter Attribute sections of [Attribute-Based Mapping](attribute-based-mapping.md) and [Stored Procedures](stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fc2d-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fc2d-157">See also</span></span>

- [<span data-ttu-id="0fc2d-158">Asignación basada en atributos</span><span class="sxs-lookup"><span data-stu-id="0fc2d-158">Attribute-Based Mapping</span></span>](attribute-based-mapping.md)
- [<span data-ttu-id="0fc2d-159">Información general</span><span class="sxs-lookup"><span data-stu-id="0fc2d-159">Background Information</span></span>](background-information.md)

---
title: "Cómo: Crear dinámicamente una base de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: fb7f23c4-4572-4c38-9898-a287807d070c
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f92d34276855a7b7473dd15dd3828c4ea91c64d1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-dynamically-create-a-database"></a><span data-ttu-id="409af-102">Cómo: Crear dinámicamente una base de datos</span><span class="sxs-lookup"><span data-stu-id="409af-102">How to: Dynamically Create a Database</span></span>
<span data-ttu-id="409af-103">En LINQ to SQL, se asigna un modelo de objetos a una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="409af-103">In LINQ to SQL, an object model is mapped to a relational database.</span></span> <span data-ttu-id="409af-104">La asignación se habilita mediante una asignación basada en atributos o mediante un archivo de asignación externo para describir la estructura de la base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="409af-104">Mapping is enabled by using attribute-based mapping or an external mapping file to describe the structure of the relational database.</span></span> <span data-ttu-id="409af-105">En ambos escenarios, hay información suficiente sobre la base de datos relacional para crear una instancia nueva de la base de datos mediante el método <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="409af-105">In both scenarios, there is enough information about the relational database that you can create a new instance of the database using the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="409af-106">El método <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> crea una réplica de la base de datos solo en lo que respecta a la información codificada en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="409af-106">The <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method creates a replica of the database only to the extent of the information encoded in the object model.</span></span> <span data-ttu-id="409af-107">Es posible que los atributos y los archivos de asignación del modelo de objetos no codifiquen todos los elementos de la estructura de una base de datos existente.</span><span class="sxs-lookup"><span data-stu-id="409af-107">Mapping files and attributes from your object model might not encode everything about the structure of an existing database.</span></span> <span data-ttu-id="409af-108">La información de asignación no representa el contenido de las funciones definidas por el usuario, los procedimientos almacenados, los desencadenadores y las restricciones CHECK.</span><span class="sxs-lookup"><span data-stu-id="409af-108">Mapping information does not represent the contents of user-defined functions, stored procedures, triggers, or check constraints.</span></span> <span data-ttu-id="409af-109">Este comportamiento es suficiente para varias bases de datos.</span><span class="sxs-lookup"><span data-stu-id="409af-109">This behavior is sufficient for a variety of databases.</span></span>  
  
 <span data-ttu-id="409af-110">Podría utilizar el método <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> en cualquier escenario, especialmente si está disponible un proveedor de datos conocido, como Microsoft SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="409af-110">You can use the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method in any number of scenarios, especially if a known data provider like Microsoft SQL Server 2008 is available.</span></span> <span data-ttu-id="409af-111">Entre los escenarios típicos, se pueden citar los siguientes:</span><span class="sxs-lookup"><span data-stu-id="409af-111">Typical scenarios include the following:</span></span>  
  
-   <span data-ttu-id="409af-112">Se crea una aplicación que se instala automáticamente en un sistema del cliente.</span><span class="sxs-lookup"><span data-stu-id="409af-112">You are building an application that automatically installs itself on a customer system.</span></span>  
  
-   <span data-ttu-id="409af-113">Se crea una aplicación cliente que necesita que una base de datos local guarde su estado sin conexión.</span><span class="sxs-lookup"><span data-stu-id="409af-113">You are building a client application that needs a local database to save its offline state.</span></span>  
  
 <span data-ttu-id="409af-114">También puede utilizar el método <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> con SQL Server mediante un archivo .mdf o un nombre del catálogo, dependiendo de su cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="409af-114">You can also use the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method with SQL Server by using an .mdf file or a catalog name, depending on your connection string.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="409af-115"> utiliza la cadena de conexión para definir la base de datos que se va a crear y en qué servidor se va a crear.</span><span class="sxs-lookup"><span data-stu-id="409af-115"> uses the connection string to define the database to be created and on which server the database is to be created.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="409af-116">Siempre que sea posible, utilice Windows Integrated Security para conectar con la base de datos, de modo que no se requieran contraseñas en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="409af-116">Whenever possible, use Windows Integrated Security to connect to the database so that passwords are not required in the connection string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="409af-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="409af-117">Example</span></span>  
 <span data-ttu-id="409af-118">El código siguiente proporciona un ejemplo de cómo se crearía una nueva base de datos denominada MyDVDs.mdf.</span><span class="sxs-lookup"><span data-stu-id="409af-118">The following code provides an example of how to create a new database named MyDVDs.mdf.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#5)]
 [!code-vb[DLinqSubmittingChanges#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="409af-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="409af-119">Example</span></span>  
 <span data-ttu-id="409af-120">Puede utilizar el modelo de objetos para crear una base de datos de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="409af-120">You can use the object model to create a database by doing the following:</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#6)]
 [!code-vb[DLinqSubmittingChanges#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="409af-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="409af-121">Example</span></span>  
 <span data-ttu-id="409af-122">Cuando cree una aplicación que se instale automáticamente en un sistema de un cliente, compruebe si la base de datos existe y quítela antes de crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="409af-122">When building an application that automatically installs itself on a  customer system, see if the database already exists and drop it before creating a new one.</span></span> <span data-ttu-id="409af-123">La clase <xref:System.Data.Linq.DataContext> proporciona los métodos <xref:System.Data.Linq.DataContext.DatabaseExists%2A> y <xref:System.Data.Linq.DataContext.DeleteDatabase%2A> para ayudarle en este proceso.</span><span class="sxs-lookup"><span data-stu-id="409af-123">The <xref:System.Data.Linq.DataContext> class provides the <xref:System.Data.Linq.DataContext.DatabaseExists%2A> and <xref:System.Data.Linq.DataContext.DeleteDatabase%2A> methods to help you with this process.</span></span>  
  
 <span data-ttu-id="409af-124">En el ejemplo siguiente se muestra una manera de usar estos métodos para implementar este enfoque:</span><span class="sxs-lookup"><span data-stu-id="409af-124">The following example shows one way these methods can be used to implement this approach:</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#7)]
 [!code-vb[DLinqSubmittingChanges#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="409af-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="409af-125">See Also</span></span>  
 [<span data-ttu-id="409af-126">Asignación basada en atributos</span><span class="sxs-lookup"><span data-stu-id="409af-126">Attribute-Based Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)  
 [<span data-ttu-id="409af-127">Asignación externa</span><span class="sxs-lookup"><span data-stu-id="409af-127">External Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)  
 [<span data-ttu-id="409af-128">Asignación de tipos entre CLR y SQL</span><span class="sxs-lookup"><span data-stu-id="409af-128">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)  
 [<span data-ttu-id="409af-129">Información general</span><span class="sxs-lookup"><span data-stu-id="409af-129">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="409af-130">Realización y envío de cambios de datos</span><span class="sxs-lookup"><span data-stu-id="409af-130">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)

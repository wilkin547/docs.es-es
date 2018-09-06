---
title: 'Cómo: Crear un servicio de datos utilizando un origen de datos de LINQ to SQL (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
ms.openlocfilehash: e65d9dc48f128d7808f0731057ec0a5e52e65444
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43866837"
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a><span data-ttu-id="1c982-102">Cómo: Crear un servicio de datos utilizando un origen de datos de LINQ to SQL (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="1c982-102">How to: Create a Data Service Using a LINQ to SQL Data Source (WCF Data Services)</span></span>

<span data-ttu-id="1c982-103">WCF Data Services expone los datos de entidad como un servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="1c982-103">WCF Data Services exposes entity data as a data service.</span></span> <span data-ttu-id="1c982-104">El proveedor de reflexión le permite definir un modelo de datos que se basa en cualquier clase que expone miembros que devuelven un <xref:System.Linq.IQueryable%601> implementación.</span><span class="sxs-lookup"><span data-stu-id="1c982-104">The reflection provider enables you to define a data model that is based on any class that exposes members that return an <xref:System.Linq.IQueryable%601> implementation.</span></span> <span data-ttu-id="1c982-105">Para poder realizar actualizaciones en los datos del origen de datos, estas clases también deben implementar la interfaz <xref:System.Data.Services.IUpdatable>.</span><span class="sxs-lookup"><span data-stu-id="1c982-105">To be able to make updates to data in the data source, these classes must also implement the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="1c982-106">Para obtener más información, consulte [proveedores de servicios de datos](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1c982-106">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span> <span data-ttu-id="1c982-107">En este tema se muestra cómo crear clases LINQ to SQL que tienen acceso a la base de datos de ejemplo Northwind usando el proveedor de reflexión, así como el modo de crear el servicio de datos que está basado en estas clases de datos.</span><span class="sxs-lookup"><span data-stu-id="1c982-107">This topic shows you how to create LINQ to SQL classes that access the Northwind sample database by using the reflection provider, as well as how to create the data service that is based on these data classes.</span></span>

## <a name="to-add-linq-to-sql-classes-to-a-project"></a><span data-ttu-id="1c982-108">Para agregar clases LINQ to SQL a un proyecto</span><span class="sxs-lookup"><span data-stu-id="1c982-108">To add LINQ to SQL classes to a project</span></span>

1. <span data-ttu-id="1c982-109">Desde dentro de una aplicación de Visual Basic o C#, en el **proyecto** menú, haga clic en **agregar** > **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="1c982-109">From within a Visual Basic or C# application, on the **Project** menu, click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="1c982-110">Haga clic en el **clases LINQ to SQL** plantilla.</span><span class="sxs-lookup"><span data-stu-id="1c982-110">Click the **LINQ to SQL Classes** template.</span></span>

3. <span data-ttu-id="1c982-111">Cambie el nombre a **Northwind.dbml**.</span><span class="sxs-lookup"><span data-stu-id="1c982-111">Change the name to **Northwind.dbml**.</span></span>

4. <span data-ttu-id="1c982-112">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1c982-112">Click **Add**.</span></span>

     <span data-ttu-id="1c982-113">Se agrega al proyecto el archivo Northwind.dbml y se abre Object Relational Designer (O/R Designer).</span><span class="sxs-lookup"><span data-stu-id="1c982-113">The Northwind.dbml file is added to the project and the Object Relational Designer (O/R Designer) opens.</span></span>

5. <span data-ttu-id="1c982-114">En **Server**/**Database Explorer**, bajo Northwind, expanda **tablas** y arrastre el `Customers` tabla en Object Relational Designer (Object Relational Diseñador).</span><span class="sxs-lookup"><span data-stu-id="1c982-114">In **Server**/**Database Explorer**, under Northwind, expand **Tables** and drag the `Customers` table onto the Object Relational Designer (O/R Designer).</span></span>

     <span data-ttu-id="1c982-115">Se crea una clase de entidad `Customer` que aparece en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="1c982-115">A `Customer` entity class is created and appears on the design surface.</span></span>

6. <span data-ttu-id="1c982-116">Repita el paso 6 para las tablas `Orders`, `Order_Details` y `Products`.</span><span class="sxs-lookup"><span data-stu-id="1c982-116">Repeat step 6 for the `Orders`, `Order_Details`, and `Products` tables.</span></span>

7. <span data-ttu-id="1c982-117">Haga clic en el nuevo archivo .dbml que representa el LINQ a las clases SQL y haga clic en **ver código**.</span><span class="sxs-lookup"><span data-stu-id="1c982-117">Right-click the new .dbml file that represents the LINQ to SQL classes and click **View Code**.</span></span>

     <span data-ttu-id="1c982-118">Esto crea una nueva página de codigos subyacente denominada Northwind.cs que contiene una definición de clase parcial para la clase que hereda de la clase <xref:System.Data.Linq.DataContext>, que en este caso es `NorthwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="1c982-118">This creates a new code-behind page named Northwind.cs that contains a partial class definition for the class that inherits from the <xref:System.Data.Linq.DataContext> class, which in this case is `NorthwindDataContext`.</span></span>

8. <span data-ttu-id="1c982-119">Reemplace el contenido del archivo de código Northwind.cs por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="1c982-119">Replace the contents of the Northwind.cs code file with the following code.</span></span> <span data-ttu-id="1c982-120">Este código implementa el proveedor de reflexión extendiendo la clase <xref:System.Data.Linq.DataContext> y las clases de datos generadas por LINQ to SQL:</span><span class="sxs-lookup"><span data-stu-id="1c982-120">This code implements the reflection provider by extending the <xref:System.Data.Linq.DataContext> and data classes generated by LINQ to SQL:</span></span>

     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.vb#linq2sqlprovider)]

### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a><span data-ttu-id="1c982-121">Para crear un servicio de datos usando un modelo de datos basado en LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1c982-121">To create a data service by using a LINQ to SQL-based data model</span></span>

1. <span data-ttu-id="1c982-122">En **el Explorador de soluciones**, haga clic en el nombre del proyecto de ASP.NET y, a continuación, haga clic en **agregar** > **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="1c982-122">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="1c982-123">En el **Agregar nuevo elemento** cuadro de diálogo, seleccione el **WCF Data Service** plantilla desde el **Web** categoría.</span><span class="sxs-lookup"><span data-stu-id="1c982-123">In the **Add New Item** dialog box, select the **WCF Data Service** template from the **Web** category.</span></span>

   ![Plantilla de elemento de servicio de datos de WCF en Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="1c982-125">El **WCF Data Service** plantilla está disponible en Visual Studio 2015, pero no en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="1c982-125">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

3. <span data-ttu-id="1c982-126">Proporcione un nombre para el servicio y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1c982-126">Supply a name for the service, and then click **OK**.</span></span>

     <span data-ttu-id="1c982-127">Visual Studio crea los archivos de código y marcado XML para el nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="1c982-127">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="1c982-128">De forma predeterminada, se abre la ventana del editor de código.</span><span class="sxs-lookup"><span data-stu-id="1c982-128">By default, the code-editor window opens.</span></span>

4. <span data-ttu-id="1c982-129">En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que es el contenedor de entidades del modelo de datos, que en este caso es `NorthwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="1c982-129">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindDataContext`.</span></span>

5. <span data-ttu-id="1c982-130">En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="1c982-130">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.svc.vb#enableaccess)]

     <span data-ttu-id="1c982-131">Esto permite a los clientes autorizados tener acceso a los recursos para los tres conjuntos de entidades especificados.</span><span class="sxs-lookup"><span data-stu-id="1c982-131">This enables authorized clients to access resources for the three specified entity sets.</span></span>

6. <span data-ttu-id="1c982-132">Para probar el servicio de datos Northwind.svc usando un explorador Web, siga las instrucciones del tema [acceder al servicio desde un explorador Web](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="1c982-132">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1c982-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c982-133">See Also</span></span>

- [<span data-ttu-id="1c982-134">Creación de un servicio de datos con un origen de datos de ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="1c982-134">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)
- [<span data-ttu-id="1c982-135">Creación de un servicio de datos utilizando el proveedor de reflexión</span><span class="sxs-lookup"><span data-stu-id="1c982-135">How to: Create a Data Service Using the Reflection Provider</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)
- [<span data-ttu-id="1c982-136">Proveedores de Data Services</span><span class="sxs-lookup"><span data-stu-id="1c982-136">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
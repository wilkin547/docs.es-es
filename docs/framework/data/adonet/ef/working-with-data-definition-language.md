---
title: Trabajar con lenguaje de definición de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
ms.openlocfilehash: 788388b93a00cf5393174d35b8a160b4991da3bc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743719"
---
# <a name="working-with-data-definition-language"></a><span data-ttu-id="98887-102">Trabajar con lenguaje de definición de datos</span><span class="sxs-lookup"><span data-stu-id="98887-102">Working with Data Definition Language</span></span>
<span data-ttu-id="98887-103">A partir de .NET Framework versión 4, el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] es compatible con el lenguaje de definición de datos (DDL).</span><span class="sxs-lookup"><span data-stu-id="98887-103">Starting with the .NET Framework version 4, the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supports data definition language (DDL).</span></span> <span data-ttu-id="98887-104">Esto le permite crear o eliminar una instancia de la base de datos basada en la cadena de conexión y los metadatos del modelo de almacenamiento (SSDL).</span><span class="sxs-lookup"><span data-stu-id="98887-104">This allows you to create or delete a database instance based on the connection string and the metadata of the storage (SSDL) model.</span></span>  
  
 <span data-ttu-id="98887-105">Los siguientes métodos de <xref:System.Data.Objects.ObjectContext> utilizan la cadena de conexión y el contenido SSDL para crear o eliminar la base de datos, comprobar si la base de datos existe y ver el script DDL generado:</span><span class="sxs-lookup"><span data-stu-id="98887-105">The following methods on the <xref:System.Data.Objects.ObjectContext> use the connection string and the SSDL content to accomplish the following: create or delete the database, check whether the database exists, and view the generated DDL script:</span></span>  
  
- <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
- <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
- <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
- <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  <span data-ttu-id="98887-106">La ejecución de los comandos DDL supone que se cuenta con los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="98887-106">Executing the DDL commands assumes sufficient permissions.</span></span>  
  
 <span data-ttu-id="98887-107">Los métodos enumerados anteriormente delegan la mayoría del trabajo en el proveedor de datos de ADO.NET subyacente.</span><span class="sxs-lookup"><span data-stu-id="98887-107">The methods previously listed delegate most of the work to the underlying ADO.NET data provider.</span></span> <span data-ttu-id="98887-108">Es responsabilidad del proveedor asegurarse de que la convención de nomenclatura utilizada para generar los objetos de base de datos es coherente con las convenciones utilizadas para las consultas y las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="98887-108">It is the provider’s responsibility to ensure that the naming convention used to generate database objects is consistent with conventions used for querying and updates.</span></span>  
  
 <span data-ttu-id="98887-109">En el siguiente ejemplo se muestra cómo generar la base de datos en función del modelo existente.</span><span class="sxs-lookup"><span data-stu-id="98887-109">The following example shows you how to generate the database based on the existing model.</span></span> <span data-ttu-id="98887-110">También agrega un nuevo objeto entidad al contexto del objeto y, a continuación, lo guarda en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="98887-110">It also adds a new entity object to the object context and then saves it to the database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="98887-111">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="98887-111">Procedures</span></span>  
  
### <a name="to-define-a-database-based-on-the-existing-model"></a><span data-ttu-id="98887-112">Para definir una base de datos en función del modelo existente</span><span class="sxs-lookup"><span data-stu-id="98887-112">To define a database based on the existing model</span></span>  
  
1. <span data-ttu-id="98887-113">Cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="98887-113">Create a console application.</span></span>  
  
2. <span data-ttu-id="98887-114">Agregue un modelo existente a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98887-114">Add an existing model to your application.</span></span>  
  
    1. <span data-ttu-id="98887-115">Agregar un modelo vacío denominado `SchoolModel`.</span><span class="sxs-lookup"><span data-stu-id="98887-115">Add an empty model named `SchoolModel`.</span></span> <span data-ttu-id="98887-116">Para crear un modelo vacío, consulte el [Cómo: Crear un nuevo archivo .edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100)) tema.</span><span class="sxs-lookup"><span data-stu-id="98887-116">To create an empty model, see the [How to: Create a New .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100)) topic.</span></span>  
  
     <span data-ttu-id="98887-117">El archivo SchoolModel.edmx se añade al proyecto.</span><span class="sxs-lookup"><span data-stu-id="98887-117">The SchoolModel.edmx file is added to your project.</span></span>  
  
    1. <span data-ttu-id="98887-118">Copie el conceptual, almacenamiento y la asignación de contenido para el modelo School desde el [modelo School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) tema.</span><span class="sxs-lookup"><span data-stu-id="98887-118">Copy the conceptual, storage, and mapping content for the School model from the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) topic.</span></span>  
  
    2. <span data-ttu-id="98887-119">Abra el archivo SchoolModel.edmx y pegue el contenido dentro de las etiquetas `edmx:Runtime`.</span><span class="sxs-lookup"><span data-stu-id="98887-119">Open the SchoolModel.edmx file and paste the content within the `edmx:Runtime` tags.</span></span>  
  
3. <span data-ttu-id="98887-120">Agregue el siguiente código a la función principal.</span><span class="sxs-lookup"><span data-stu-id="98887-120">Add the following code to your main function.</span></span> <span data-ttu-id="98887-121">El código inicializa la cadena de conexión en el servidor de bases de datos, ve el script DDL, crea la base de datos, agrega una nueva entidad al contexto y guarda los cambios en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="98887-121">The code initializes the connection string to your database server, views the DDL script, creates the database, adds a new entity to the context, and saves the changes to the database.</span></span>  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]

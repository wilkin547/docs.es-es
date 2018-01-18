---
title: "Trabajar con lenguaje de definición de datos"
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
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8b363105f0dd6978d4e59678fb7cd1b3f1d721df
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="working-with-data-definition-language"></a><span data-ttu-id="64461-102">Trabajar con lenguaje de definición de datos</span><span class="sxs-lookup"><span data-stu-id="64461-102">Working with Data Definition Language</span></span>
<span data-ttu-id="64461-103">A partir de la [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] versión 4, el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] es compatible con el lenguaje de definición de datos (DDL).</span><span class="sxs-lookup"><span data-stu-id="64461-103">Starting with the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] version 4, the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supports data definition language (DDL).</span></span> <span data-ttu-id="64461-104">Esto le permite crear o eliminar una instancia de la base de datos basada en la cadena de conexión y los metadatos del modelo de almacenamiento (SSDL).</span><span class="sxs-lookup"><span data-stu-id="64461-104">This allows you to create or delete a database instance based on the connection string and the metadata of the storage (SSDL) model.</span></span>  
  
 <span data-ttu-id="64461-105">Los siguientes métodos de <xref:System.Data.Objects.ObjectContext> utilizan la cadena de conexión y el contenido SSDL para crear o eliminar la base de datos, comprobar si la base de datos existe y ver el script DDL generado:</span><span class="sxs-lookup"><span data-stu-id="64461-105">The following methods on the <xref:System.Data.Objects.ObjectContext> use the connection string and the SSDL content to accomplish the following: create or delete the database, check whether the database exists, and view the generated DDL script:</span></span>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  <span data-ttu-id="64461-106">La ejecución de los comandos DDL supone que se cuenta con los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="64461-106">Executing the DDL commands assumes sufficient permissions.</span></span>  
  
 <span data-ttu-id="64461-107">Los métodos enumerados anteriormente delegan la mayoría del trabajo en el proveedor de datos de ADO.NET subyacente.</span><span class="sxs-lookup"><span data-stu-id="64461-107">The methods previously listed delegate most of the work to the underlying ADO.NET data provider.</span></span> <span data-ttu-id="64461-108">Es responsabilidad del proveedor asegurarse de que la convención de nomenclatura utilizada para generar los objetos de base de datos es coherente con las convenciones utilizadas para las consultas y las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="64461-108">It is the provider’s responsibility to ensure that the naming convention used to generate database objects is consistent with conventions used for querying and updates.</span></span>  
  
 <span data-ttu-id="64461-109">En el siguiente ejemplo se muestra cómo generar la base de datos en función del modelo existente.</span><span class="sxs-lookup"><span data-stu-id="64461-109">The following example shows you how to generate the database based on the existing model.</span></span> <span data-ttu-id="64461-110">También agrega un nuevo objeto entidad al contexto del objeto y, a continuación, lo guarda en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="64461-110">It also adds a new entity object to the object context and then saves it to the database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="64461-111">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="64461-111">Procedures</span></span>  
  
#### <a name="to-define-a-database-based-on-the-existing-model"></a><span data-ttu-id="64461-112">Para definir una base de datos en función del modelo existente</span><span class="sxs-lookup"><span data-stu-id="64461-112">To define a database based on the existing model</span></span>  
  
1.  <span data-ttu-id="64461-113">Cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="64461-113">Create a console application.</span></span>  
  
2.  <span data-ttu-id="64461-114">Agregue un modelo existente a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="64461-114">Add an existing model to your application.</span></span>  
  
    1.  <span data-ttu-id="64461-115">Agregar un modelo vacío denominado `SchoolModel`.</span><span class="sxs-lookup"><span data-stu-id="64461-115">Add an empty model named `SchoolModel`.</span></span> <span data-ttu-id="64461-116">Para crear un modelo vacío, consulte el [Cómo: crear un nuevo archivo de .edmx](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2) tema.</span><span class="sxs-lookup"><span data-stu-id="64461-116">To create an empty model, see the [How to: Create a New .edmx File](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2) topic.</span></span>  
  
     <span data-ttu-id="64461-117">El archivo SchoolModel.edmx se añade al proyecto.</span><span class="sxs-lookup"><span data-stu-id="64461-117">The SchoolModel.edmx file is added to your project.</span></span>  
  
    1.  <span data-ttu-id="64461-118">Copie el almacenamiento de información conceptual y asignación de contenido para el modelo School desde el [modelo School](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) tema.</span><span class="sxs-lookup"><span data-stu-id="64461-118">Copy the conceptual, storage, and mapping content for the School model from the [School Model](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) topic.</span></span>  
  
    2.  <span data-ttu-id="64461-119">Abra el archivo SchoolModel.edmx y pegue el contenido dentro de las etiquetas `edmx:Runtime`.</span><span class="sxs-lookup"><span data-stu-id="64461-119">Open the SchoolModel.edmx file and paste the content within the `edmx:Runtime` tags.</span></span>  
  
3.  <span data-ttu-id="64461-120">Agregue el siguiente código a la función principal.</span><span class="sxs-lookup"><span data-stu-id="64461-120">Add the following code to your main function.</span></span> <span data-ttu-id="64461-121">El código inicializa la cadena de conexión en el servidor de bases de datos, ve el script DDL, crea la base de datos, agrega una nueva entidad al contexto y guarda los cambios en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="64461-121">The code initializes the connection string to your database server, views the DDL script, creates the database, adds a new entity to the context, and saves the changes to the database.</span></span>  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]

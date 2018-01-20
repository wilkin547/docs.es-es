---
title: "Cómo: Hacer que los archivos de asignación y de modelo sean recursos incrustados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 60c17ebbdd4b7e7f460855d4888a922da9c953d2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="651af-102">Cómo: Hacer que los archivos de asignación y de modelo sean recursos incrustados</span><span class="sxs-lookup"><span data-stu-id="651af-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="651af-103">El [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] le permite implementar los archivos de asignación y modelo como recursos incrustados de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="651af-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="651af-104">El ensamblado con los archivos de asignación y de modelo incrustados se debe cargar en el mismo dominio de aplicación que la conexión de entidad.</span><span class="sxs-lookup"><span data-stu-id="651af-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="651af-105">Para más información, consulte [Cadenas de conexión](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="651af-105">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span> <span data-ttu-id="651af-106">De forma predeterminada, las herramientas de [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] incrustan los archivos de asignación y de modelo.</span><span class="sxs-lookup"><span data-stu-id="651af-106">By default, the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] tools embed the model and mapping files.</span></span> <span data-ttu-id="651af-107">Cuando defina los archivos de asignación y de modelo manualmente, use este procedimiento para asegurarse de que dichos archivos se implementan como recursos incrustados junto con una aplicación de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="651af-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="651af-108">Para mantener los recursos incrustados, deberá repetir este procedimiento cada vez que se modifiquen los archivos de asignación y de modelo.</span><span class="sxs-lookup"><span data-stu-id="651af-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="651af-109">Para incrustar los archivos de asignación y de modelo</span><span class="sxs-lookup"><span data-stu-id="651af-109">To embed model and mapping files</span></span>  
  
1.  <span data-ttu-id="651af-110">En **el Explorador de soluciones**, seleccione el archivo conceptual (.csdl).</span><span class="sxs-lookup"><span data-stu-id="651af-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2.  <span data-ttu-id="651af-111">En el **propiedades** panel, establezca **acción de compilación** a **recurso incrustado**.</span><span class="sxs-lookup"><span data-stu-id="651af-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3.  <span data-ttu-id="651af-112">Repita los pasos 1 y 2 para el archivo de almacenamiento (.ssdl) y el archivo de asignación (.msl).</span><span class="sxs-lookup"><span data-stu-id="651af-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4.  <span data-ttu-id="651af-113">En **el Explorador de soluciones**, haga doble clic en el archivo App.config y, a continuación, modifique la `Metadata` parámetro en el `connectionString` atributo basado en uno de los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="651af-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    -   <span data-ttu-id="651af-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="651af-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    -   <span data-ttu-id="651af-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="651af-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    -   `Metadata=res://*;`  
  
     <span data-ttu-id="651af-116">Para más información, consulte [Cadenas de conexión](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="651af-116">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="651af-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="651af-117">Example</span></span>  
 <span data-ttu-id="651af-118">Hace referencia a la siguiente cadena de conexión para los archivos de asignación y de modelo incrustados el [modelo AdventureWorks Sales](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832).</span><span class="sxs-lookup"><span data-stu-id="651af-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832).</span></span> <span data-ttu-id="651af-119">Esta cadena de conexión está almacenada en el archivo App.config del proyecto.</span><span class="sxs-lookup"><span data-stu-id="651af-119">This connection string is stored in the project's App.config file.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="651af-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="651af-120">See Also</span></span>  
 [<span data-ttu-id="651af-121">Modelado y asignación</span><span class="sxs-lookup"><span data-stu-id="651af-121">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [<span data-ttu-id="651af-122">Definición de la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="651af-122">How to: Define the Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)  
 [<span data-ttu-id="651af-123">Compilación de una cadena de conexión EntityConnection</span><span class="sxs-lookup"><span data-stu-id="651af-123">How to: Build an EntityConnection Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
 [<span data-ttu-id="651af-124">Herramientas de Entity Data Model de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="651af-124">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)

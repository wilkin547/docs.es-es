---
title: Filtrar para hacer que los archivos de asignación y de modelo sean recursos incrustados
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: b00ccdd0a1fc1cb22cf7cc0d0a3177dcc0e8017f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138598"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="e2e90-102">Filtrar para hacer que los archivos de asignación y de modelo sean recursos incrustados</span><span class="sxs-lookup"><span data-stu-id="e2e90-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="e2e90-103">El [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] le permite implementar los archivos de asignación y modelo como recursos incrustados de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="e2e90-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="e2e90-104">El ensamblado con los archivos de asignación y de modelo incrustados se debe cargar en el mismo dominio de aplicación que la conexión de entidad.</span><span class="sxs-lookup"><span data-stu-id="e2e90-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="e2e90-105">Para más información, consulte [Cadenas de conexión](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="e2e90-105">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span> <span data-ttu-id="e2e90-106">De forma predeterminada, las herramientas de [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] incrustan los archivos de asignación y de modelo.</span><span class="sxs-lookup"><span data-stu-id="e2e90-106">By default, the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] tools embed the model and mapping files.</span></span> <span data-ttu-id="e2e90-107">Cuando defina los archivos de asignación y de modelo manualmente, use este procedimiento para asegurarse de que dichos archivos se implementan como recursos incrustados junto con una aplicación de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2e90-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2e90-108">Para mantener los recursos incrustados, deberá repetir este procedimiento cada vez que se modifiquen los archivos de asignación y de modelo.</span><span class="sxs-lookup"><span data-stu-id="e2e90-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="e2e90-109">Para incrustar los archivos de asignación y de modelo</span><span class="sxs-lookup"><span data-stu-id="e2e90-109">To embed model and mapping files</span></span>  
  
1.  <span data-ttu-id="e2e90-110">En **el Explorador de soluciones**, seleccione el archivo conceptual (.csdl).</span><span class="sxs-lookup"><span data-stu-id="e2e90-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2.  <span data-ttu-id="e2e90-111">En el **propiedades** panel, establezca **acción de compilación** a **recurso incrustado**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3.  <span data-ttu-id="e2e90-112">Repita los pasos 1 y 2 para el archivo de almacenamiento (.ssdl) y el archivo de asignación (.msl).</span><span class="sxs-lookup"><span data-stu-id="e2e90-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4.  <span data-ttu-id="e2e90-113">En **el Explorador de soluciones**, haga doble clic en el archivo App.config y, a continuación, modifique la `Metadata` parámetro en el `connectionString` atributo basado en uno de los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="e2e90-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    -   `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    -   `Metadata=` `res://*/<resourceName>;`  
  
    -   `Metadata=res://*;`  
  
     <span data-ttu-id="e2e90-114">Para más información, consulte [Cadenas de conexión](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="e2e90-114">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2e90-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2e90-115">Example</span></span>  
 <span data-ttu-id="e2e90-116">La cadena de conexión siguiente hace referencia a un modelo incrustado y archivos de asignación para el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="e2e90-116">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="e2e90-117">Esta cadena de conexión está almacenada en el archivo App.config del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e2e90-117">This connection string is stored in the project's App.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e2e90-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2e90-118">See also</span></span>

- [<span data-ttu-id="e2e90-119">Modelado y asignación</span><span class="sxs-lookup"><span data-stu-id="e2e90-119">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="e2e90-120">Filtrar para defina la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="e2e90-120">How to: Define the Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)
- [<span data-ttu-id="e2e90-121">Filtrar para compilar una cadena de conexión EntityConnection</span><span class="sxs-lookup"><span data-stu-id="e2e90-121">How to: Build an EntityConnection Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)
- [<span data-ttu-id="e2e90-122">Herramientas de Entity Data Model de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e2e90-122">ADO.NET Entity Data Model Tools</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))

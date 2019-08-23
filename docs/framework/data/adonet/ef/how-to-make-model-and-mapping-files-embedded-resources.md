---
title: Procedimiento para hacer que los archivos de asignación y de modelo sean recursos incrustados
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: 53817498f6d772c308888c5e994fb25239c4ed61
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949741"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="1c315-102">Procedimiento para hacer que los archivos de asignación y de modelo sean recursos incrustados</span><span class="sxs-lookup"><span data-stu-id="1c315-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="1c315-103">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Permite implementar archivos de asignación y de modelo como recursos incrustados de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="1c315-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="1c315-104">El ensamblado con los archivos de asignación y de modelo incrustados se debe cargar en el mismo dominio de aplicación que la conexión de entidad.</span><span class="sxs-lookup"><span data-stu-id="1c315-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="1c315-105">Para más información, consulte [Cadenas de conexión](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="1c315-105">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span> <span data-ttu-id="1c315-106">De forma predeterminada, las herramientas de Entity Data Model insertan los archivos de asignación y de modelo.</span><span class="sxs-lookup"><span data-stu-id="1c315-106">By default, the Entity Data Model tools embed the model and mapping files.</span></span> <span data-ttu-id="1c315-107">Cuando defina los archivos de asignación y de modelo manualmente, use este procedimiento para asegurarse de que dichos archivos se implementan como recursos incrustados junto con una aplicación de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c315-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1c315-108">Para mantener los recursos incrustados, deberá repetir este procedimiento cada vez que se modifiquen los archivos de asignación y de modelo.</span><span class="sxs-lookup"><span data-stu-id="1c315-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="1c315-109">Para incrustar los archivos de asignación y de modelo</span><span class="sxs-lookup"><span data-stu-id="1c315-109">To embed model and mapping files</span></span>  
  
1. <span data-ttu-id="1c315-110">En **Explorador de soluciones**, seleccione el archivo conceptual (. CSDL).</span><span class="sxs-lookup"><span data-stu-id="1c315-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2. <span data-ttu-id="1c315-111">En el panel **propiedades** , establezca **acción de compilación** en **recurso incrustado**.</span><span class="sxs-lookup"><span data-stu-id="1c315-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3. <span data-ttu-id="1c315-112">Repita los pasos 1 y 2 para el archivo de almacenamiento (.ssdl) y el archivo de asignación (.msl).</span><span class="sxs-lookup"><span data-stu-id="1c315-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4. <span data-ttu-id="1c315-113">En **Explorador de soluciones**, haga doble clic en el archivo app. config y, a `Metadata` continuación, modifique `connectionString` el parámetro en el atributo basándose en uno de los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="1c315-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    - <span data-ttu-id="1c315-114">`Metadata=``res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="1c315-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    - <span data-ttu-id="1c315-115">`Metadata=``res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="1c315-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    - `Metadata=res://*;`  
  
     <span data-ttu-id="1c315-116">Para más información, consulte [Cadenas de conexión](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="1c315-116">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c315-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c315-117">Example</span></span>  
 <span data-ttu-id="1c315-118">La siguiente cadena de conexión hace referencia a los archivos de asignación y de modelo incrustados para el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="1c315-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="1c315-119">Esta cadena de conexión está almacenada en el archivo App.config del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1c315-119">This connection string is stored in the project's App.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="1c315-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c315-120">See also</span></span>

- [<span data-ttu-id="1c315-121">Modelado y asignación</span><span class="sxs-lookup"><span data-stu-id="1c315-121">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="1c315-122">Cómo: Definir la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="1c315-122">How to: Define the Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)
- [<span data-ttu-id="1c315-123">Cómo: Compilación de una cadena de conexión de EntityConnection</span><span class="sxs-lookup"><span data-stu-id="1c315-123">How to: Build an EntityConnection Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)
- <span data-ttu-id="1c315-124">[ADO.NET Entity Data Model herramientas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1c315-124">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>

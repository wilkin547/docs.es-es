---
title: Procedimiento para hacer que los archivos de asignación y de modelo sean recursos incrustados
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: aaab2ccc96497cb718b868f7ac63995ad4ba35c8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546684"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="1a5fa-102">Procedimiento para hacer que los archivos de asignación y de modelo sean recursos incrustados</span><span class="sxs-lookup"><span data-stu-id="1a5fa-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="1a5fa-103">El Entity Framework permite implementar archivos de asignación y de modelo como recursos incrustados de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="1a5fa-103">The Entity Framework enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="1a5fa-104">El ensamblado con los archivos de asignación y de modelo incrustados se debe cargar en el mismo dominio de aplicación que la conexión de entidad.</span><span class="sxs-lookup"><span data-stu-id="1a5fa-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="1a5fa-105">Para obtener más información, consulte [cadenas de conexión](connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="1a5fa-105">For more information, see [Connection Strings](connection-strings.md).</span></span> <span data-ttu-id="1a5fa-106">De forma predeterminada, las herramientas de Entity Data Model insertan los archivos de asignación y de modelo.</span><span class="sxs-lookup"><span data-stu-id="1a5fa-106">By default, the Entity Data Model tools embed the model and mapping files.</span></span> <span data-ttu-id="1a5fa-107">Al definir manualmente los archivos de asignación y de modelo, use este procedimiento para asegurarse de que los archivos se implementan como recursos incrustados junto con una aplicación Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="1a5fa-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an Entity Framework application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1a5fa-108">Para mantener los recursos incrustados, deberá repetir este procedimiento cada vez que se modifiquen los archivos de asignación y de modelo.</span><span class="sxs-lookup"><span data-stu-id="1a5fa-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="1a5fa-109">Para incrustar los archivos de asignación y de modelo</span><span class="sxs-lookup"><span data-stu-id="1a5fa-109">To embed model and mapping files</span></span>  
  
1. <span data-ttu-id="1a5fa-110">En **Explorador de soluciones**, seleccione el archivo conceptual (. CSDL).</span><span class="sxs-lookup"><span data-stu-id="1a5fa-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2. <span data-ttu-id="1a5fa-111">En el panel **propiedades** , establezca **acción de compilación** en **recurso incrustado**.</span><span class="sxs-lookup"><span data-stu-id="1a5fa-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3. <span data-ttu-id="1a5fa-112">Repita los pasos 1 y 2 para el archivo de almacenamiento (.ssdl) y el archivo de asignación (.msl).</span><span class="sxs-lookup"><span data-stu-id="1a5fa-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4. <span data-ttu-id="1a5fa-113">En **Explorador de soluciones**, haga doble clic en el archivo de App.config y, a continuación, modifique el `Metadata` parámetro en el `connectionString` atributo basándose en uno de los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="1a5fa-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    - <span data-ttu-id="1a5fa-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="1a5fa-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    - <span data-ttu-id="1a5fa-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="1a5fa-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    - `Metadata=res://*;`  
  
     <span data-ttu-id="1a5fa-116">Para obtener más información, consulte [cadenas de conexión](connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="1a5fa-116">For more information, see [Connection Strings](connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a5fa-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1a5fa-117">Example</span></span>  
 <span data-ttu-id="1a5fa-118">La siguiente cadena de conexión hace referencia a los archivos de asignación y de modelo incrustados para el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="1a5fa-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="1a5fa-119">Esta cadena de conexión está almacenada en el archivo App.config del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1a5fa-119">This connection string is stored in the project's App.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="1a5fa-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a5fa-120">See also</span></span>

- [<span data-ttu-id="1a5fa-121">Modelado y asignación</span><span class="sxs-lookup"><span data-stu-id="1a5fa-121">Modeling and Mapping</span></span>](modeling-and-mapping.md)
- [<span data-ttu-id="1a5fa-122">Procedimiento para defina la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="1a5fa-122">How to: Define the Connection String</span></span>](how-to-define-the-connection-string.md)
- [<span data-ttu-id="1a5fa-123">Procedimiento para compilar una cadena de conexión EntityConnection</span><span class="sxs-lookup"><span data-stu-id="1a5fa-123">How to: Build an EntityConnection Connection String</span></span>](how-to-build-an-entityconnection-connection-string.md)
- <span data-ttu-id="1a5fa-124">[ADO.NET Entity Data Model herramientas](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1a5fa-124">[ADO.NET Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>

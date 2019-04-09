---
title: Filtrar para usar EdmGen.exe para validar los archivos de asignación y de modelo
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: 1981e293d634af451a7084ac519a97f1ad5b5fd6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076525"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a><span data-ttu-id="82ec0-102">Filtrar para usar EdmGen.exe para validar los archivos de asignación y de modelo</span><span class="sxs-lookup"><span data-stu-id="82ec0-102">How to: Use EdmGen.exe to Validate Model and Mapping Files</span></span>
<span data-ttu-id="82ec0-103">En este tema se muestra cómo usar el [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) herramienta para validar los archivos de asignación y modelo.</span><span class="sxs-lookup"><span data-stu-id="82ec0-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to validate the model and mapping files.</span></span> <span data-ttu-id="82ec0-104">Para obtener más información, consulte [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).</span><span class="sxs-lookup"><span data-stu-id="82ec0-104">For more information, see [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).</span></span>  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a><span data-ttu-id="82ec0-105">Para validar el modelo School mediante el uso de EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="82ec0-105">To validate the School model using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="82ec0-106">Cree la base de datos School.</span><span class="sxs-lookup"><span data-stu-id="82ec0-106">Create the School database.</span></span> <span data-ttu-id="82ec0-107">Para obtener más información, consulte [crear la base de datos de ejemplo School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="82ec0-107">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="82ec0-108">Genere el modelo School.</span><span class="sxs-lookup"><span data-stu-id="82ec0-108">Generate the School model.</span></span> <span data-ttu-id="82ec0-109">Para obtener más información, vea [Cómo: Usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="82ec0-109">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="82ec0-110">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="82ec0-110">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="82ec0-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="82ec0-111">See also</span></span>

- [<span data-ttu-id="82ec0-112">Filtrar Configurar manualmente un proyecto de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="82ec0-112">How to: Manually Configure an Entity Framework Project</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [<span data-ttu-id="82ec0-113">Herramientas de Entity Data Model de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="82ec0-113">ADO.NET Entity Data Model Tools</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [<span data-ttu-id="82ec0-114">Filtrar Generar previamente vistas para mejorar el rendimiento de las consultas</span><span class="sxs-lookup"><span data-stu-id="82ec0-114">How to: Pre-Generate Views to Improve Query Performance</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [<span data-ttu-id="82ec0-115">Filtrar para usar EdmGen.exe para generar código de capa de objeto</span><span class="sxs-lookup"><span data-stu-id="82ec0-115">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)

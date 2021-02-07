---
description: 'Más información acerca de cómo: usar EdmGen.exe para validar los archivos de asignación y de modelo'
title: Procedimiento para usar EdmGen.exe para validar los archivos de asignación y de modelo
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: e729ea36b7ff17dc318f4488a669b968161aea8b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697353"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a><span data-ttu-id="59a59-103">Procedimiento para usar EdmGen.exe para validar los archivos de asignación y de modelo</span><span class="sxs-lookup"><span data-stu-id="59a59-103">How to: Use EdmGen.exe to Validate Model and Mapping Files</span></span>

<span data-ttu-id="59a59-104">En este tema se muestra cómo usar la herramienta [generador de EDM (EdmGen.exe)](edm-generator-edmgen-exe.md) para validar los archivos de asignación y de modelo.</span><span class="sxs-lookup"><span data-stu-id="59a59-104">This topic shows how to use the [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md) tool to validate the model and mapping files.</span></span> <span data-ttu-id="59a59-105">Para obtener más información, vea [Entity Data Model](../entity-data-model.md).</span><span class="sxs-lookup"><span data-stu-id="59a59-105">For more information, see [Entity Data Model](../entity-data-model.md).</span></span>  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a><span data-ttu-id="59a59-106">Para validar el modelo School mediante el uso de EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="59a59-106">To validate the School model using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="59a59-107">Cree la base de datos School.</span><span class="sxs-lookup"><span data-stu-id="59a59-107">Create the School database.</span></span> <span data-ttu-id="59a59-108">Para obtener más información, vea [crear la base de datos de ejemplo School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="59a59-108">For more information, see [Creating the School Sample Database](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="59a59-109">Genere el modelo School.</span><span class="sxs-lookup"><span data-stu-id="59a59-109">Generate the School model.</span></span> <span data-ttu-id="59a59-110">Para obtener más información, vea [Cómo: usar EdmGen.exe para generar los archivos de asignación y de modelo](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="59a59-110">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="59a59-111">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="59a59-111">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="59a59-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="59a59-112">See also</span></span>

- <span data-ttu-id="59a59-113">[Cómo: Configurar manualmente un proyecto de Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="59a59-113">[How to: Manually Configure an Entity Framework Project](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span></span>
- <span data-ttu-id="59a59-114">[ADO.NET Entity Data Model herramientas](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="59a59-114">[ADO.NET Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="59a59-115">[Cómo: Generar previamente vistas para mejorar el rendimiento de la consulta](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="59a59-115">[How to: Pre-Generate Views to Improve Query Performance](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span></span>
- [<span data-ttu-id="59a59-116">Procedimiento para usar EdmGen.exe para generar código de capa de objeto</span><span class="sxs-lookup"><span data-stu-id="59a59-116">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>](how-to-use-edmgen-exe-to-generate-object-layer-code.md)

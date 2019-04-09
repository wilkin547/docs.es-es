---
title: Filtrar para usar EdmGen.exe para generar código de capa de objeto
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 04b35dbb5e487e573a2adfff196b79e10afdfb61
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188235"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="048cf-102">Filtrar para usar EdmGen.exe para generar código de capa de objeto</span><span class="sxs-lookup"><span data-stu-id="048cf-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="048cf-103">En este tema se muestra cómo usar el [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) herramienta para generar el código de capa de objeto basado en el archivo de CSDL.</span><span class="sxs-lookup"><span data-stu-id="048cf-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="048cf-104">Para generar código del nivel de objeto para el modelo School en un proyecto de Visual Basic utilizando EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="048cf-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="048cf-105">Cree la base de datos School.</span><span class="sxs-lookup"><span data-stu-id="048cf-105">Create the School database.</span></span> <span data-ttu-id="048cf-106">Para obtener más información, consulte [crear la base de datos de ejemplo School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="048cf-106">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="048cf-107">Genere el modelo School u obtenga el archivo School.csdl.</span><span class="sxs-lookup"><span data-stu-id="048cf-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="048cf-108">Para obtener más información, vea [Cómo: Usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="048cf-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="048cf-109">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="048cf-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="048cf-110">Para generar código del nivel de objeto para el modelo School en un proyecto de C# utilizando EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="048cf-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="048cf-111">Cree la base de datos School.</span><span class="sxs-lookup"><span data-stu-id="048cf-111">Create the School database.</span></span> <span data-ttu-id="048cf-112">Para obtener más información, consulte [crear la base de datos de ejemplo School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="048cf-112">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="048cf-113">Genere el modelo School u obtenga el archivo School.csdl.</span><span class="sxs-lookup"><span data-stu-id="048cf-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="048cf-114">Para obtener más información, vea [Cómo: Usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="048cf-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="048cf-115">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="048cf-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="048cf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="048cf-116">See also</span></span>

- [<span data-ttu-id="048cf-117">Modelado y asignación</span><span class="sxs-lookup"><span data-stu-id="048cf-117">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="048cf-118">Filtrar Configurar manualmente un proyecto de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="048cf-118">How to: Manually Configure an Entity Framework Project</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [<span data-ttu-id="048cf-119">Herramientas de ADO.NET Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="048cf-119">ADO.NET Entity Data Model  Tools</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [<span data-ttu-id="048cf-120">Filtrar Generar previamente vistas para mejorar el rendimiento de las consultas</span><span class="sxs-lookup"><span data-stu-id="048cf-120">How to: Pre-Generate Views to Improve Query Performance</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [<span data-ttu-id="048cf-121">Filtrar para usar EdmGen.exe para generar los archivos de asignación y de modelo</span><span class="sxs-lookup"><span data-stu-id="048cf-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)

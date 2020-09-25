---
title: Procedimiento para usar EdmGen.exe para generar código de capa de objeto
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: a243a588dcb6f7e7001de331cb9011a23ee2fdbe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198228"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="912a7-102">Procedimiento para usar EdmGen.exe para generar código de capa de objeto</span><span class="sxs-lookup"><span data-stu-id="912a7-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>

<span data-ttu-id="912a7-103">En este tema se muestra cómo usar la herramienta [generador de EDM (EdmGen.exe)](edm-generator-edmgen-exe.md) para generar código de nivel de objeto basado en el archivo. CSDL.</span><span class="sxs-lookup"><span data-stu-id="912a7-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="912a7-104">Para generar código del nivel de objeto para el modelo School en un proyecto de Visual Basic utilizando EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="912a7-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="912a7-105">Cree la base de datos School.</span><span class="sxs-lookup"><span data-stu-id="912a7-105">Create the School database.</span></span> <span data-ttu-id="912a7-106">Para obtener más información, vea [crear la base de datos de ejemplo School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="912a7-106">For more information, see [Creating the School Sample Database](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="912a7-107">Genere el modelo School u obtenga el archivo School.csdl.</span><span class="sxs-lookup"><span data-stu-id="912a7-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="912a7-108">Para obtener más información, vea [Cómo: usar EdmGen.exe para generar los archivos de asignación y de modelo](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="912a7-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="912a7-109">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="912a7-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="912a7-110">Para generar código del nivel de objeto para el modelo School en un proyecto de C# utilizando EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="912a7-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="912a7-111">Cree la base de datos School.</span><span class="sxs-lookup"><span data-stu-id="912a7-111">Create the School database.</span></span> <span data-ttu-id="912a7-112">Para obtener más información, vea [crear la base de datos de ejemplo School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="912a7-112">For more information, see [Creating the School Sample Database](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="912a7-113">Genere el modelo School u obtenga el archivo School.csdl.</span><span class="sxs-lookup"><span data-stu-id="912a7-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="912a7-114">Para obtener más información, vea [Cómo: usar EdmGen.exe para generar los archivos de asignación y de modelo](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="912a7-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="912a7-115">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="912a7-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="912a7-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="912a7-116">See also</span></span>

- [<span data-ttu-id="912a7-117">Modelado y asignación</span><span class="sxs-lookup"><span data-stu-id="912a7-117">Modeling and Mapping</span></span>](modeling-and-mapping.md)
- <span data-ttu-id="912a7-118">[Cómo: Configurar manualmente un proyecto de Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="912a7-118">[How to: Manually Configure an Entity Framework Project](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span></span>
- <span data-ttu-id="912a7-119">[Herramientas de Entity Data Model de ADO.NET](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="912a7-119">[ADO.NET Entity Data Model  Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="912a7-120">[Cómo: Generar previamente vistas para mejorar el rendimiento de la consulta](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="912a7-120">[How to: Pre-Generate Views to Improve Query Performance](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span></span>
- [<span data-ttu-id="912a7-121">Procedimiento para usar EdmGen.exe para generar los archivos de asignación y de modelo</span><span class="sxs-lookup"><span data-stu-id="912a7-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)

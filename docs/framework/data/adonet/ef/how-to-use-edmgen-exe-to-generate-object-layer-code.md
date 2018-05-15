---
title: 'Cómo: Usar EdmGen.exe para generar código de capa de objeto'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: cd919f382096af6ff3e5e27225619767f3922ff0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="b8d3e-102">Cómo: Usar EdmGen.exe para generar código de capa de objeto</span><span class="sxs-lookup"><span data-stu-id="b8d3e-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="b8d3e-103">Este tema muestra cómo utilizar el [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) herramienta para generar el código de capa de objeto basados en el archivo CSDL.</span><span class="sxs-lookup"><span data-stu-id="b8d3e-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="b8d3e-104">Para generar código del nivel de objeto para el modelo School en un proyecto de Visual Basic utilizando EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="b8d3e-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="b8d3e-105">Cree la base de datos School.</span><span class="sxs-lookup"><span data-stu-id="b8d3e-105">Create the School database.</span></span> <span data-ttu-id="b8d3e-106">Para obtener más información, consulte [crear la base de datos de ejemplo School](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="b8d3e-106">For more information, see [Creating the School Sample Database](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="b8d3e-107">Genere el modelo School u obtenga el archivo School.csdl.</span><span class="sxs-lookup"><span data-stu-id="b8d3e-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="b8d3e-108">Para obtener más información, consulte [Cómo: usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="b8d3e-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="b8d3e-109">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="b8d3e-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="b8d3e-110">Para generar código del nivel de objeto para el modelo School en un proyecto de C# utilizando EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="b8d3e-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="b8d3e-111">Cree la base de datos School.</span><span class="sxs-lookup"><span data-stu-id="b8d3e-111">Create the School database.</span></span> <span data-ttu-id="b8d3e-112">Para obtener más información, consulte [crear la base de datos de ejemplo School](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="b8d3e-112">For more information, see [Creating the School Sample Database](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="b8d3e-113">Genere el modelo School u obtenga el archivo School.csdl.</span><span class="sxs-lookup"><span data-stu-id="b8d3e-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="b8d3e-114">Para obtener más información, consulte [Cómo: usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="b8d3e-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="b8d3e-115">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="b8d3e-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b8d3e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8d3e-116">See Also</span></span>  
 [<span data-ttu-id="b8d3e-117">Modelado y asignación</span><span class="sxs-lookup"><span data-stu-id="b8d3e-117">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [<span data-ttu-id="b8d3e-118">Cómo: configurar manualmente un proyecto de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="b8d3e-118">How to: Manually Configure an Entity Framework Project</span></span>](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [<span data-ttu-id="b8d3e-119">Herramientas de Entity Data Model de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b8d3e-119">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="b8d3e-120">Cómo: generar previamente las vistas para mejorar el rendimiento de las consultas</span><span class="sxs-lookup"><span data-stu-id="b8d3e-120">How to: Pre-Generate Views to Improve Query Performance</span></span>](http://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [<span data-ttu-id="b8d3e-121">Uso de EdmGen.exe para generar los archivos de asignación y de modelo</span><span class="sxs-lookup"><span data-stu-id="b8d3e-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)

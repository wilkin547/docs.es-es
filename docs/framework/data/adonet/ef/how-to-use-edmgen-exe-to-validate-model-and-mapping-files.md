---
title: "Cómo: Usar EdmGen.exe para validar los archivos de asignación y de modelo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: ae70c90fc20265334cdfb55e4a0f88724284d822
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a><span data-ttu-id="7c595-102">Cómo: Usar EdmGen.exe para validar los archivos de asignación y de modelo</span><span class="sxs-lookup"><span data-stu-id="7c595-102">How to: Use EdmGen.exe to Validate Model and Mapping Files</span></span>
<span data-ttu-id="7c595-103">Este tema muestra cómo utilizar el [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) herramienta para validar los archivos de asignación y modelo.</span><span class="sxs-lookup"><span data-stu-id="7c595-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to validate the model and mapping files.</span></span> <span data-ttu-id="7c595-104">Para obtener más información, consulte [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).</span><span class="sxs-lookup"><span data-stu-id="7c595-104">For more information, see [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).</span></span>  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a><span data-ttu-id="7c595-105">Para validar el modelo School mediante el uso de EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="7c595-105">To validate the School model using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="7c595-106">Cree la base de datos School.</span><span class="sxs-lookup"><span data-stu-id="7c595-106">Create the School database.</span></span> <span data-ttu-id="7c595-107">Para obtener más información, consulte [crear la base de datos de ejemplo School](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="7c595-107">For more information, see [Creating the School Sample Database](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="7c595-108">Genere el modelo School.</span><span class="sxs-lookup"><span data-stu-id="7c595-108">Generate the School model.</span></span> <span data-ttu-id="7c595-109">Para obtener más información, consulte [Cómo: usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="7c595-109">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="7c595-110">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="7c595-110">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7c595-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c595-111">See Also</span></span>  
 [<span data-ttu-id="7c595-112">Cómo: configurar manualmente un proyecto de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="7c595-112">How to: Manually Configure an Entity Framework Project</span></span>](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [<span data-ttu-id="7c595-113">Herramientas de Entity Data Model de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7c595-113">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="7c595-114">Cómo: generar previamente las vistas para mejorar el rendimiento de las consultas</span><span class="sxs-lookup"><span data-stu-id="7c595-114">How to: Pre-Generate Views to Improve Query Performance</span></span>](http://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [<span data-ttu-id="7c595-115">Uso de EdmGen.exe para generar código de capa de objeto</span><span class="sxs-lookup"><span data-stu-id="7c595-115">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)

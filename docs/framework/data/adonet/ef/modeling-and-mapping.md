---
description: 'Más información acerca de: modelado y asignación'
title: Modelado y asignación
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 063cac072b7a205a471cd808fc85ad9a3ac71288
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795006"
---
# <a name="modeling-and-mapping"></a><span data-ttu-id="6f663-103">Modelado y asignación</span><span class="sxs-lookup"><span data-stu-id="6f663-103">Modeling and Mapping</span></span>

<span data-ttu-id="6f663-104">En el Entity Framework, puede definir el modelo conceptual, el modelo de almacenamiento y la asignación entre los dos de la forma que mejor se adapte a su aplicación.</span><span class="sxs-lookup"><span data-stu-id="6f663-104">In the Entity Framework, you can define the conceptual model, storage model, and the mapping between the two in the way that best suits your application.</span></span> <span data-ttu-id="6f663-105">Las herramientas de Entity Data Model de Visual Studio le permiten crear un. [archivo edmx](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) de una base de datos o un modelo gráfico y, a continuación, actualice el archivo cuando cambie la base de datos o el modelo.</span><span class="sxs-lookup"><span data-stu-id="6f663-105">The Entity Data Model Tools in Visual Studio allow you to create an .[edmx file](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) from a database or a graphical model and then update that file when either the database or model changes.</span></span>  
  
 <span data-ttu-id="6f663-106">A partir de Entity Framework 4.0.1 también puede crear un modelo mediante programación usando desarrollo Code First.</span><span class="sxs-lookup"><span data-stu-id="6f663-106">Starting with the Entity Framework 4.1 you can also create a model programmatically using Code First development.</span></span> <span data-ttu-id="6f663-107">Hay dos escenarios diferentes para el desarrollo Code First.</span><span class="sxs-lookup"><span data-stu-id="6f663-107">There are two different scenarios for Code First development.</span></span> <span data-ttu-id="6f663-108">En ambos casos, el desarrollador define un modelo codificando definiciones de clase de .NET Framework y especifica opcionalmente la asignación o configuración adicional usando anotaciones de datos o la API fluida.</span><span class="sxs-lookup"><span data-stu-id="6f663-108">In both cases, the developer defines a model by coding .NET Framework class definitions, and then optionally specifies additional mapping or configuration by using Data Annotations or the fluent API.</span></span>  
  
 <span data-ttu-id="6f663-109">Para más información, vea [Creación de un modelo](/ef/ef6/modeling/).</span><span class="sxs-lookup"><span data-stu-id="6f663-109">For more information, see [Creating a Model](/ef/ef6/modeling/).</span></span>  
  
 <span data-ttu-id="6f663-110">También puede usar el generador de EDM, que se incluye con el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f663-110">You can also use the EDM Generator, which is included with the .NET Framework.</span></span> <span data-ttu-id="6f663-111">EdmGen.exe genera los archivos .csdl, .ssdl y .msl a partir de un origen de datos existente.</span><span class="sxs-lookup"><span data-stu-id="6f663-111">The EdmGen.exe generates the .csdl, .ssdl, and .msl files from an existing data source.</span></span> <span data-ttu-id="6f663-112">También puede crear manualmente el contenido del modelo y la asignación.</span><span class="sxs-lookup"><span data-stu-id="6f663-112">You can also manually create the model and mapping content.</span></span> <span data-ttu-id="6f663-113">Para obtener más información, vea [generador de EDM (EdmGen.exe)](edm-generator-edmgen-exe.md).</span><span class="sxs-lookup"><span data-stu-id="6f663-113">For more information, see [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md).</span></span>

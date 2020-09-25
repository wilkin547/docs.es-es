---
title: Modelado y asignación
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 5592ce5301216c8c3e74231480997d9e44d71a7d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197760"
---
# <a name="modeling-and-mapping"></a><span data-ttu-id="3ea05-102">Modelado y asignación</span><span class="sxs-lookup"><span data-stu-id="3ea05-102">Modeling and Mapping</span></span>

<span data-ttu-id="3ea05-103">En el Entity Framework, puede definir el modelo conceptual, el modelo de almacenamiento y la asignación entre los dos de la forma que mejor se adapte a su aplicación.</span><span class="sxs-lookup"><span data-stu-id="3ea05-103">In the Entity Framework, you can define the conceptual model, storage model, and the mapping between the two in the way that best suits your application.</span></span> <span data-ttu-id="3ea05-104">Las herramientas de Entity Data Model de Visual Studio le permiten crear un. [archivo edmx](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) de una base de datos o un modelo gráfico y, a continuación, actualice el archivo cuando cambie la base de datos o el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ea05-104">The Entity Data Model Tools in Visual Studio allow you to create an .[edmx file](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) from a database or a graphical model and then update that file when either the database or model changes.</span></span>  
  
 <span data-ttu-id="3ea05-105">A partir de Entity Framework 4.0.1 también puede crear un modelo mediante programación usando desarrollo Code First.</span><span class="sxs-lookup"><span data-stu-id="3ea05-105">Starting with the Entity Framework 4.1 you can also create a model programmatically using Code First development.</span></span> <span data-ttu-id="3ea05-106">Hay dos escenarios diferentes para el desarrollo Code First.</span><span class="sxs-lookup"><span data-stu-id="3ea05-106">There are two different scenarios for Code First development.</span></span> <span data-ttu-id="3ea05-107">En ambos casos, el desarrollador define un modelo codificando definiciones de clase de .NET Framework y especifica opcionalmente la asignación o configuración adicional usando anotaciones de datos o la API fluida.</span><span class="sxs-lookup"><span data-stu-id="3ea05-107">In both cases, the developer defines a model by coding .NET Framework class definitions, and then optionally specifies additional mapping or configuration by using Data Annotations or the fluent API.</span></span>  
  
 <span data-ttu-id="3ea05-108">Para obtener más información, vea [crear un modelo](/ef/ef6/modeling/).</span><span class="sxs-lookup"><span data-stu-id="3ea05-108">For more information, see [Creating a Model](/ef/ef6/modeling/).</span></span>  
  
 <span data-ttu-id="3ea05-109">También puede usar el generador de EDM, que se incluye con el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3ea05-109">You can also use the EDM Generator, which is included with the .NET Framework.</span></span> <span data-ttu-id="3ea05-110">EdmGen.exe genera los archivos .csdl, .ssdl y .msl a partir de un origen de datos existente.</span><span class="sxs-lookup"><span data-stu-id="3ea05-110">The EdmGen.exe generates the .csdl, .ssdl, and .msl files from an existing data source.</span></span> <span data-ttu-id="3ea05-111">También puede crear manualmente el contenido del modelo y la asignación.</span><span class="sxs-lookup"><span data-stu-id="3ea05-111">You can also manually create the model and mapping content.</span></span> <span data-ttu-id="3ea05-112">Para obtener más información, vea [generador de EDM (EdmGen.exe)](edm-generator-edmgen-exe.md).</span><span class="sxs-lookup"><span data-stu-id="3ea05-112">For more information, see [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md).</span></span>

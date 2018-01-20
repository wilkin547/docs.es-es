---
title: "Modelado y asignación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
caps.latest.revision: "7"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0782d75aa44557ef87f1d59757b0d60873d8a949
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="modeling-and-mapping"></a><span data-ttu-id="89f9e-102">Modelado y asignación</span><span class="sxs-lookup"><span data-stu-id="89f9e-102">Modeling and Mapping</span></span>
<span data-ttu-id="89f9e-103">En [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], puede definir el modelo conceptual, el modelo de almacenamiento y la asignación entre los dos de la forma que mejor convenga a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="89f9e-103">In the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you can define the conceptual model, storage model, and the mapping between the two in the way that best suits your application.</span></span> <span data-ttu-id="89f9e-104">Las herramientas de Entity Data Model en [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] le permiten crear una.[ archivo edmx](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4) desde una base de datos o una modelo gráfico y, a continuación, actualizar ese archivo cuando cambia la base de datos o el modelo.</span><span class="sxs-lookup"><span data-stu-id="89f9e-104">The Entity Data Model Tools in [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] allow you to create an .[edmx file](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4) from a database or a graphical model and then update that file when either the database or model changes.</span></span>  
  
 <span data-ttu-id="89f9e-105">A partir de Entity Framework 4.0.1 también puede crear un modelo mediante programación usando desarrollo Code First.</span><span class="sxs-lookup"><span data-stu-id="89f9e-105">Starting with the Entity Framework 4.1 you can also create a model programmatically using Code First development.</span></span> <span data-ttu-id="89f9e-106">Hay dos escenarios diferentes para el desarrollo Code First.</span><span class="sxs-lookup"><span data-stu-id="89f9e-106">There are two different scenarios for Code First development.</span></span> <span data-ttu-id="89f9e-107">En ambos casos, el desarrollador define un modelo codificando definiciones de clase de .NET Framework y especifica opcionalmente la asignación o configuración adicional usando anotaciones de datos o la API fluida.</span><span class="sxs-lookup"><span data-stu-id="89f9e-107">In both cases, the developer defines a model by coding .NET Framework class definitions, and then optionally specifies additional mapping or configuration by using Data Annotations or the fluent API.</span></span>  
  
 <span data-ttu-id="89f9e-108">Para obtener más información, consulte [crear y asignar un modelo Conceptual](http://go.microsoft.com/fwlink/?LinkId=235016).</span><span class="sxs-lookup"><span data-stu-id="89f9e-108">For more information, see [Creating and Mapping a Conceptual Model](http://go.microsoft.com/fwlink/?LinkId=235016).</span></span>  
  
 <span data-ttu-id="89f9e-109">También puede usar el generador de EDM, que se incluye con la [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89f9e-109">You can also use the EDM Generator, which is included with the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="89f9e-110">EdmGen.exe genera los archivos .csdl, .ssdl y .msl a partir de un origen de datos existente.</span><span class="sxs-lookup"><span data-stu-id="89f9e-110">The EdmGen.exe generates the .csdl, .ssdl, and .msl files from an existing data source.</span></span> <span data-ttu-id="89f9e-111">También puede crear manualmente el contenido del modelo y la asignación.</span><span class="sxs-lookup"><span data-stu-id="89f9e-111">You can also manually create the model and mapping content.</span></span> <span data-ttu-id="89f9e-112">Para obtener más información, consulte [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).</span><span class="sxs-lookup"><span data-stu-id="89f9e-112">For more information, see [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).</span></span>

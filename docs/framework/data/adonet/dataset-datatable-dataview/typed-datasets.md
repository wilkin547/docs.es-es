---
title: Objetos DataSet con tipo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a68d4a10b01285a7e1b33238409351ca04d0aeb4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="typed-datasets"></a><span data-ttu-id="6d5b5-102">Objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="6d5b5-102">Typed DataSets</span></span>
<span data-ttu-id="6d5b5-103">Además del acceso en tiempo de ejecución a valores mediante variables débilmente tipadas, el <xref:System.Data.DataSet> proporciona acceso a los datos mediante una metáfora fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="6d5b5-103">Along with late bound access to values through weakly typed variables, the <xref:System.Data.DataSet> provides access to data through a strongly typed metaphor.</span></span> <span data-ttu-id="6d5b5-104">Tablas y columnas que forman parte de la **conjunto de datos** puede tener acceso mediante nombres descriptivos y variables fuertemente tipadas.</span><span class="sxs-lookup"><span data-stu-id="6d5b5-104">Tables and columns that are part of the **DataSet** can be accessed using user-friendly names and strongly typed variables.</span></span>  
  
 <span data-ttu-id="6d5b5-105">Un tipo **conjunto de datos** es una clase que deriva de un **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="6d5b5-105">A typed **DataSet** is a class that derives from a **DataSet**.</span></span> <span data-ttu-id="6d5b5-106">Como tal, hereda todos los métodos, eventos y propiedades de un **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="6d5b5-106">As such, it inherits all the methods, events, and properties of a **DataSet**.</span></span> <span data-ttu-id="6d5b5-107">Además, un tipo **conjunto de datos** proporciona métodos fuertemente tipados, eventos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="6d5b5-107">Additionally, a typed **DataSet** provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="6d5b5-108">Esto significa que se puede tener acceso a tablas y columnas por su nombre, en lugar de utilizar métodos de una colección.</span><span class="sxs-lookup"><span data-stu-id="6d5b5-108">This means you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="6d5b5-109">Además de la mayor legibilidad del código, un tipo **conjunto de datos** también permite que el código de Visual Studio .NET complete automáticamente las líneas mientras escribe el editor.</span><span class="sxs-lookup"><span data-stu-id="6d5b5-109">Aside from the improved readability of the code, a typed **DataSet** also allows the Visual Studio .NET code editor to automatically complete lines as you type.</span></span>  
  
 <span data-ttu-id="6d5b5-110">Además, el fuertemente tipado **conjunto de datos** proporciona acceso a los valores del tipo correcto en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="6d5b5-110">Additionally, the strongly typed **DataSet** provides access to values as the correct type at compile time.</span></span> <span data-ttu-id="6d5b5-111">Con un fuertemente tipado **conjunto de datos**, errores de falta de coincidencia de tipos se interceptan cuando el código se compila en lugar de en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6d5b5-111">With a strongly typed **DataSet**, type mismatch errors are caught when the code is compiled rather than at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d5b5-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6d5b5-112">In This Section</span></span>  
 [<span data-ttu-id="6d5b5-113">Generación de conjuntos de datos fuertemente tipados</span><span class="sxs-lookup"><span data-stu-id="6d5b5-113">Generating Strongly Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 <span data-ttu-id="6d5b5-114">Describe cómo crear y usar un fuertemente tipado **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="6d5b5-114">Describes how to create and use a strongly typed **DataSet**.</span></span>  
  
 [<span data-ttu-id="6d5b5-115">Anotación de conjuntos de datos con tipo</span><span class="sxs-lookup"><span data-stu-id="6d5b5-115">Annotating Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 <span data-ttu-id="6d5b5-116">Describe cómo se anota el esquema de lenguaje (XSD) de definición de esquema XML utilizado para generar un fuertemente tipado **conjunto de datos**fin de asignar **conjunto de datos** nombres descriptivos de elementos sin modificar el esquema subyacente.</span><span class="sxs-lookup"><span data-stu-id="6d5b5-116">Describes how to annotate the XML Schema definition language (XSD) schema used to generate a strongly typed **DataSet**, to give **DataSet** elements friendly names without altering the underlying schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d5b5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d5b5-117">See Also</span></span>  
 [<span data-ttu-id="6d5b5-118">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="6d5b5-118">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="6d5b5-119">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="6d5b5-119">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

---
title: Objetos DataSet con tipo
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 7c8111e0e62a57b6745a5ea0387fc65a05839df8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785842"
---
# <a name="typed-datasets"></a><span data-ttu-id="631f5-102">Objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="631f5-102">Typed DataSets</span></span>
<span data-ttu-id="631f5-103">Además del acceso en tiempo de ejecución a valores mediante variables débilmente tipadas, el <xref:System.Data.DataSet> proporciona acceso a los datos mediante una metáfora fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="631f5-103">Along with late bound access to values through weakly typed variables, the <xref:System.Data.DataSet> provides access to data through a strongly typed metaphor.</span></span> <span data-ttu-id="631f5-104">Se puede tener acceso a las tablas y columnas que forman parte del **conjunto** de elementos mediante nombres descriptivos y variables fuertemente tipadas.</span><span class="sxs-lookup"><span data-stu-id="631f5-104">Tables and columns that are part of the **DataSet** can be accessed using user-friendly names and strongly typed variables.</span></span>  
  
 <span data-ttu-id="631f5-105">Un **DataSet** con tipo es una clase que se deriva de un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="631f5-105">A typed **DataSet** is a class that derives from a **DataSet**.</span></span> <span data-ttu-id="631f5-106">Como tal, hereda todos los métodos, eventos y propiedades de un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="631f5-106">As such, it inherits all the methods, events, and properties of a **DataSet**.</span></span> <span data-ttu-id="631f5-107">Además, un conjunto de un **DataSet** con tipo proporciona métodos, eventos y propiedades fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="631f5-107">Additionally, a typed **DataSet** provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="631f5-108">Esto significa que se puede tener acceso a tablas y columnas por su nombre, en lugar de utilizar métodos de una colección.</span><span class="sxs-lookup"><span data-stu-id="631f5-108">This means you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="631f5-109">Aparte de la mejora de la legibilidad del código, un **conjunto** de elementos de tipo también permite que el editor de código de Visual Studio .net complete automáticamente las líneas a medida que escribe.</span><span class="sxs-lookup"><span data-stu-id="631f5-109">Aside from the improved readability of the code, a typed **DataSet** also allows the Visual Studio .NET code editor to automatically complete lines as you type.</span></span>  
  
 <span data-ttu-id="631f5-110">Además, el **conjunto de DataSet** fuertemente tipado proporciona acceso a los valores como el tipo correcto en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="631f5-110">Additionally, the strongly typed **DataSet** provides access to values as the correct type at compile time.</span></span> <span data-ttu-id="631f5-111">Con un **conjunto**de tipos fuertemente tipado, los errores de coincidencia de tipos se detectan cuando se compila el código en lugar de en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="631f5-111">With a strongly typed **DataSet**, type mismatch errors are caught when the code is compiled rather than at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="631f5-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="631f5-112">In This Section</span></span>  
 [<span data-ttu-id="631f5-113">Generación de conjuntos de datos fuertemente tipados</span><span class="sxs-lookup"><span data-stu-id="631f5-113">Generating Strongly Typed DataSets</span></span>](generating-strongly-typed-datasets.md)  
 <span data-ttu-id="631f5-114">Describe cómo crear y usar un **conjunto de DataSet**fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="631f5-114">Describes how to create and use a strongly typed **DataSet**.</span></span>  
  
 [<span data-ttu-id="631f5-115">Anotación de conjuntos de datos con tipo</span><span class="sxs-lookup"><span data-stu-id="631f5-115">Annotating Typed DataSets</span></span>](annotating-typed-datasets.md)  
 <span data-ttu-id="631f5-116">Describe cómo anotar el esquema del lenguaje de definición de esquemas XML (XSD) utilizado para generar un **DataSet**fuertemente tipado, a fin de proporcionar nombres descriptivos a los elementos del **conjunto** de elementos sin modificar el esquema subyacente.</span><span class="sxs-lookup"><span data-stu-id="631f5-116">Describes how to annotate the XML Schema definition language (XSD) schema used to generate a strongly typed **DataSet**, to give **DataSet** elements friendly names without altering the underlying schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="631f5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="631f5-117">See also</span></span>

- [<span data-ttu-id="631f5-118">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="631f5-118">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="631f5-119">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="631f5-119">ADO.NET Overview</span></span>](../ado-net-overview.md)

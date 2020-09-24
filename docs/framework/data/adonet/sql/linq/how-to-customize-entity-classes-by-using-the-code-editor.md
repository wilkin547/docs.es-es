---
title: Procedimiento para personalizar clases de entidades con el editor de código
ms.date: 03/30/2017
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
ms.openlocfilehash: 5e61acc9de1ef2f00d5e81a3c3080a9dc46f074d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147702"
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="2bb0d-102">Procedimiento para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="2bb0d-102">How to: Customize Entity Classes by Using the Code Editor</span></span>

<span data-ttu-id="2bb0d-103">Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para crear o personalizar las clases de entidad.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-103">Developers using Visual Studio can use the Object Relational Designer to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="2bb0d-104">También puede usar el editor de código de Visual Studio para escribir su propio código de asignación o para personalizar el código que ya se ha generado.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-104">You can also use the Visual Studio code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="2bb0d-105">Para obtener más información, consulte [asignación basada en atributos](attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="2bb0d-105">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="2bb0d-106">Los temas de esta sección describen cómo personalizar un modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="2bb0d-107">Procedimiento para especificar nombres de base de datos</span><span class="sxs-lookup"><span data-stu-id="2bb0d-107">How to: Specify Database Names</span></span>](how-to-specify-database-names.md)  
 <span data-ttu-id="2bb0d-108">Describe cómo usar <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="2bb0d-109">Procedimiento para representar tablas como clases</span><span class="sxs-lookup"><span data-stu-id="2bb0d-109">How to: Represent Tables as Classes</span></span>](how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="2bb0d-110">Describe cómo usar <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="2bb0d-111">Procedimiento para representar columnas como miembros de clase</span><span class="sxs-lookup"><span data-stu-id="2bb0d-111">How to: Represent Columns as Class Members</span></span>](how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="2bb0d-112">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="2bb0d-113">Procedimiento para representar claves principales</span><span class="sxs-lookup"><span data-stu-id="2bb0d-113">How to: Represent Primary Keys</span></span>](how-to-represent-primary-keys.md)  
 <span data-ttu-id="2bb0d-114">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="2bb0d-115">Procedimiento para asignar relaciones de base de datos</span><span class="sxs-lookup"><span data-stu-id="2bb0d-115">How to: Map Database Relationships</span></span>](how-to-map-database-relationships.md)  
 <span data-ttu-id="2bb0d-116">Proporciona ejemplos de cómo se utiliza el atributo <xref:System.Data.Linq.Mapping.AssociationAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="2bb0d-117">Procedimiento para representar columnas como columnas generadas por la base de datos</span><span class="sxs-lookup"><span data-stu-id="2bb0d-117">How to: Represent Columns as Database-Generated</span></span>](how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="2bb0d-118">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="2bb0d-119">Procedimiento para representar columnas como columnas de marcas de tiempo o de versión</span><span class="sxs-lookup"><span data-stu-id="2bb0d-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="2bb0d-120">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="2bb0d-121">Procedimiento para especificar tipos de datos de base de datos</span><span class="sxs-lookup"><span data-stu-id="2bb0d-121">How to: Specify Database Data Types</span></span>](how-to-specify-database-data-types.md)  
 <span data-ttu-id="2bb0d-122">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="2bb0d-123">Procedimiento para representar columnas calculadas</span><span class="sxs-lookup"><span data-stu-id="2bb0d-123">How to: Represent Computed Columns</span></span>](how-to-represent-computed-columns.md)  
 <span data-ttu-id="2bb0d-124">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="2bb0d-125">Procedimiento para especificar campos de almacenamiento privado</span><span class="sxs-lookup"><span data-stu-id="2bb0d-125">How to: Specify Private Storage Fields</span></span>](how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="2bb0d-126">Describe cómo usar <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="2bb0d-127">Procedimiento para representar columnas como columnas que permiten valores null</span><span class="sxs-lookup"><span data-stu-id="2bb0d-127">How to: Represent Columns as Allowing Null Values</span></span>](how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="2bb0d-128">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="2bb0d-129">Procedimiento para asignar jerarquías de herencia</span><span class="sxs-lookup"><span data-stu-id="2bb0d-129">How to: Map Inheritance Hierarchies</span></span>](how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="2bb0d-130">Describe las asignaciones necesarias para especificar una jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="2bb0d-131">Procedimiento para especificar comprobaciones con conflictos de simultaneidad</span><span class="sxs-lookup"><span data-stu-id="2bb0d-131">How to: Specify Concurrency-Conflict Checking</span></span>](how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="2bb0d-132">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="2bb0d-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bb0d-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bb0d-133">See also</span></span>

- [<span data-ttu-id="2bb0d-134">SqlMetal.exe (Herramienta de generación de código)</span><span class="sxs-lookup"><span data-stu-id="2bb0d-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)

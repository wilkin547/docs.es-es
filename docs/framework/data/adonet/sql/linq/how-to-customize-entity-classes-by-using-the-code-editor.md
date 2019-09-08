---
title: Procedimiento para personalizar clases de entidades con el editor de código
ms.date: 03/30/2017
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
ms.openlocfilehash: 578e0cbd1f6990a5d41007ad31f4c1c938cd3ebe
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793800"
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="28052-102">Procedimiento para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="28052-102">How to: Customize Entity Classes by Using the Code Editor</span></span>
<span data-ttu-id="28052-103">Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para crear o personalizar las clases de entidad.</span><span class="sxs-lookup"><span data-stu-id="28052-103">Developers using Visual Studio can use the Object Relational Designer to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="28052-104">También puede usar el editor de código de Visual Studio para escribir su propio código de asignación o para personalizar el código que ya se ha generado.</span><span class="sxs-lookup"><span data-stu-id="28052-104">You can also use the Visual Studio code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="28052-105">Para obtener más información, consulte [asignación basada en atributos](attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="28052-105">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="28052-106">Los temas de esta sección describen cómo personalizar un modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="28052-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="28052-107">Procedimientos: Especificar nombres de base de datos</span><span class="sxs-lookup"><span data-stu-id="28052-107">How to: Specify Database Names</span></span>](how-to-specify-database-names.md)  
 <span data-ttu-id="28052-108">Describe cómo usar <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="28052-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="28052-109">Procedimientos: Representar tablas como clases</span><span class="sxs-lookup"><span data-stu-id="28052-109">How to: Represent Tables as Classes</span></span>](how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="28052-110">Describe cómo usar <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="28052-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="28052-111">Cómo: Representar columnas como miembros de clase</span><span class="sxs-lookup"><span data-stu-id="28052-111">How to: Represent Columns as Class Members</span></span>](how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="28052-112">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="28052-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="28052-113">Cómo: Representar claves principales</span><span class="sxs-lookup"><span data-stu-id="28052-113">How to: Represent Primary Keys</span></span>](how-to-represent-primary-keys.md)  
 <span data-ttu-id="28052-114">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="28052-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="28052-115">Cómo: Asignar relaciones de base de datos</span><span class="sxs-lookup"><span data-stu-id="28052-115">How to: Map Database Relationships</span></span>](how-to-map-database-relationships.md)  
 <span data-ttu-id="28052-116">Proporciona ejemplos de cómo se utiliza el atributo <xref:System.Data.Linq.Mapping.AssociationAttribute>.</span><span class="sxs-lookup"><span data-stu-id="28052-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="28052-117">Cómo: Representar columnas como generadas por la base de datos</span><span class="sxs-lookup"><span data-stu-id="28052-117">How to: Represent Columns as Database-Generated</span></span>](how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="28052-118">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="28052-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="28052-119">Cómo: Representar columnas como marcas de tiempo o columnas de versión</span><span class="sxs-lookup"><span data-stu-id="28052-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="28052-120">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="28052-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="28052-121">Cómo: Especificar tipos de datos de base de datos</span><span class="sxs-lookup"><span data-stu-id="28052-121">How to: Specify Database Data Types</span></span>](how-to-specify-database-data-types.md)  
 <span data-ttu-id="28052-122">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span><span class="sxs-lookup"><span data-stu-id="28052-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="28052-123">Cómo: Representar columnas calculadas</span><span class="sxs-lookup"><span data-stu-id="28052-123">How to: Represent Computed Columns</span></span>](how-to-represent-computed-columns.md)  
 <span data-ttu-id="28052-124">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="28052-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="28052-125">Cómo: Especificar campos de almacenamiento privado</span><span class="sxs-lookup"><span data-stu-id="28052-125">How to: Specify Private Storage Fields</span></span>](how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="28052-126">Describe cómo usar <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="28052-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="28052-127">Procedimientos: Representar columnas como permitir valores NULL</span><span class="sxs-lookup"><span data-stu-id="28052-127">How to: Represent Columns as Allowing Null Values</span></span>](how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="28052-128">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="28052-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="28052-129">Procedimientos: Asignar jerarquías de herencia</span><span class="sxs-lookup"><span data-stu-id="28052-129">How to: Map Inheritance Hierarchies</span></span>](how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="28052-130">Describe las asignaciones necesarias para especificar una jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="28052-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="28052-131">Procedimientos: Especificar comprobación de conflictos de simultaneidad</span><span class="sxs-lookup"><span data-stu-id="28052-131">How to: Specify Concurrency-Conflict Checking</span></span>](how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="28052-132">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="28052-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28052-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="28052-133">See also</span></span>

- [<span data-ttu-id="28052-134">SqlMetal.exe (Herramienta de generación de código)</span><span class="sxs-lookup"><span data-stu-id="28052-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)

---
title: 'Cómo: Personalizar clases de entidades con el editor de código'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: f57b07d03297347561b6b2e2634038aa1f29bc40
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="6ccd8-102">Cómo: Personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="6ccd8-102">How to: Customize Entity Classes by Using the Code Editor</span></span>
<span data-ttu-id="6ccd8-103">Los desarrolladores que utilizan Visual Studio pueden usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para crear o personalizar las clases de entidad.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-103">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="6ccd8-104">También puede usar el editor de código de Visual Studio para escribir su propio código de asignación o para personalizar código que ya se ha generado.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-104">You can also use the Visual Studio code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="6ccd8-105">Para obtener más información, consulte [asignación basada en el atributo](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="6ccd8-105">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="6ccd8-106">Los temas de esta sección describen cómo personalizar un modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="6ccd8-107">Especificación de nombres de base de datos</span><span class="sxs-lookup"><span data-stu-id="6ccd8-107">How to: Specify Database Names</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-names.md)  
 <span data-ttu-id="6ccd8-108">Describe cómo usar <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="6ccd8-109">Representación de tablas como clases</span><span class="sxs-lookup"><span data-stu-id="6ccd8-109">How to: Represent Tables as Classes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="6ccd8-110">Describe cómo usar <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="6ccd8-111">Representación de columnas como miembros de clase</span><span class="sxs-lookup"><span data-stu-id="6ccd8-111">How to: Represent Columns as Class Members</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="6ccd8-112">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="6ccd8-113">Representación de claves principales</span><span class="sxs-lookup"><span data-stu-id="6ccd8-113">How to: Represent Primary Keys</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-primary-keys.md)  
 <span data-ttu-id="6ccd8-114">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="6ccd8-115">Asignación de relaciones de base de datos</span><span class="sxs-lookup"><span data-stu-id="6ccd8-115">How to: Map Database Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-database-relationships.md)  
 <span data-ttu-id="6ccd8-116">Proporciona ejemplos de cómo se utiliza el atributo <xref:System.Data.Linq.Mapping.AssociationAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="6ccd8-117">Representación de columnas como columnas generadas por la base de datos</span><span class="sxs-lookup"><span data-stu-id="6ccd8-117">How to: Represent Columns as Database-Generated</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="6ccd8-118">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="6ccd8-119">Representación de columnas como marcas de tiempo o columnas de versión</span><span class="sxs-lookup"><span data-stu-id="6ccd8-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="6ccd8-120">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="6ccd8-121">Definición de tipos de datos de base de datos</span><span class="sxs-lookup"><span data-stu-id="6ccd8-121">How to: Specify Database Data Types</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-data-types.md)  
 <span data-ttu-id="6ccd8-122">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="6ccd8-123">Representación de columnas calculadas</span><span class="sxs-lookup"><span data-stu-id="6ccd8-123">How to: Represent Computed Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-computed-columns.md)  
 <span data-ttu-id="6ccd8-124">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="6ccd8-125">Definición de campos de almacenamiento privado</span><span class="sxs-lookup"><span data-stu-id="6ccd8-125">How to: Specify Private Storage Fields</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="6ccd8-126">Describe cómo usar <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="6ccd8-127">Representación de columnas como columnas que permiten valores null</span><span class="sxs-lookup"><span data-stu-id="6ccd8-127">How to: Represent Columns as Allowing Null Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="6ccd8-128">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="6ccd8-129">Asignación de jerarquías de herencia</span><span class="sxs-lookup"><span data-stu-id="6ccd8-129">How to: Map Inheritance Hierarchies</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="6ccd8-130">Describe las asignaciones necesarias para especificar una jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="6ccd8-131">Definición de comprobaciones con conflictos de simultaneidad</span><span class="sxs-lookup"><span data-stu-id="6ccd8-131">How to: Specify Concurrency-Conflict Checking</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="6ccd8-132">Describe cómo usar <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ccd8-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ccd8-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ccd8-133">See Also</span></span>  
 [<span data-ttu-id="6ccd8-134">SqlMetal.exe (Herramienta de generación de código)</span><span class="sxs-lookup"><span data-stu-id="6ccd8-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)

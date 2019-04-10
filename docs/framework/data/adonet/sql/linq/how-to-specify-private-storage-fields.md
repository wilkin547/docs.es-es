---
title: Filtrar para especificar campos de almacenamiento privado
ms.date: 03/30/2017
ms.assetid: 5a40e816-cc6e-43a0-b32a-9caaa0ab6912
ms.openlocfilehash: 843b7ae8dbddb76e0e5fa33d3594a5655dbf1a37
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59302457"
---
# <a name="how-to-specify-private-storage-fields"></a><span data-ttu-id="d6c9c-102">Filtrar para especificar campos de almacenamiento privado</span><span class="sxs-lookup"><span data-stu-id="d6c9c-102">How to: Specify Private Storage Fields</span></span>
<span data-ttu-id="d6c9c-103">Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> propiedad en el <xref:System.Data.Linq.Mapping.DataAttribute> atributo para designar el nombre de un campo de almacenamiento subyacente.</span><span class="sxs-lookup"><span data-stu-id="d6c9c-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property on the <xref:System.Data.Linq.Mapping.DataAttribute> attribute to designate the name of an underlying storage field.</span></span>  
  
 <span data-ttu-id="d6c9c-104">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="d6c9c-104">For code examples, see <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-an-underlying-storage-field"></a><span data-ttu-id="d6c9c-105">Para especificar el nombre de un campo de almacenamiento subyacente</span><span class="sxs-lookup"><span data-stu-id="d6c9c-105">To specify the name of an underlying storage field</span></span>  
  
1. <span data-ttu-id="d6c9c-106">Agregue la propiedad <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d6c9c-106">Add the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="d6c9c-107">Asigne el nombre del campo como valor de la propiedad <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="d6c9c-107">Assign the name of the field as the value of the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c9c-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6c9c-108">See also</span></span>

- [<span data-ttu-id="d6c9c-109">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d6c9c-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="d6c9c-110">Filtrar para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="d6c9c-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)

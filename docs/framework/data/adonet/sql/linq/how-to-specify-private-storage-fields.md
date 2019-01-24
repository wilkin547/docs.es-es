---
title: Procedimiento Especificar campos de almacenamiento privado
ms.date: 03/30/2017
ms.assetid: 5a40e816-cc6e-43a0-b32a-9caaa0ab6912
ms.openlocfilehash: d127de889fdaa2eb2d03a96dae5aa3d856efe32a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549605"
---
# <a name="how-to-specify-private-storage-fields"></a><span data-ttu-id="f448e-102">Procedimiento Especificar campos de almacenamiento privado</span><span class="sxs-lookup"><span data-stu-id="f448e-102">How to: Specify Private Storage Fields</span></span>
<span data-ttu-id="f448e-103">Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> propiedad en el <xref:System.Data.Linq.Mapping.DataAttribute> atributo para designar el nombre de un campo de almacenamiento subyacente.</span><span class="sxs-lookup"><span data-stu-id="f448e-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property on the <xref:System.Data.Linq.Mapping.DataAttribute> attribute to designate the name of an underlying storage field.</span></span>  
  
 <span data-ttu-id="f448e-104">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="f448e-104">For code examples, see <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-an-underlying-storage-field"></a><span data-ttu-id="f448e-105">Para especificar el nombre de un campo de almacenamiento subyacente</span><span class="sxs-lookup"><span data-stu-id="f448e-105">To specify the name of an underlying storage field</span></span>  
  
1.  <span data-ttu-id="f448e-106">Agregue la propiedad <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f448e-106">Add the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="f448e-107">Asigne el nombre del campo como valor de la propiedad <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="f448e-107">Assign the name of the field as the value of the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f448e-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="f448e-108">See also</span></span>
- [<span data-ttu-id="f448e-109">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f448e-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="f448e-110">Cómo: Personalizar las clases de entidad mediante el Editor de código</span><span class="sxs-lookup"><span data-stu-id="f448e-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)

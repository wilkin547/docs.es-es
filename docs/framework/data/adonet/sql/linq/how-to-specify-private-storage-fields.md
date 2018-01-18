---
title: "Cómo: Especificar campos de almacenamiento privado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a40e816-cc6e-43a0-b32a-9caaa0ab6912
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bdb25f21a94ac6eb521e08688e33903e8891caf4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-specify-private-storage-fields"></a><span data-ttu-id="04f31-102">Cómo: Especificar campos de almacenamiento privado</span><span class="sxs-lookup"><span data-stu-id="04f31-102">How to: Specify Private Storage Fields</span></span>
<span data-ttu-id="04f31-103">Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> propiedad en el <xref:System.Data.Linq.Mapping.DataAttribute> atributo para designar el nombre de un campo de almacenamiento subyacente.</span><span class="sxs-lookup"><span data-stu-id="04f31-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property on the <xref:System.Data.Linq.Mapping.DataAttribute> attribute to designate the name of an underlying storage field.</span></span>  
  
 <span data-ttu-id="04f31-104">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="04f31-104">For code examples, see <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-an-underlying-storage-field"></a><span data-ttu-id="04f31-105">Para especificar el nombre de un campo de almacenamiento subyacente</span><span class="sxs-lookup"><span data-stu-id="04f31-105">To specify the name of an underlying storage field</span></span>  
  
1.  <span data-ttu-id="04f31-106">Agregue la propiedad <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="04f31-106">Add the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="04f31-107">Asigne el nombre del campo como valor de la propiedad <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="04f31-107">Assign the name of the field as the value of the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f31-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="04f31-108">See Also</span></span>  
 [<span data-ttu-id="04f31-109">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="04f31-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="04f31-110">Personalización de clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="04f31-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)

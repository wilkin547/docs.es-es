---
title: Procedimiento para especificar en qué miembros se comprueban los conflictos de simultaneidad
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
ms.openlocfilehash: 9a1b4ab2dc28c569473eddbf50b96d10298d8d3c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59310439"
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a><span data-ttu-id="b952b-102">Procedimiento para especificar en qué miembros se comprueban los conflictos de simultaneidad</span><span class="sxs-lookup"><span data-stu-id="b952b-102">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>
<span data-ttu-id="b952b-103">Aplicar una de las tres enumeraciones a la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> propiedad en un <xref:System.Data.Linq.Mapping.ColumnAttribute> comprueba el atributo para especificar qué miembros estarán incluidos en la actualización para la detección de conflictos de simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="b952b-103">Apply one of three enums to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify which members are to be included in update checks for the detection of optimistic concurrency conflicts.</span></span>  
  
 <span data-ttu-id="b952b-104">La propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> (asignada en tiempo de diseño) se utiliza junto con las características de simultaneidad en tiempo de ejecución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b952b-104">The <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property (mapped at design time) is used together with run-time concurrency features in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="b952b-105">Para obtener más información, consulte [simultaneidad optimista: Información general sobre](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b952b-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b952b-106">Los valores de miembro originales se comparan con el estado de la base de datos actual siempre y cuando ningún miembro se designe como `IsVersion=true`.</span><span class="sxs-lookup"><span data-stu-id="b952b-106">Original member values are compared with the current database state as long as no member is designated as `IsVersion=true`.</span></span> <span data-ttu-id="b952b-107">Para obtener más información, consulta <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="b952b-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 <span data-ttu-id="b952b-108">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="b952b-108">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
### <a name="to-always-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="b952b-109">Para usar siempre este miembro para detectar los conflictos</span><span class="sxs-lookup"><span data-stu-id="b952b-109">To always use this member for detecting conflicts</span></span>  
  
1. <span data-ttu-id="b952b-110">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b952b-110">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="b952b-111">Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> en `Always`.</span><span class="sxs-lookup"><span data-stu-id="b952b-111">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Always`.</span></span>  
  
### <a name="to-never-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="b952b-112">Para no usar nunca este miembro para detectar los conflictos</span><span class="sxs-lookup"><span data-stu-id="b952b-112">To never use this member for detecting conflicts</span></span>  
  
1. <span data-ttu-id="b952b-113">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b952b-113">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="b952b-114">Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> en `Never`.</span><span class="sxs-lookup"><span data-stu-id="b952b-114">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Never`.</span></span>  
  
### <a name="to-use-this-member-for-detecting-conflicts-only-when-the-application-has-changed-the-value-of-the-member"></a><span data-ttu-id="b952b-115">Para utilizar este miembro para detectar conflictos sólo cuando la aplicación cambia el valor del miembro</span><span class="sxs-lookup"><span data-stu-id="b952b-115">To use this member for detecting conflicts only when the application has changed the value of the member</span></span>  
  
1. <span data-ttu-id="b952b-116">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b952b-116">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="b952b-117">Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> en `WhenChanged`.</span><span class="sxs-lookup"><span data-stu-id="b952b-117">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `WhenChanged`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b952b-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b952b-118">Example</span></span>  
 <span data-ttu-id="b952b-119">En el ejemplo siguiente se especifica que nunca deberían probarse los objetos `HomePage` durante las comprobaciones de actualización.</span><span class="sxs-lookup"><span data-stu-id="b952b-119">The following example specifies that `HomePage` objects should never be tested during update checks.</span></span> <span data-ttu-id="b952b-120">Para obtener más información, consulta <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="b952b-120">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b952b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b952b-121">See also</span></span>

- [<span data-ttu-id="b952b-122">Cómo: Administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="b952b-122">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="b952b-123">Realización y envío de cambios de datos</span><span class="sxs-lookup"><span data-stu-id="b952b-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)

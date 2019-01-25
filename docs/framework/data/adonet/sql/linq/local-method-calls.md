---
title: Llamadas a métodos locales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
ms.openlocfilehash: 249ed8425f175b80cb55289c2a7fe68742d8389c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655730"
---
# <a name="local-method-calls"></a><span data-ttu-id="debe4-102">Llamadas a métodos locales</span><span class="sxs-lookup"><span data-stu-id="debe4-102">Local Method Calls</span></span>
<span data-ttu-id="debe4-103">Las llamadas a métodos locales son las que se ejecutan dentro del modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="debe4-103">A local method call is one that is executed within the object model.</span></span> <span data-ttu-id="debe4-104">Las llamadas a métodos remotos son la que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte a SQL y después transmite al motor de base de datos para su ejecución.</span><span class="sxs-lookup"><span data-stu-id="debe4-104">A remote method call is one that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates to SQL and transmits to the database engine for execution.</span></span> <span data-ttu-id="debe4-105">Llamadas a métodos locales son necesarios cuando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no se puede convertir una llamada a SQL.</span><span class="sxs-lookup"><span data-stu-id="debe4-105">Local method calls are needed when [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot translate the call into SQL.</span></span> <span data-ttu-id="debe4-106">De lo contrario, se produce una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="debe4-106">Otherwise, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="debe4-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="debe4-107">Example 1</span></span>  
 <span data-ttu-id="debe4-108">En el ejemplo siguiente, se asigna una clase `Order` a la tabla Orders de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="debe4-108">In the following example, an `Order` class is mapped to the Orders table in the Northwind sample database.</span></span> <span data-ttu-id="debe4-109">Se ha agregado a la clase un método de instancia local.</span><span class="sxs-lookup"><span data-stu-id="debe4-109">A local instance method has been added to the class.</span></span>  
  
 <span data-ttu-id="debe4-110">En la consulta 1, el constructor de la clase `Order` se ejecuta localmente.</span><span class="sxs-lookup"><span data-stu-id="debe4-110">In Query 1, the constructor for the `Order` class is executed locally.</span></span> <span data-ttu-id="debe4-111">En la consulta 2, si [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] intentara convertir `LocalInstanceMethod()` a SQL, se produciría un error y se iniciaría una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="debe4-111">In Query 2, if [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tried to translate `LocalInstanceMethod()`into SQL, the attempt would fail and an <xref:System.InvalidOperationException> exception would be thrown.</span></span> <span data-ttu-id="debe4-112">Pero, dado que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona compatibilidad con las llamadas a métodos locales, la consulta 2 no iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="debe4-112">But because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides support for local method calls, Query2 will not throw an exception.</span></span>  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="debe4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="debe4-113">See also</span></span>
- [<span data-ttu-id="debe4-114">Información general</span><span class="sxs-lookup"><span data-stu-id="debe4-114">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)

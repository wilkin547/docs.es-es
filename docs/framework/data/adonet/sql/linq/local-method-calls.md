---
title: Llamadas a métodos locales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
ms.openlocfilehash: 25aded1aa961e182e8d2d472fca4c5a84b501af1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166175"
---
# <a name="local-method-calls"></a><span data-ttu-id="54658-102">Llamadas a métodos locales</span><span class="sxs-lookup"><span data-stu-id="54658-102">Local Method Calls</span></span>

<span data-ttu-id="54658-103">Las llamadas a métodos locales son las que se ejecutan dentro del modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="54658-103">A local method call is one that is executed within the object model.</span></span> <span data-ttu-id="54658-104">Las llamadas a métodos remotos son la que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte a SQL y después transmite al motor de base de datos para su ejecución.</span><span class="sxs-lookup"><span data-stu-id="54658-104">A remote method call is one that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates to SQL and transmits to the database engine for execution.</span></span> <span data-ttu-id="54658-105">Las llamadas a métodos locales son necesarias cuando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no puede convertir la llamada en SQL.</span><span class="sxs-lookup"><span data-stu-id="54658-105">Local method calls are needed when [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot translate the call into SQL.</span></span> <span data-ttu-id="54658-106">De lo contrario, se produce una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="54658-106">Otherwise, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="54658-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="54658-107">Example 1</span></span>  

 <span data-ttu-id="54658-108">En el ejemplo siguiente, se asigna una clase `Order` a la tabla Orders de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="54658-108">In the following example, an `Order` class is mapped to the Orders table in the Northwind sample database.</span></span> <span data-ttu-id="54658-109">Se ha agregado a la clase un método de instancia local.</span><span class="sxs-lookup"><span data-stu-id="54658-109">A local instance method has been added to the class.</span></span>  
  
 <span data-ttu-id="54658-110">En la consulta 1, el constructor de la clase `Order` se ejecuta localmente.</span><span class="sxs-lookup"><span data-stu-id="54658-110">In Query 1, the constructor for the `Order` class is executed locally.</span></span> <span data-ttu-id="54658-111">En la consulta 2, si [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] intentara convertir `LocalInstanceMethod()` a SQL, se produciría un error y se iniciaría una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="54658-111">In Query 2, if [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tried to translate `LocalInstanceMethod()`into SQL, the attempt would fail and an <xref:System.InvalidOperationException> exception would be thrown.</span></span> <span data-ttu-id="54658-112">Pero, dado que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona compatibilidad con las llamadas a métodos locales, la consulta 2 no iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="54658-112">But because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides support for local method calls, Query2 will not throw an exception.</span></span>  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="54658-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54658-113">See also</span></span>

- [<span data-ttu-id="54658-114">Información general</span><span class="sxs-lookup"><span data-stu-id="54658-114">Background Information</span></span>](background-information.md)

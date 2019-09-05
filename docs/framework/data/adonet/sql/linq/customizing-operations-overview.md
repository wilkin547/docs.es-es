---
title: 'Personalizar operaciones: Información general'
ms.date: 03/30/2017
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
ms.openlocfilehash: 48116887471709c60c9666f68c7ebdd0e6d128a1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247523"
---
# <a name="customizing-operations-overview"></a><span data-ttu-id="a125c-102">Personalizar operaciones: Información general</span><span class="sxs-lookup"><span data-stu-id="a125c-102">Customizing Operations: Overview</span></span>
<span data-ttu-id="a125c-103">De forma predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera SQL dinámico para las operaciones de inserción, actualización y eliminación por asignación.</span><span class="sxs-lookup"><span data-stu-id="a125c-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL for insert, update, and delete operations based on mapping.</span></span> <span data-ttu-id="a125c-104">Sin embargo, en la práctica, normalmente se agrega lógica empresarial propia para proporcionar seguridad, validación, etc.</span><span class="sxs-lookup"><span data-stu-id="a125c-104">However, in practice you typically want to add your own business logic to provide for security, validation, and so forth.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a125c-105">entre las técnicas para personalizar estas operaciones se incluyen las siguientes.</span><span class="sxs-lookup"><span data-stu-id="a125c-105">techniques for customizing these operations include the following.</span></span>  
  
## <a name="loading-options"></a><span data-ttu-id="a125c-106">Opciones de carga</span><span class="sxs-lookup"><span data-stu-id="a125c-106">Loading Options</span></span>  
 <span data-ttu-id="a125c-107">En las consultas es posible controlar la cantidad de datos relacionados con el destino principal que se recuperan al establecer una conexión con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a125c-107">In your queries, you can control how much data related to your main target is retrieved when you connect to the database.</span></span> <span data-ttu-id="a125c-108">Esta funcionalidad se implementa en gran medida mediante el uso de <xref:System.Data.Linq.DataLoadOptions>.</span><span class="sxs-lookup"><span data-stu-id="a125c-108">This functionality is implemented largely by using <xref:System.Data.Linq.DataLoadOptions>.</span></span> <span data-ttu-id="a125c-109">Para obtener más información, vea [carga aplazada frente a carga inmediata](deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="a125c-109">For more information, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="partial-methods"></a><span data-ttu-id="a125c-110">Métodos Partial</span><span class="sxs-lookup"><span data-stu-id="a125c-110">Partial Methods</span></span>  
 <span data-ttu-id="a125c-111">En su asignación predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona métodos parciales para ayudar a implementar lógica empresarial propia.</span><span class="sxs-lookup"><span data-stu-id="a125c-111">In its default mapping, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides partial methods to help you implement your business logic.</span></span> <span data-ttu-id="a125c-112">Para obtener más información, vea [Agregar lógica de negocios mediante métodos parciales](adding-business-logic-by-using-partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="a125c-112">For more information, see [Adding Business Logic By Using Partial Methods](adding-business-logic-by-using-partial-methods.md).</span></span>  
  
## <a name="stored-procedures-and-user-defined-functions"></a><span data-ttu-id="a125c-113">Procedimientos almacenados y funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="a125c-113">Stored Procedures and User-Defined Functions</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a125c-114">admite el uso de procedimientos almacenados y funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a125c-114">supports the use of stored procedures and user-defined functions.</span></span> <span data-ttu-id="a125c-115">Los procedimientos almacenados se utilizan con frecuencia para personalizar operaciones.</span><span class="sxs-lookup"><span data-stu-id="a125c-115">Stored procedures are frequently used to customize operations.</span></span> <span data-ttu-id="a125c-116">Para obtener más información, vea [Procedimientos almacenados](stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a125c-116">For more information, see [Stored Procedures](stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a125c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a125c-117">See also</span></span>

- [<span data-ttu-id="a125c-118">Personalización de operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="a125c-118">Customizing Insert, Update, and Delete Operations</span></span>](customizing-insert-update-and-delete-operations.md)

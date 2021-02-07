---
description: 'Más información sobre: personalización de operaciones: información general'
title: 'Personalizar operaciones: Información general'
ms.date: 03/30/2017
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
ms.openlocfilehash: bdcaf482f49b9c55fb7a1834b19b683ac2fa16bb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729606"
---
# <a name="customizing-operations-overview"></a><span data-ttu-id="d53ce-103">Personalizar operaciones: Información general</span><span class="sxs-lookup"><span data-stu-id="d53ce-103">Customizing Operations: Overview</span></span>

<span data-ttu-id="d53ce-104">De forma predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera SQL dinámico para las operaciones de inserción, actualización y eliminación por asignación.</span><span class="sxs-lookup"><span data-stu-id="d53ce-104">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL for insert, update, and delete operations based on mapping.</span></span> <span data-ttu-id="d53ce-105">Sin embargo, en la práctica, normalmente se agrega lógica empresarial propia para proporcionar seguridad, validación, etc.</span><span class="sxs-lookup"><span data-stu-id="d53ce-105">However, in practice you typically want to add your own business logic to provide for security, validation, and so forth.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="d53ce-106">entre las técnicas para personalizar estas operaciones se incluyen las siguientes.</span><span class="sxs-lookup"><span data-stu-id="d53ce-106">techniques for customizing these operations include the following.</span></span>  
  
## <a name="loading-options"></a><span data-ttu-id="d53ce-107">Opciones de carga</span><span class="sxs-lookup"><span data-stu-id="d53ce-107">Loading Options</span></span>  

 <span data-ttu-id="d53ce-108">En las consultas es posible controlar la cantidad de datos relacionados con el destino principal que se recuperan al establecer una conexión con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d53ce-108">In your queries, you can control how much data related to your main target is retrieved when you connect to the database.</span></span> <span data-ttu-id="d53ce-109">Esta funcionalidad se implementa en gran medida mediante el uso de <xref:System.Data.Linq.DataLoadOptions>.</span><span class="sxs-lookup"><span data-stu-id="d53ce-109">This functionality is implemented largely by using <xref:System.Data.Linq.DataLoadOptions>.</span></span> <span data-ttu-id="d53ce-110">Para obtener más información, vea [carga aplazada frente a carga inmediata](deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="d53ce-110">For more information, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="partial-methods"></a><span data-ttu-id="d53ce-111">Métodos Partial</span><span class="sxs-lookup"><span data-stu-id="d53ce-111">Partial Methods</span></span>  

 <span data-ttu-id="d53ce-112">En su asignación predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona métodos parciales para ayudar a implementar lógica empresarial propia.</span><span class="sxs-lookup"><span data-stu-id="d53ce-112">In its default mapping, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides partial methods to help you implement your business logic.</span></span> <span data-ttu-id="d53ce-113">Para obtener más información, vea [Agregar lógica de negocios mediante métodos parciales](adding-business-logic-by-using-partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="d53ce-113">For more information, see [Adding Business Logic By Using Partial Methods](adding-business-logic-by-using-partial-methods.md).</span></span>  
  
## <a name="stored-procedures-and-user-defined-functions"></a><span data-ttu-id="d53ce-114">Procedimientos almacenados y funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="d53ce-114">Stored Procedures and User-Defined Functions</span></span>  

 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="d53ce-115">admite el uso de procedimientos almacenados y funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d53ce-115">supports the use of stored procedures and user-defined functions.</span></span> <span data-ttu-id="d53ce-116">Los procedimientos almacenados se utilizan con frecuencia para personalizar operaciones.</span><span class="sxs-lookup"><span data-stu-id="d53ce-116">Stored procedures are frequently used to customize operations.</span></span> <span data-ttu-id="d53ce-117">Para obtener más información, vea [Procedimientos almacenados](stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d53ce-117">For more information, see [Stored Procedures](stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d53ce-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d53ce-118">See also</span></span>

- [<span data-ttu-id="d53ce-119">Personalizar operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="d53ce-119">Customizing Insert, Update, and Delete Operations</span></span>](customizing-insert-update-and-delete-operations.md)

---
title: "Personalizar operaciones: Información general"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 9776daa28b0a7ffcd3b721f004f5b9a44dd09f48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-operations-overview"></a><span data-ttu-id="8d16e-102">Personalizar operaciones: Información general</span><span class="sxs-lookup"><span data-stu-id="8d16e-102">Customizing Operations: Overview</span></span>
<span data-ttu-id="8d16e-103">De forma predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera SQL dinámico para las operaciones de inserción, actualización y eliminación por asignación.</span><span class="sxs-lookup"><span data-stu-id="8d16e-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL for insert, update, and delete operations based on mapping.</span></span> <span data-ttu-id="8d16e-104">Sin embargo, en la práctica, normalmente se agrega lógica empresarial propia para proporcionar seguridad, validación, etc.</span><span class="sxs-lookup"><span data-stu-id="8d16e-104">However, in practice you typically want to add your own business logic to provide for security, validation, and so forth.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="8d16e-105">las técnicas para personalizar estas operaciones incluyen lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d16e-105"> techniques for customizing these operations include the following.</span></span>  
  
## <a name="loading-options"></a><span data-ttu-id="8d16e-106">Opciones de carga</span><span class="sxs-lookup"><span data-stu-id="8d16e-106">Loading Options</span></span>  
 <span data-ttu-id="8d16e-107">En las consultas es posible controlar la cantidad de datos relacionados con el destino principal que se recuperan al establecer una conexión con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8d16e-107">In your queries, you can control how much data related to your main target is retrieved when you connect to the database.</span></span> <span data-ttu-id="8d16e-108">Esta funcionalidad se implementa en gran medida mediante el uso de <xref:System.Data.Linq.DataLoadOptions>.</span><span class="sxs-lookup"><span data-stu-id="8d16e-108">This functionality is implemented largely by using <xref:System.Data.Linq.DataLoadOptions>.</span></span> <span data-ttu-id="8d16e-109">Para obtener más información, consulte [ejecución diferida frente a carga inmediata](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="8d16e-109">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="partial-methods"></a><span data-ttu-id="8d16e-110">Métodos Partial</span><span class="sxs-lookup"><span data-stu-id="8d16e-110">Partial Methods</span></span>  
 <span data-ttu-id="8d16e-111">En su asignación predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona métodos parciales para ayudar a implementar lógica empresarial propia.</span><span class="sxs-lookup"><span data-stu-id="8d16e-111">In its default mapping, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides partial methods to help you implement your business logic.</span></span> <span data-ttu-id="8d16e-112">Para obtener más información, consulte [agregar Business lógica por utilizando métodos parciales](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="8d16e-112">For more information, see [Adding Business Logic By Using Partial Methods](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).</span></span>  
  
## <a name="stored-procedures-and-user-defined-functions"></a><span data-ttu-id="8d16e-113">Procedimientos almacenados y funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="8d16e-113">Stored Procedures and User-Defined Functions</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="8d16e-114">admite el uso de procedimientos almacenados y funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="8d16e-114"> supports the use of stored procedures and user-defined functions.</span></span> <span data-ttu-id="8d16e-115">Los procedimientos almacenados se utilizan con frecuencia para personalizar operaciones.</span><span class="sxs-lookup"><span data-stu-id="8d16e-115">Stored procedures are frequently used to customize operations.</span></span> <span data-ttu-id="8d16e-116">Para obtener más información, vea [Procedimientos almacenados](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8d16e-116">For more information, see [Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d16e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d16e-117">See Also</span></span>  
 [<span data-ttu-id="8d16e-118">Personalización de operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="8d16e-118">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)

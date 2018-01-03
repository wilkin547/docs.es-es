---
title: "Personalizar operaciones de actualización, inserción y eliminación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 99a87a3d0dfabb053ca05644e0b3e53361821b9b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="85d50-102">Personalizar operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="85d50-102">Customizing Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="85d50-103">De forma predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera SQL dinámico para implementar operaciones de inserción, lectura, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="85d50-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="85d50-104">Sin embargo, en la práctica, normalmente se personaliza la aplicación para satisfacer las necesidades de la empresa.</span><span class="sxs-lookup"><span data-stu-id="85d50-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85d50-105">Si utiliza [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], puede usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para personalizar las acciones de inserción, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="85d50-105">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="85d50-106">En esta sección de temas se describen las técnicas que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona para personalizar las operaciones de inserción, lectura, actualización y eliminación en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="85d50-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85d50-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="85d50-107">In This Section</span></span>  
 [<span data-ttu-id="85d50-108">Personalización de operaciones: información general</span><span class="sxs-lookup"><span data-stu-id="85d50-108">Customizing Operations: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-overview.md)  
 <span data-ttu-id="85d50-109">Describe las distintas técnicas que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona para personalizar las operaciones de inserción, lectura, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="85d50-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="85d50-110">Operaciones de inserción, actualización y eliminación</span><span class="sxs-lookup"><span data-stu-id="85d50-110">Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)  
 <span data-ttu-id="85d50-111">Describe los procesos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para manipular los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="85d50-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="85d50-112">Responsabilidades del desarrollador al invalidar un comportamiento predeterminado</span><span class="sxs-lookup"><span data-stu-id="85d50-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="85d50-113">Describe el rol del programador en la implementación de requisitos que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no aplica.</span><span class="sxs-lookup"><span data-stu-id="85d50-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="85d50-114">Adición de lógica de negocios utilizando métodos parciales</span><span class="sxs-lookup"><span data-stu-id="85d50-114">Adding Business Logic By Using Partial Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="85d50-115">Describe cómo utilizar métodos parciales para invalidar los métodos generados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="85d50-115">Describes how to use partial methods to override autogenerated methods.</span></span>

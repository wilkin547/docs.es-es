---
title: Personalizar operaciones de actualización, inserción y eliminación
ms.date: 03/30/2017
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
ms.openlocfilehash: 4b846d1e1f737cec85ecda75df5e3f66982def62
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177350"
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="baaa6-102">Personalizar operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="baaa6-102">Customizing Insert, Update, and Delete Operations</span></span>

<span data-ttu-id="baaa6-103">De forma predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera SQL dinámico para implementar operaciones de inserción, lectura, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="baaa6-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="baaa6-104">Sin embargo, en la práctica, normalmente se personaliza la aplicación para satisfacer las necesidades de la empresa.</span><span class="sxs-lookup"><span data-stu-id="baaa6-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="baaa6-105">Si usa Visual Studio, puede usar el Object Relational Designer para personalizar las acciones de inserción, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="baaa6-105">If you are using Visual Studio, you can use the Object Relational Designer to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="baaa6-106">En esta sección de temas se describen las técnicas que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona para personalizar las operaciones de inserción, lectura, actualización y eliminación en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="baaa6-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="baaa6-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="baaa6-107">In This Section</span></span>  

 [<span data-ttu-id="baaa6-108">Personalizar operaciones: Información general</span><span class="sxs-lookup"><span data-stu-id="baaa6-108">Customizing Operations: Overview</span></span>](customizing-operations-overview.md)  
 <span data-ttu-id="baaa6-109">Describe las distintas técnicas que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona para personalizar las operaciones de inserción, lectura, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="baaa6-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="baaa6-110">Operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="baaa6-110">Insert, Update, and Delete Operations</span></span>](insert-update-and-delete-operations.md)  
 <span data-ttu-id="baaa6-111">Describe los procesos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para manipular los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="baaa6-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="baaa6-112">Responsabilidades del desarrollador al invalidar un comportamiento predeterminado</span><span class="sxs-lookup"><span data-stu-id="baaa6-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="baaa6-113">Describe el rol del programador en la implementación de requisitos que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no aplica.</span><span class="sxs-lookup"><span data-stu-id="baaa6-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="baaa6-114">Agregar lógica de negocios utilizando métodos parciales</span><span class="sxs-lookup"><span data-stu-id="baaa6-114">Adding Business Logic By Using Partial Methods</span></span>](adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="baaa6-115">Describe cómo utilizar métodos parciales para invalidar los métodos generados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="baaa6-115">Describes how to use partial methods to override autogenerated methods.</span></span>

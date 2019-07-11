---
title: Personalizar operaciones de actualización, inserción y eliminación
ms.date: 03/30/2017
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
ms.openlocfilehash: 114447fd45806e567b4fde8e9e74138c096bff07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743572"
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="9b6ac-102">Personalizar operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="9b6ac-102">Customizing Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="9b6ac-103">De forma predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera SQL dinámico para implementar operaciones de inserción, lectura, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="9b6ac-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="9b6ac-104">Sin embargo, en la práctica, normalmente se personaliza la aplicación para satisfacer las necesidades de la empresa.</span><span class="sxs-lookup"><span data-stu-id="9b6ac-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b6ac-105">Si utiliza Visual Studio, puede usar Object Relational Designer para personalizar la inserción, actualización y eliminación de acciones.</span><span class="sxs-lookup"><span data-stu-id="9b6ac-105">If you are using Visual Studio, you can use the Object Relational Designer to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="9b6ac-106">En esta sección de temas se describen las técnicas que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona para personalizar las operaciones de inserción, lectura, actualización y eliminación en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="9b6ac-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9b6ac-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9b6ac-107">In This Section</span></span>  
 [<span data-ttu-id="9b6ac-108">Personalizar operaciones: Introducción</span><span class="sxs-lookup"><span data-stu-id="9b6ac-108">Customizing Operations: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-overview.md)  
 <span data-ttu-id="9b6ac-109">Describe las distintas técnicas que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona para personalizar las operaciones de inserción, lectura, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="9b6ac-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="9b6ac-110">Operaciones de inserción, actualización y eliminación</span><span class="sxs-lookup"><span data-stu-id="9b6ac-110">Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)  
 <span data-ttu-id="9b6ac-111">Describe los procesos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para manipular los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9b6ac-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="9b6ac-112">Responsabilidades del desarrollador al invalidar un comportamiento predeterminado</span><span class="sxs-lookup"><span data-stu-id="9b6ac-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="9b6ac-113">Describe el rol del programador en la implementación de requisitos que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no aplica.</span><span class="sxs-lookup"><span data-stu-id="9b6ac-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="9b6ac-114">Adición de lógica de negocios utilizando métodos parciales</span><span class="sxs-lookup"><span data-stu-id="9b6ac-114">Adding Business Logic By Using Partial Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="9b6ac-115">Describe cómo utilizar métodos parciales para invalidar los métodos generados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9b6ac-115">Describes how to use partial methods to override autogenerated methods.</span></span>

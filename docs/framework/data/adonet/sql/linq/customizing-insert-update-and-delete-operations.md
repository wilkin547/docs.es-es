---
description: Más información acerca de cómo personalizar las operaciones de inserción, actualización y eliminación
title: Personalizar operaciones de actualización, inserción y eliminación
ms.date: 03/30/2017
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
ms.openlocfilehash: 44bd76b61aff335019818b3c61040d10babe7301
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773217"
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="91a31-103">Personalizar operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="91a31-103">Customizing Insert, Update, and Delete Operations</span></span>

<span data-ttu-id="91a31-104">De forma predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera SQL dinámico para implementar operaciones de inserción, lectura, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="91a31-104">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="91a31-105">Sin embargo, en la práctica, normalmente se personaliza la aplicación para satisfacer las necesidades de la empresa.</span><span class="sxs-lookup"><span data-stu-id="91a31-105">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="91a31-106">Si usa Visual Studio, puede usar el Object Relational Designer para personalizar las acciones de inserción, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="91a31-106">If you are using Visual Studio, you can use the Object Relational Designer to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="91a31-107">En esta sección de temas se describen las técnicas que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona para personalizar las operaciones de inserción, lectura, actualización y eliminación en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="91a31-107">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91a31-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="91a31-108">In This Section</span></span>  

 [<span data-ttu-id="91a31-109">Personalizar operaciones: Información general</span><span class="sxs-lookup"><span data-stu-id="91a31-109">Customizing Operations: Overview</span></span>](customizing-operations-overview.md)  
 <span data-ttu-id="91a31-110">Describe las distintas técnicas que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona para personalizar las operaciones de inserción, lectura, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="91a31-110">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="91a31-111">Operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="91a31-111">Insert, Update, and Delete Operations</span></span>](insert-update-and-delete-operations.md)  
 <span data-ttu-id="91a31-112">Describe los procesos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para manipular los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="91a31-112">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="91a31-113">Responsabilidades del desarrollador al invalidar un comportamiento predeterminado</span><span class="sxs-lookup"><span data-stu-id="91a31-113">Responsibilities of the Developer In Overriding Default Behavior</span></span>](responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="91a31-114">Describe el rol del programador en la implementación de requisitos que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no aplica.</span><span class="sxs-lookup"><span data-stu-id="91a31-114">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="91a31-115">Agregar lógica de negocios utilizando métodos parciales</span><span class="sxs-lookup"><span data-stu-id="91a31-115">Adding Business Logic By Using Partial Methods</span></span>](adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="91a31-116">Describe cómo utilizar métodos parciales para invalidar los métodos generados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="91a31-116">Describes how to use partial methods to override autogenerated methods.</span></span>

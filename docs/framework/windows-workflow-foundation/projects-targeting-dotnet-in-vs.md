---
title: Escribir proyectos destinados a .NET Framework 3.0 y 3.5 en Visual Studio 2010
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81858ab7-763c-4eac-83fe-d7205e5c4c98
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 95348ad57bb4dce1799c1ddf741b69f0e2b969af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="writing-projects-targeting-the-net-framework-30-and-35-in-visual-studio-2010"></a><span data-ttu-id="0011d-102">Escribir proyectos destinados a .NET Framework 3.0 y 3.5 en Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="0011d-102">Writing Projects Targeting the .NET Framework 3.0 and 3.5 in Visual Studio 2010</span></span>
<span data-ttu-id="0011d-103">Puede utilizar [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] para crear proyectos para [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] versión 3.0 o 3.5.</span><span class="sxs-lookup"><span data-stu-id="0011d-103">You can use [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] to create projects that target the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] version 3.0 or 3.5.</span></span> <span data-ttu-id="0011d-104">En este tema se describe cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="0011d-104">This topic describes how to do this.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0011d-105">Al agregar actividades, asegúrese de que se establece la versión deseada de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0011d-105">When adding activities, make sure that the desired version of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] is set.</span></span> <span data-ttu-id="0011d-106">Cambiar la versión de destino del flujo de trabajo una vez agregadas las actividades producirá un error de validación en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0011d-106">Changing the target version of the workflow after activities are added will cause the workflow to fail validation.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="0011d-107">Abrir flujos de trabajo existentes en [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] que tengan actividades de  .Net Framework 3.5 producirá un error en `this.SetValue()`.</span><span class="sxs-lookup"><span data-stu-id="0011d-107">Opening existing workflows in [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] that have .Net Framework 3.5 activities will cause an error at `this.SetValue()`.</span></span> <span data-ttu-id="0011d-108">Para abrir proyectos creados con versiones anteriores de .Net Framework, abra primero un flujo de trabajo en blanco en el diseñador y agregue una actividad de  .Net Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="0011d-108">In order to open projects created with previous versions of the .Net Framework, first open a blank workflow in the designer and add a .Net Framework 3.5 activity.</span></span>  
  
## <a name="to-create-a-net-framework--30-or-35-project-with-visual-studio-2010"></a><span data-ttu-id="0011d-109">Crear un proyecto .NET Framework 3.0 o 3.5 con Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="0011d-109">To create a .NET Framework  3.0 or 3.5 project with Visual Studio 2010</span></span>  
  
1.  <span data-ttu-id="0011d-110">Abra [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0011d-110">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="0011d-111">Seleccione **archivo**, **nueva**, **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="0011d-111">Select **File**, **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="0011d-112">En la lista desplegable de la parte superior del cuadro de diálogo, seleccione la versión deseada de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0011d-112">In the drop-down list at the top of the dialog box, select the desired version of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="to-upgrade-the-targeted-version-of-the-net-framework"></a><span data-ttu-id="0011d-113">Actualizar la versión de destino de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0011d-113">To upgrade the targeted version of the .NET Framework</span></span>  
  
1.  <span data-ttu-id="0011d-114">Haga clic en el proyecto en el Explorador de soluciones y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0011d-114">Right-click the project in Solution Explorer, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="0011d-115">En el **.NET Framework de destino** lista desplegable, seleccione la versión deseada.</span><span class="sxs-lookup"><span data-stu-id="0011d-115">In the **Target Framework** drop-down list, select the desired version.</span></span>

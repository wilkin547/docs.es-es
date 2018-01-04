---
title: "Cómo: Crear un nuevo valor de configuración en tiempo de diseño"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04b86579f45c5a357f8759bf36ae41f7a5c6e98b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="9bfd7-102">Cómo: Crear un nuevo valor de configuración en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="9bfd7-102">How To: Create a New Setting at Design Time</span></span>
<span data-ttu-id="9bfd7-103">Puede crear una nueva configuración en tiempo de diseño mediante el Diseñador de configuración.</span><span class="sxs-lookup"><span data-stu-id="9bfd7-103">You can create a new setting at design time by using the Settings designer.</span></span> <span data-ttu-id="9bfd7-104">El Diseñador de configuración es una interfaz de estilo de cuadrícula que le permite crear una nueva configuración y especificar propiedades para ver esas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="9bfd7-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="9bfd7-105">Debe especificar el nombre, valor, tipo y ámbito de la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="9bfd7-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="9bfd7-106">Una vez que se crea una configuración, es accesible en el código.</span><span class="sxs-lookup"><span data-stu-id="9bfd7-106">Once a setting is created, it is accessible in code.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="9bfd7-107">Para crear una nueva configuración en tiempo de diseño en C#</span><span class="sxs-lookup"><span data-stu-id="9bfd7-107">To create a new setting at design time in C#</span></span>  
  
1.  <span data-ttu-id="9bfd7-108">En **el Explorador de soluciones**, expanda la **propiedades** nodo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9bfd7-108">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>  
  
2.  <span data-ttu-id="9bfd7-109">Haga doble clic en el archivo .settings en el que desea agregar una nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="9bfd7-109">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="9bfd7-110">El nombre predeterminado de este archivo es Settings.settings.</span><span class="sxs-lookup"><span data-stu-id="9bfd7-110">The default name for this file is Settings.settings.</span></span>  
  
3.  <span data-ttu-id="9bfd7-111">En el Diseñador de configuración, establezca el nombre, el valor, el tipo y el ámbito de la configuración.</span><span class="sxs-lookup"><span data-stu-id="9bfd7-111">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="9bfd7-112">Cada fila representa un valor único.</span><span class="sxs-lookup"><span data-stu-id="9bfd7-112">Each row represents a single setting.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="9bfd7-113">Para crear una nueva configuración en tiempo de diseño en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9bfd7-113">To create a new setting at design time in Visual Basic</span></span>  
  
1.  <span data-ttu-id="9bfd7-114">En **el Explorador de soluciones**, haga clic en el nodo del proyecto y elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9bfd7-114">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="9bfd7-115">En el **propiedades** página, seleccione la **configuración** ficha.</span><span class="sxs-lookup"><span data-stu-id="9bfd7-115">In the **Properties** page, select the **Settings** tab.</span></span>  
  
3.  <span data-ttu-id="9bfd7-116">En el Diseñador de configuración, establezca el nombre, el valor, el tipo y el ámbito de la configuración.</span><span class="sxs-lookup"><span data-stu-id="9bfd7-116">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="9bfd7-117">Cada fila representa un valor único.</span><span class="sxs-lookup"><span data-stu-id="9bfd7-117">Each row represents a single setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bfd7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bfd7-118">See Also</span></span>  
 [<span data-ttu-id="9bfd7-119">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="9bfd7-119">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="9bfd7-120">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="9bfd7-120">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [<span data-ttu-id="9bfd7-121">Cambiar el valor de una opción de configuración existente en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="9bfd7-121">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)

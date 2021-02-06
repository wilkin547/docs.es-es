---
description: 'Más información acerca de: My. Settings (objeto)'
title: My.Settings (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 92323c5379d0c5a4dbf96cfdbe0becccc2bad7cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640607"
---
# <a name="mysettings-object"></a><span data-ttu-id="b81fe-103">My.Settings (Objeto)</span><span class="sxs-lookup"><span data-stu-id="b81fe-103">My.Settings Object</span></span>

<span data-ttu-id="b81fe-104">Proporciona propiedades y métodos para tener acceso a la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b81fe-104">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b81fe-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b81fe-105">Remarks</span></span>  

 <span data-ttu-id="b81fe-106">El `My.Settings` objeto proporciona acceso a la configuración de la aplicación y permite almacenar y recuperar dinámicamente la configuración de propiedades y otra información de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b81fe-106">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="b81fe-107">Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="b81fe-107">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b81fe-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b81fe-108">Properties</span></span>  

 <span data-ttu-id="b81fe-109">Las propiedades del objeto `My.Settings` proporcionan acceso a la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b81fe-109">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="b81fe-110">Para agregar o quitar la configuración, use el **Diseñador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="b81fe-110">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="b81fe-111">Cada configuración tiene un **nombre**, **tipo**, **ámbito** y **valor**, y esta configuración determina cómo aparece la propiedad para tener acceso a cada configuración en el `My.Settings` objeto:</span><span class="sxs-lookup"><span data-stu-id="b81fe-111">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
- <span data-ttu-id="b81fe-112">**Nombre** determina el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b81fe-112">**Name** determines the name of the property.</span></span>  
  
- <span data-ttu-id="b81fe-113">**Tipo** determina el tipo de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b81fe-113">**Type** determines the type of the property.</span></span>  
  
- <span data-ttu-id="b81fe-114">El **ámbito** indica si la propiedad es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="b81fe-114">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="b81fe-115">Si el valor es **Application**, la propiedad es de solo lectura; Si el valor es **User**, la propiedad es de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="b81fe-115">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
- <span data-ttu-id="b81fe-116">**Value** es el valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b81fe-116">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b81fe-117">Métodos</span><span class="sxs-lookup"><span data-stu-id="b81fe-117">Methods</span></span>  
  
|<span data-ttu-id="b81fe-118">Método</span><span class="sxs-lookup"><span data-stu-id="b81fe-118">Method</span></span>|<span data-ttu-id="b81fe-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="b81fe-119">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="b81fe-120">Vuelve a cargar la configuración de usuario de los últimos valores guardados.</span><span class="sxs-lookup"><span data-stu-id="b81fe-120">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="b81fe-121">Guarda la configuración del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="b81fe-121">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="b81fe-122">El `My.Settings` objeto también proporciona propiedades y métodos avanzados, heredados de la <xref:System.Configuration.ApplicationSettingsBase> clase.</span><span class="sxs-lookup"><span data-stu-id="b81fe-122">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="b81fe-123">Tareas</span><span class="sxs-lookup"><span data-stu-id="b81fe-123">Tasks</span></span>  

 <span data-ttu-id="b81fe-124">En la tabla siguiente se muestran ejemplos de tareas que implican el `My.Settings` objeto.</span><span class="sxs-lookup"><span data-stu-id="b81fe-124">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="b81fe-125">En</span><span class="sxs-lookup"><span data-stu-id="b81fe-125">To</span></span>|<span data-ttu-id="b81fe-126">Vea</span><span class="sxs-lookup"><span data-stu-id="b81fe-126">See</span></span>|  
|---|---|  
|<span data-ttu-id="b81fe-127">Leer una configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b81fe-127">Read an application setting</span></span>|[<span data-ttu-id="b81fe-128">Cómo: Leer la configuración de la aplicación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b81fe-128">How to: Read Application Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="b81fe-129">Cambiar la configuración de un usuario</span><span class="sxs-lookup"><span data-stu-id="b81fe-129">Change a user setting</span></span>|[<span data-ttu-id="b81fe-130">Cómo: Cambiar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b81fe-130">How to: Change User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="b81fe-131">Conservar la configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="b81fe-131">Persist user settings</span></span>|[<span data-ttu-id="b81fe-132">Cómo: Conservar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b81fe-132">How to: Persist User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="b81fe-133">Crear una cuadrícula de propiedades para la configuración del usuario</span><span class="sxs-lookup"><span data-stu-id="b81fe-133">Create a property grid for user settings</span></span>|[<span data-ttu-id="b81fe-134">Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b81fe-134">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="b81fe-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b81fe-135">Example</span></span>  

 <span data-ttu-id="b81fe-136">En este ejemplo se muestra el valor de la configuración `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="b81fe-136">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="b81fe-137">Para que este ejemplo funcione, la aplicación debe tener una configuración `Nickname` de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="b81fe-137">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b81fe-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="b81fe-138">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- [<span data-ttu-id="b81fe-139">Cómo: Leer la configuración de la aplicación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b81fe-139">How to: Read Application Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="b81fe-140">Cómo: Cambiar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b81fe-140">How to: Change User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="b81fe-141">Cómo: Conservar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b81fe-141">How to: Persist User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="b81fe-142">Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b81fe-142">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="b81fe-143">Administrar la configuración de la aplicación (.NET)</span><span class="sxs-lookup"><span data-stu-id="b81fe-143">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

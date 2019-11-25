---
title: My.Settings (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 9560a51332ea596d4cf2228f1e07c158a0457ece
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350357"
---
# <a name="mysettings-object"></a><span data-ttu-id="735fa-102">My.Settings (Objeto)</span><span class="sxs-lookup"><span data-stu-id="735fa-102">My.Settings Object</span></span>
<span data-ttu-id="735fa-103">Provides properties and methods for accessing the application's settings.</span><span class="sxs-lookup"><span data-stu-id="735fa-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="735fa-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="735fa-104">Remarks</span></span>  
 <span data-ttu-id="735fa-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span><span class="sxs-lookup"><span data-stu-id="735fa-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="735fa-106">Para obtener más información, consulte [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="735fa-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="735fa-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="735fa-107">Properties</span></span>  
 <span data-ttu-id="735fa-108">Las propiedades del objeto `My.Settings` proporcionan acceso a la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="735fa-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="735fa-109">To add or remove settings, use the **Settings Designer**.</span><span class="sxs-lookup"><span data-stu-id="735fa-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="735fa-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span><span class="sxs-lookup"><span data-stu-id="735fa-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
- <span data-ttu-id="735fa-111">**Name** determines the name of the property.</span><span class="sxs-lookup"><span data-stu-id="735fa-111">**Name** determines the name of the property.</span></span>  
  
- <span data-ttu-id="735fa-112">**Type** determines the type of the property.</span><span class="sxs-lookup"><span data-stu-id="735fa-112">**Type** determines the type of the property.</span></span>  
  
- <span data-ttu-id="735fa-113">**Scope** indicates if the property is read-only.</span><span class="sxs-lookup"><span data-stu-id="735fa-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="735fa-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span><span class="sxs-lookup"><span data-stu-id="735fa-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
- <span data-ttu-id="735fa-115">**Value** is the default value of the property.</span><span class="sxs-lookup"><span data-stu-id="735fa-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="735fa-116">Métodos</span><span class="sxs-lookup"><span data-stu-id="735fa-116">Methods</span></span>  
  
|<span data-ttu-id="735fa-117">Método</span><span class="sxs-lookup"><span data-stu-id="735fa-117">Method</span></span>|<span data-ttu-id="735fa-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="735fa-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="735fa-119">Reloads the user settings from the last saved values.</span><span class="sxs-lookup"><span data-stu-id="735fa-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="735fa-120">Saves the current user settings.</span><span class="sxs-lookup"><span data-stu-id="735fa-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="735fa-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span><span class="sxs-lookup"><span data-stu-id="735fa-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="735fa-122">Tareas</span><span class="sxs-lookup"><span data-stu-id="735fa-122">Tasks</span></span>  
 <span data-ttu-id="735fa-123">The following table lists examples of tasks involving the `My.Settings` object.</span><span class="sxs-lookup"><span data-stu-id="735fa-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="735fa-124">En</span><span class="sxs-lookup"><span data-stu-id="735fa-124">To</span></span>|<span data-ttu-id="735fa-125">Vea</span><span class="sxs-lookup"><span data-stu-id="735fa-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="735fa-126">Read an application setting</span><span class="sxs-lookup"><span data-stu-id="735fa-126">Read an application setting</span></span>|[<span data-ttu-id="735fa-127">Cómo: Leer la configuración de la aplicación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="735fa-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="735fa-128">Change a user setting</span><span class="sxs-lookup"><span data-stu-id="735fa-128">Change a user setting</span></span>|[<span data-ttu-id="735fa-129">Cómo: Cambiar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="735fa-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="735fa-130">Persist user settings</span><span class="sxs-lookup"><span data-stu-id="735fa-130">Persist user settings</span></span>|[<span data-ttu-id="735fa-131">Cómo: Conservar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="735fa-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="735fa-132">Create a property grid for user settings</span><span class="sxs-lookup"><span data-stu-id="735fa-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="735fa-133">Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="735fa-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="735fa-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="735fa-134">Example</span></span>  
 <span data-ttu-id="735fa-135">En este ejemplo se muestra el valor de la configuración `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="735fa-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="735fa-136">Para que este ejemplo funcione, la aplicación debe tener una configuración `Nickname` de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="735fa-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="735fa-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="735fa-137">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- [<span data-ttu-id="735fa-138">Cómo: Leer la configuración de la aplicación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="735fa-138">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="735fa-139">Cómo: Cambiar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="735fa-139">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="735fa-140">Cómo: Conservar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="735fa-140">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="735fa-141">Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="735fa-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="735fa-142">Administrar la configuración de la aplicación (.NET)</span><span class="sxs-lookup"><span data-stu-id="735fa-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

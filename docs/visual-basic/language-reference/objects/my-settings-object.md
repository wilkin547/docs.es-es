---
title: My.Settings (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: f3348e9eea5bdd7f4fd911150877c9aefdd66bcc
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867300"
---
# <a name="mysettings-object"></a><span data-ttu-id="b1a3f-102">My.Settings (Objeto)</span><span class="sxs-lookup"><span data-stu-id="b1a3f-102">My.Settings Object</span></span>

<span data-ttu-id="b1a3f-103">Proporciona propiedades y métodos para tener acceso a la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b1a3f-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1a3f-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b1a3f-104">Remarks</span></span>  

 <span data-ttu-id="b1a3f-105">El `My.Settings` objeto proporciona acceso a la configuración de la aplicación y permite almacenar y recuperar dinámicamente la configuración de propiedades y otra información de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b1a3f-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="b1a3f-106">Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="b1a3f-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b1a3f-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b1a3f-107">Properties</span></span>  

 <span data-ttu-id="b1a3f-108">Las propiedades del objeto `My.Settings` proporcionan acceso a la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b1a3f-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="b1a3f-109">Para agregar o quitar la configuración, use el **Diseñador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="b1a3f-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="b1a3f-110">Cada configuración tiene un **nombre**, **tipo**, **ámbito**y **valor**, y esta configuración determina cómo aparece la propiedad para tener acceso a cada configuración en el `My.Settings` objeto:</span><span class="sxs-lookup"><span data-stu-id="b1a3f-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
- <span data-ttu-id="b1a3f-111">**Nombre** determina el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b1a3f-111">**Name** determines the name of the property.</span></span>  
  
- <span data-ttu-id="b1a3f-112">**Tipo** determina el tipo de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b1a3f-112">**Type** determines the type of the property.</span></span>  
  
- <span data-ttu-id="b1a3f-113">El **ámbito** indica si la propiedad es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="b1a3f-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="b1a3f-114">Si el valor es **Application**, la propiedad es de solo lectura; Si el valor es **User**, la propiedad es de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="b1a3f-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
- <span data-ttu-id="b1a3f-115">**Value** es el valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b1a3f-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b1a3f-116">Métodos</span><span class="sxs-lookup"><span data-stu-id="b1a3f-116">Methods</span></span>  
  
|<span data-ttu-id="b1a3f-117">Método</span><span class="sxs-lookup"><span data-stu-id="b1a3f-117">Method</span></span>|<span data-ttu-id="b1a3f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="b1a3f-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="b1a3f-119">Vuelve a cargar la configuración de usuario de los últimos valores guardados.</span><span class="sxs-lookup"><span data-stu-id="b1a3f-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="b1a3f-120">Guarda la configuración del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="b1a3f-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="b1a3f-121">El `My.Settings` objeto también proporciona propiedades y métodos avanzados, heredados de la <xref:System.Configuration.ApplicationSettingsBase> clase.</span><span class="sxs-lookup"><span data-stu-id="b1a3f-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="b1a3f-122">Tareas</span><span class="sxs-lookup"><span data-stu-id="b1a3f-122">Tasks</span></span>  

 <span data-ttu-id="b1a3f-123">En la tabla siguiente se muestran ejemplos de tareas que implican el `My.Settings` objeto.</span><span class="sxs-lookup"><span data-stu-id="b1a3f-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="b1a3f-124">En</span><span class="sxs-lookup"><span data-stu-id="b1a3f-124">To</span></span>|<span data-ttu-id="b1a3f-125">Vea</span><span class="sxs-lookup"><span data-stu-id="b1a3f-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="b1a3f-126">Leer una configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b1a3f-126">Read an application setting</span></span>|[<span data-ttu-id="b1a3f-127">Cómo: Leer la configuración de la aplicación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1a3f-127">How to: Read Application Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="b1a3f-128">Cambiar la configuración de un usuario</span><span class="sxs-lookup"><span data-stu-id="b1a3f-128">Change a user setting</span></span>|[<span data-ttu-id="b1a3f-129">Cómo: Cambiar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1a3f-129">How to: Change User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="b1a3f-130">Conservar la configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="b1a3f-130">Persist user settings</span></span>|[<span data-ttu-id="b1a3f-131">Cómo: Conservar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1a3f-131">How to: Persist User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="b1a3f-132">Crear una cuadrícula de propiedades para la configuración del usuario</span><span class="sxs-lookup"><span data-stu-id="b1a3f-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="b1a3f-133">Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1a3f-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="b1a3f-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1a3f-134">Example</span></span>  

 <span data-ttu-id="b1a3f-135">En este ejemplo se muestra el valor de la configuración `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="b1a3f-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="b1a3f-136">Para que este ejemplo funcione, la aplicación debe tener una configuración `Nickname` de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="b1a3f-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1a3f-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1a3f-137">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- [<span data-ttu-id="b1a3f-138">Cómo: Leer la configuración de la aplicación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1a3f-138">How to: Read Application Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="b1a3f-139">Cómo: Cambiar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1a3f-139">How to: Change User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="b1a3f-140">Cómo: Conservar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1a3f-140">How to: Persist User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="b1a3f-141">Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1a3f-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="b1a3f-142">Administrar la configuración de la aplicación (.NET)</span><span class="sxs-lookup"><span data-stu-id="b1a3f-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

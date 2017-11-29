---
title: "Utilizar valores de configuración de aplicación y de usuario"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f9544b6af74608bd1b29db3250e887999ae3187f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="02c28-102">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="02c28-102">Using Application Settings and User Settings</span></span>
<span data-ttu-id="02c28-103">A partir de .NET Framework 2.0, puede crear y obtener acceso a los valores que se conservan entre sesiones de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02c28-103">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="02c28-104">Estos valores se denominan *configuración*.</span><span class="sxs-lookup"><span data-stu-id="02c28-104">These values are called *settings*.</span></span> <span data-ttu-id="02c28-105">Configuración puede representar las preferencias del usuario o información valiosa de la aplicación debe usar.</span><span class="sxs-lookup"><span data-stu-id="02c28-105">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="02c28-106">Por ejemplo, podría crear una serie de valores que almacenan las preferencias del usuario para la combinación de colores de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="02c28-106">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="02c28-107">O bien, puede almacenar la cadena de conexión que especifica una base de datos que usa su aplicación.</span><span class="sxs-lookup"><span data-stu-id="02c28-107">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="02c28-108">La configuración permite que conservar la información que es fundamental para la aplicación fuera del código así como crear perfiles que almacenen las preferencias de usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="02c28-108">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="02c28-109">Los temas de esta sección describen cómo utilizar la configuración en tiempo de diseño y tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="02c28-109">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02c28-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="02c28-110">In This Section</span></span>  
 [<span data-ttu-id="02c28-111">Crear un nuevo valor de configuración en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="02c28-111">How To: Create a New Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="02c28-112">Explica cómo utilizar Visual Studio para crear una nueva configuración para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="02c28-112">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="02c28-113">Cambiar el valor de una opción de configuración existente en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="02c28-113">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="02c28-114">Describe cómo utilizar Visual Studio para cambiar el valor de una configuración existente.</span><span class="sxs-lookup"><span data-stu-id="02c28-114">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="02c28-115">Cambiar el valor de una opción de configuración entre sesiones de aplicación</span><span class="sxs-lookup"><span data-stu-id="02c28-115">How To: Change the Value of a Setting Between Application Sessions</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="02c28-116">Describe cómo cambiar el valor de una configuración en una aplicación compilada entre sesiones de aplicación.</span><span class="sxs-lookup"><span data-stu-id="02c28-116">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="02c28-117">Leer valores de configuración en tiempo de ejecución con C#</span><span class="sxs-lookup"><span data-stu-id="02c28-117">How To: Read Settings at Run Time With C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="02c28-118">Describe cómo utilizar código para leer los valores con C#.</span><span class="sxs-lookup"><span data-stu-id="02c28-118">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="02c28-119">Escribir valores de configuración de usuario en tiempo de ejecución con C#</span><span class="sxs-lookup"><span data-stu-id="02c28-119">How To: Write User Settings at Run Time with C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="02c28-120">Explica cómo usar código para escribir y guardar los valores de configuración de usuario con C#.</span><span class="sxs-lookup"><span data-stu-id="02c28-120">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="02c28-121">Agregar varios conjuntos de valores de configuración a una aplicación en C#</span><span class="sxs-lookup"><span data-stu-id="02c28-121">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="02c28-122">Detalles sobre cómo agregar varios conjuntos de configuración a una aplicación con C#.</span><span class="sxs-lookup"><span data-stu-id="02c28-122">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c28-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="02c28-123">See Also</span></span>  
 [<span data-ttu-id="02c28-124">Configuración de la aplicación en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="02c28-124">Application Settings for Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/application-settings-for-windows-forms.md)

---
title: Utilizar valores de configuración de aplicación y de usuario
ms.date: 03/30/2017
description: Aprenda a usar la configuración de la aplicación y la configuración de usuario para crear y obtener acceso a los valores que se conservan entre las sesiones de ejecución de la aplicación.
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
ms.openlocfilehash: a30fd354986265eca002fce57bccf5b3bb2adc15
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903173"
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="4b051-103">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="4b051-103">Using Application Settings and User Settings</span></span>
<span data-ttu-id="4b051-104">A partir del .NET Framework 2,0, puede crear y obtener acceso a los valores que se conservan entre las sesiones de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b051-104">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="4b051-105">Estos valores se denominan *valores*.</span><span class="sxs-lookup"><span data-stu-id="4b051-105">These values are called *settings*.</span></span> <span data-ttu-id="4b051-106">La configuración puede representar preferencias del usuario o información valiosa que debe usar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b051-106">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="4b051-107">Por ejemplo, puede crear una serie de opciones de configuración que almacenen las preferencias de usuario para la combinación de colores de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b051-107">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="4b051-108">También puede almacenar la cadena de conexión que especifica una base de datos que utiliza la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b051-108">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="4b051-109">La configuración le permite conservar la información que es fundamental para la aplicación fuera del código y crear perfiles que almacenen las preferencias de los usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="4b051-109">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="4b051-110">En los temas de esta sección se describe cómo usar las opciones de configuración en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4b051-110">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4b051-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4b051-111">In This Section</span></span>  
 [<span data-ttu-id="4b051-112">Cómo crear un valor de configuración en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="4b051-112">How To: Create a New Setting at Design Time</span></span>](how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="4b051-113">Explica cómo usar Visual Studio para crear un nuevo valor para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b051-113">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="4b051-114">Cómo cambiar el valor de una opción de configuración existente en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="4b051-114">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="4b051-115">Describe cómo usar Visual Studio para cambiar el valor de una configuración existente.</span><span class="sxs-lookup"><span data-stu-id="4b051-115">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="4b051-116">Cómo cambiar el valor de una opción de configuración entre sesiones de aplicación</span><span class="sxs-lookup"><span data-stu-id="4b051-116">How To: Change the Value of a Setting Between Application Sessions</span></span>](how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="4b051-117">Detalla cómo cambiar el valor de una configuración en una aplicación compilada entre sesiones de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b051-117">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="4b051-118">Cómo leer valores de configuración en tiempo de ejecución con C#</span><span class="sxs-lookup"><span data-stu-id="4b051-118">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="4b051-119">Describe cómo usar el código para leer la configuración con C#.</span><span class="sxs-lookup"><span data-stu-id="4b051-119">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="4b051-120">Cómo escribir valores de configuración de usuario en tiempo de ejecución con C#</span><span class="sxs-lookup"><span data-stu-id="4b051-120">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="4b051-121">Explica cómo usar el código para escribir y guardar los valores de configuración de usuario con C#.</span><span class="sxs-lookup"><span data-stu-id="4b051-121">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="4b051-122">Cómo agregar varios conjuntos de valores de configuración a una aplicación en C#</span><span class="sxs-lookup"><span data-stu-id="4b051-122">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="4b051-123">Detalla cómo agregar varios conjuntos de valores de configuración a una aplicación con C#.</span><span class="sxs-lookup"><span data-stu-id="4b051-123">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b051-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b051-124">See also</span></span>

- [<span data-ttu-id="4b051-125">Configuración de la aplicación en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b051-125">Application Settings for Windows Forms</span></span>](application-settings-for-windows-forms.md)

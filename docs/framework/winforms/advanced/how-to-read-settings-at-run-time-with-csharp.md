---
title: Cómo leer valores de configuración en tiempo de ejecución con C#
description: Obtenga información sobre cómo leer la configuración de ámbito de aplicación y de ámbito de usuario en tiempo de ejecución con C# a través del objeto de propiedades.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: d784544e018bb693c501e35ea36fcae1946ef5eb
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903361"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a><span data-ttu-id="f8e55-103">Cómo: leer la configuración en tiempo de ejecución con C\#</span><span class="sxs-lookup"><span data-stu-id="f8e55-103">How To: Read Settings at Run Time With C\#</span></span>

<span data-ttu-id="f8e55-104">Puede leer valores de configuración de aplicación y usuario en tiempo de ejecución a través del objeto Properties.</span><span class="sxs-lookup"><span data-stu-id="f8e55-104">You can read both Application-scoped and User-scoped settings at run time via the Properties object.</span></span> <span data-ttu-id="f8e55-105">El objeto Properties expone todas las opciones de configuración predeterminadas del proyecto a través del miembro Properties. Settings. default en el espacio de nombres predeterminado del proyecto en el que se definen.</span><span class="sxs-lookup"><span data-stu-id="f8e55-105">The Properties object exposes all of the default settings for the project via the Properties.Settings.Default member in the default namespace of the project they are defined in.</span></span>  
  
## <a name="to-read-settings-at-run-time-with-c"></a><span data-ttu-id="f8e55-106">Para leer la configuración en tiempo de ejecución con C\#</span><span class="sxs-lookup"><span data-stu-id="f8e55-106">To Read Settings at Run Time with C\#</span></span>
  
<span data-ttu-id="f8e55-107">Acceda a la configuración correspondiente a través del miembro Properties.Settings.Default. </span><span class="sxs-lookup"><span data-stu-id="f8e55-107">Access the appropriate setting via the Properties.Settings.Default member.</span></span> <span data-ttu-id="f8e55-108">En el ejemplo siguiente, se muestra cómo asignar un valor de configuración con el nombre `myColor` a una propiedad BackColor.</span><span class="sxs-lookup"><span data-stu-id="f8e55-108">The following example shows how to assign a setting named `myColor` to a BackColor property.</span></span> <span data-ttu-id="f8e55-109">Es necesario que haya creado previamente un archivo de configuración con una configuración denominada `myColor` de tipo `System.Drawing.Color`.</span><span class="sxs-lookup"><span data-stu-id="f8e55-109">It requires you to have previously created a Settings file containing a setting named `myColor` of type `System.Drawing.Color`.</span></span> <span data-ttu-id="f8e55-110">Para obtener información sobre cómo crear un archivo de configuración, vea [Cómo: crear un nuevo valor de configuración en tiempo de diseño](how-to-create-a-new-setting-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="f8e55-110">For information about creating a Settings file, see [How To: Create a New Setting at Design Time](how-to-create-a-new-setting-at-design-time.md).</span></span>  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8e55-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f8e55-111">See also</span></span>

- [<span data-ttu-id="f8e55-112">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="f8e55-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="f8e55-113">Cómo escribir valores de configuración de usuario en tiempo de ejecución con C#</span><span class="sxs-lookup"><span data-stu-id="f8e55-113">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="f8e55-114">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f8e55-114">Application Settings Overview</span></span>](application-settings-overview.md)

---
title: Cómo leer valores de configuración en tiempo de ejecución con C#
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 6a40718d57fad4041eeea2fded03b7256abbe8d1
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710227"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a><span data-ttu-id="30a18-102">Cómo Leer la configuración en tiempo de ejecución con C\#</span><span class="sxs-lookup"><span data-stu-id="30a18-102">How To: Read Settings at Run Time With C\#</span></span>

<span data-ttu-id="30a18-103">Puede leer valores de configuración de aplicación y usuario en tiempo de ejecución a través del objeto Properties.</span><span class="sxs-lookup"><span data-stu-id="30a18-103">You can read both Application-scoped and User-scoped settings at run time via the Properties object.</span></span> <span data-ttu-id="30a18-104">El objeto Properties expone todas las opciones de configuración predeterminadas del proyecto a través del miembro Properties. Settings. default en el espacio de nombres predeterminado del proyecto en el que se definen.</span><span class="sxs-lookup"><span data-stu-id="30a18-104">The Properties object exposes all of the default settings for the project via the Properties.Settings.Default member in the default namespace of the project they are defined in.</span></span>  
  
## <a name="to-read-settings-at-run-time-with-c"></a><span data-ttu-id="30a18-105">Para leer la configuración en tiempo de ejecución con C\#</span><span class="sxs-lookup"><span data-stu-id="30a18-105">To Read Settings at Run Time with C\#</span></span>
  
<span data-ttu-id="30a18-106">Acceda a la configuración correspondiente a través del miembro Properties.Settings.Default.</span><span class="sxs-lookup"><span data-stu-id="30a18-106">Access the appropriate setting via the Properties.Settings.Default member.</span></span> <span data-ttu-id="30a18-107">En el ejemplo siguiente, se muestra cómo asignar un valor de configuración con el nombre `myColor` a una propiedad BackColor.</span><span class="sxs-lookup"><span data-stu-id="30a18-107">The following example shows how to assign a setting named `myColor` to a BackColor property.</span></span> <span data-ttu-id="30a18-108">Es necesario que haya creado previamente un archivo de configuración con una configuración denominada `myColor` de tipo `System.Drawing.Color`.</span><span class="sxs-lookup"><span data-stu-id="30a18-108">It requires you to have previously created a Settings file containing a setting named `myColor` of type `System.Drawing.Color`.</span></span> <span data-ttu-id="30a18-109">Para obtener información acerca de cómo crear un archivo [de configuración, consulte Cómo: Cree un nuevo valor de configuración en](how-to-create-a-new-setting-at-design-time.md)tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="30a18-109">For information about creating a Settings file, see [How To: Create a New Setting at Design Time](how-to-create-a-new-setting-at-design-time.md).</span></span>  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a><span data-ttu-id="30a18-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="30a18-110">See also</span></span>

- [<span data-ttu-id="30a18-111">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="30a18-111">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="30a18-112">Cómo: Escribir la configuración de usuario en tiempo de ejecución conC#</span><span class="sxs-lookup"><span data-stu-id="30a18-112">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="30a18-113">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="30a18-113">Application Settings Overview</span></span>](application-settings-overview.md)

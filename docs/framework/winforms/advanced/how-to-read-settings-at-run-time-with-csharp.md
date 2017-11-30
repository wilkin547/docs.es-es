---
title: "Cómo: Leer valores de configuración en tiempo de ejecución con C#"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c23fd88d33ff4ca480c435f2058f4c568320578
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-settings-at-run-time-with-c"></a><span data-ttu-id="bd15d-102">Cómo: Leer valores de configuración en tiempo de ejecución con C#</span><span class="sxs-lookup"><span data-stu-id="bd15d-102">How To: Read Settings at Run Time With C#</span></span> #
<span data-ttu-id="bd15d-103">Puede leer valores de configuración de aplicación y usuario en tiempo de ejecución a través del objeto Properties.</span><span class="sxs-lookup"><span data-stu-id="bd15d-103">You can read both Application-scoped and User-scoped settings at run time via the Properties object.</span></span> <span data-ttu-id="bd15d-104">El objeto Properties expone todos los valores de configuración predeterminados para el proyecto a través del miembro Properties.Settings.Default.</span><span class="sxs-lookup"><span data-stu-id="bd15d-104">The Properties object exposes all of the default settings for the project via the Properties.Settings.Default member.</span></span>  
  
### <a name="to-read-settings-at-run-time-with-c"></a><span data-ttu-id="bd15d-105">Para leer valores de configuración en tiempo de ejecución con C#</span><span class="sxs-lookup"><span data-stu-id="bd15d-105">To Read Settings at Run Time with C#</span></span>  
  
-   <span data-ttu-id="bd15d-106">Acceda a la configuración correspondiente a través del miembro Properties.Settings.Default. </span><span class="sxs-lookup"><span data-stu-id="bd15d-106">Access the appropriate setting via the Properties.Settings.Default member.</span></span> <span data-ttu-id="bd15d-107">En el ejemplo siguiente, se muestra cómo asignar un valor de configuración con el nombre `myColor` a una propiedad BackColor.</span><span class="sxs-lookup"><span data-stu-id="bd15d-107">The following example shows how to assign a setting named `myColor` to a BackColor property.</span></span> <span data-ttu-id="bd15d-108">Es necesario que haya creado previamente un archivo de configuración con una configuración denominada `myColor` de tipo `System.Drawing.Color`.</span><span class="sxs-lookup"><span data-stu-id="bd15d-108">It requires you to have previously created a Settings file containing a setting named `myColor` of type `System.Drawing.Color`.</span></span> <span data-ttu-id="bd15d-109">Para obtener información acerca de cómo crear un archivo de configuración, consulte [Cómo: crear una nueva configuración en tiempo de diseño](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="bd15d-109">For information about creating a Settings file, see [How To: Create a New Setting at Design Time](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).</span></span>  
  
    ```  
    // C#  
    this.BackColor = Properties.Settings.Default.myColor;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bd15d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd15d-110">See Also</span></span>  
 [<span data-ttu-id="bd15d-111">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="bd15d-111">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="bd15d-112">Escribir valores de configuración de usuario en tiempo de ejecución con C#</span><span class="sxs-lookup"><span data-stu-id="bd15d-112">How To: Write User Settings at Run Time with C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
 [<span data-ttu-id="bd15d-113">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="bd15d-113">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)

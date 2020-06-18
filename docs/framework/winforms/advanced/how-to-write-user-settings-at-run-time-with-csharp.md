---
title: Cómo escribir valores de configuración de usuario en tiempo de ejecución con C#
description: Obtenga información sobre cómo escribir valores de configuración en tiempo de ejecución con C# conservando los cambios en la configuración entre sesiones de aplicación llamando al método Save.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: 6154ff1b92d6c2d4c788299e59eb8f73e6b69c4b
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904330"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a><span data-ttu-id="e0cec-103">Cómo: escribir la configuración de usuario en tiempo de ejecución con C\#</span><span class="sxs-lookup"><span data-stu-id="e0cec-103">How To: Write User Settings at Run Time with C\#</span></span>

<span data-ttu-id="e0cec-104">La configuración del ámbito de aplicación es de solo lectura y únicamente se puede cambiar en tiempo de diseño o modificando el archivo .config entre sesiones de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0cec-104">Settings that are application-scoped are read-only, and can only be changed at design time or by altering the .config file in between application sessions.</span></span> <span data-ttu-id="e0cec-105">Sin embargo, la configuración del ámbito de usuario puede escribirse en tiempo de ejecución, del mismo modo que cambiaría cualquier valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="e0cec-105">Settings that are user-scoped, however, can be written at run time just as you would change any property value.</span></span> <span data-ttu-id="e0cec-106">El nuevo valor se conserva a lo largo de toda la sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0cec-106">The new value persists for the duration of the application session.</span></span> <span data-ttu-id="e0cec-107">Puede conservar los cambios de la configuración entre sesiones de aplicación llamando al método Save.</span><span class="sxs-lookup"><span data-stu-id="e0cec-107">You can persist the changes to the settings between application sessions by calling the Save method.</span></span>  
  
## <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a><span data-ttu-id="e0cec-108">Cómo: escribir y conservar la configuración de usuario en tiempo de ejecución con C\#</span><span class="sxs-lookup"><span data-stu-id="e0cec-108">How To: Write and Persist User Settings at Run Time with C\#</span></span>
  
1. <span data-ttu-id="e0cec-109">Acceda a la configuración y asigne un nuevo valor, tal como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e0cec-109">Access the setting and assign it a new value as shown in this example:</span></span>  
  
   ```csharp
   Properties.Settings.Default.myColor = Color.AliceBlue;  
   ```  
  
2. <span data-ttu-id="e0cec-110">Si desea conservar los cambios de la configuración entre sesiones de aplicación, llame al método Save tal como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e0cec-110">If you want to persist the changes to the settings between application sessions, call the Save method as shown in this example:</span></span>  
  
    ```csharp
    Properties.Settings.Default.Save();  
    ```  
  
<span data-ttu-id="e0cec-111">La configuración de usuario se guarda en un archivo en una subcarpeta de la carpeta de datos de aplicación oculta local del usuario.</span><span class="sxs-lookup"><span data-stu-id="e0cec-111">User settings are saved in a file within a subfolder of the user’s local hidden application data folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0cec-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e0cec-112">See also</span></span>

- [<span data-ttu-id="e0cec-113">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="e0cec-113">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="e0cec-114">Cómo leer valores de configuración en tiempo de ejecución con C#</span><span class="sxs-lookup"><span data-stu-id="e0cec-114">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="e0cec-115">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="e0cec-115">Application Settings Overview</span></span>](application-settings-overview.md)

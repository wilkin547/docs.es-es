---
title: 'Cómo: Escribir valores de configuración de usuario en tiempo de ejecución con C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: f289b6a6a4a726ffa6bb2c9df99c665e2872e8d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522300"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a><span data-ttu-id="6348f-102">Cómo: Escribir valores de configuración de usuario en tiempo de ejecución con C#</span><span class="sxs-lookup"><span data-stu-id="6348f-102">How To: Write User Settings at Run Time with C#</span></span> #
<span data-ttu-id="6348f-103">La configuración del ámbito de aplicación es de solo lectura y únicamente se puede cambiar en tiempo de diseño o modificando el archivo .config entre sesiones de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6348f-103">Settings that are application-scoped are read-only, and can only be changed at design time or by altering the .config file in between application sessions.</span></span> <span data-ttu-id="6348f-104">Sin embargo, la configuración del ámbito de usuario puede escribirse en tiempo de ejecución, del mismo modo que cambiaría cualquier valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="6348f-104">Settings that are user-scoped, however, can be written at run time just as you would change any property value.</span></span> <span data-ttu-id="6348f-105">El nuevo valor se conserva a lo largo de toda la sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6348f-105">The new value persists for the duration of the application session.</span></span> <span data-ttu-id="6348f-106">Puede conservar los cambios de la configuración entre sesiones de aplicación llamando al método Save.</span><span class="sxs-lookup"><span data-stu-id="6348f-106">You can persist the changes to the settings between application sessions by calling the Save method.</span></span>  
  
### <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a><span data-ttu-id="6348f-107">Cómo: Escribir y conservar valores de configuración de usuario en tiempo de ejecución con C#</span><span class="sxs-lookup"><span data-stu-id="6348f-107">How To: Write and Persist User Settings at Run Time with C#</span></span>  
  
1.  <span data-ttu-id="6348f-108">Acceda a la configuración y asigne un nuevo valor, tal como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6348f-108">Access the setting and assign it a new value as shown in this example:</span></span>  
  
    ```  
    // C#  
    Properties.Settings.Default.myColor = Color.AliceBlue;  
    ```  
  
2.  <span data-ttu-id="6348f-109">Si desea conservar los cambios de la configuración entre sesiones de aplicación, llame al método Save tal como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6348f-109">If you want to persist the changes to the settings between application sessions, call the Save method as shown in this example:</span></span>  
  
    ```  
    // C#  
    Properties.Settings.Default.Save();  
    ```  
  
     <span data-ttu-id="6348f-110">La configuración de usuario se guarda en un archivo en una subcarpeta de la carpeta de datos de aplicación oculta local del usuario.</span><span class="sxs-lookup"><span data-stu-id="6348f-110">User settings are saved in a file within a subfolder of the user’s local hidden application data folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6348f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6348f-111">See Also</span></span>  
 [<span data-ttu-id="6348f-112">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="6348f-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="6348f-113">Leer valores de configuración en tiempo de ejecución con C#</span><span class="sxs-lookup"><span data-stu-id="6348f-113">How To: Read Settings at Run Time With C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
 [<span data-ttu-id="6348f-114">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="6348f-114">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)

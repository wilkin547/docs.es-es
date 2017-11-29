---
title: "Cómo: Escribir valores de configuración de usuario en tiempo de ejecución con C#"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5966aef77c994d2657bd282ad15e8f59a64eeb47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a><span data-ttu-id="679cc-102">Cómo: Escribir valores de configuración de usuario en tiempo de ejecución con C#</span><span class="sxs-lookup"><span data-stu-id="679cc-102">How To: Write User Settings at Run Time with C#</span></span> #
<span data-ttu-id="679cc-103">La configuración del ámbito de aplicación es de solo lectura y únicamente se puede cambiar en tiempo de diseño o modificando el archivo .config entre sesiones de aplicación.</span><span class="sxs-lookup"><span data-stu-id="679cc-103">Settings that are application-scoped are read-only, and can only be changed at design time or by altering the .config file in between application sessions.</span></span> <span data-ttu-id="679cc-104">Sin embargo, la configuración del ámbito de usuario puede escribirse en tiempo de ejecución, del mismo modo que cambiaría cualquier valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="679cc-104">Settings that are user-scoped, however, can be written at run time just as you would change any property value.</span></span> <span data-ttu-id="679cc-105">El nuevo valor se conserva a lo largo de toda la sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="679cc-105">The new value persists for the duration of the application session.</span></span> <span data-ttu-id="679cc-106">Puede conservar los cambios de la configuración entre sesiones de aplicación llamando al método Save.</span><span class="sxs-lookup"><span data-stu-id="679cc-106">You can persist the changes to the settings between application sessions by calling the Save method.</span></span>  
  
### <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a><span data-ttu-id="679cc-107">Cómo: Escribir y conservar valores de configuración de usuario en tiempo de ejecución con C#</span><span class="sxs-lookup"><span data-stu-id="679cc-107">How To: Write and Persist User Settings at Run Time with C#</span></span>  
  
1.  <span data-ttu-id="679cc-108">Acceda a la configuración y asigne un nuevo valor, tal como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="679cc-108">Access the setting and assign it a new value as shown in this example:</span></span>  
  
    ```  
    // C#  
    Properties.Settings.Default.myColor = Color.AliceBlue;  
    ```  
  
2.  <span data-ttu-id="679cc-109">Si desea conservar los cambios de la configuración entre sesiones de aplicación, llame al método Save tal como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="679cc-109">If you want to persist the changes to the settings between application sessions, call the Save method as shown in this example:</span></span>  
  
    ```  
    // C#  
    Properties.Settings.Default.Save();  
    ```  
  
     <span data-ttu-id="679cc-110">La configuración de usuario se guarda en un archivo en una subcarpeta de la carpeta de datos de aplicación oculta local del usuario.</span><span class="sxs-lookup"><span data-stu-id="679cc-110">User settings are saved in a file within a subfolder of the user’s local hidden application data folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="679cc-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="679cc-111">See Also</span></span>  
 [<span data-ttu-id="679cc-112">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="679cc-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="679cc-113">Leer valores de configuración en tiempo de ejecución con C#</span><span class="sxs-lookup"><span data-stu-id="679cc-113">How To: Read Settings at Run Time With C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
 [<span data-ttu-id="679cc-114">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="679cc-114">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)

---
title: "Cómo: Cambiar el valor de una opción de configuración entre sesiones de aplicación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2dff90e499ce421f372137903daf34c09c21d5c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="6aa28-102">Cómo: Cambiar el valor de una opción de configuración entre sesiones de aplicación</span><span class="sxs-lookup"><span data-stu-id="6aa28-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="6aa28-103">En ocasiones, puede cambiar el valor de una configuración entre sesiones de aplicación después de que se ha compilado e implementada la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6aa28-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="6aa28-104">Por ejemplo, puede cambiar una cadena de conexión para que señale a la ubicación de la base de datos correcta.</span><span class="sxs-lookup"><span data-stu-id="6aa28-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="6aa28-105">Puesto que las herramientas de tiempo de diseño no están disponibles después de que se ha compilado e implementada la aplicación, debe cambiar el valor de configuración manualmente en el archivo.</span><span class="sxs-lookup"><span data-stu-id="6aa28-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="6aa28-106">Para cambiar el valor de una configuración entre sesiones de aplicación</span><span class="sxs-lookup"><span data-stu-id="6aa28-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="6aa28-107">Con Microsoft Notepad o algún otro texto o editor XML, abra el archivo .config asociado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6aa28-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="6aa28-108">Busque la entrada para la configuración que desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="6aa28-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="6aa28-109">Debe ser similar al ejemplo presentado a continuación.</span><span class="sxs-lookup"><span data-stu-id="6aa28-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="6aa28-110">Escriba un nuevo valor para la configuración y guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="6aa28-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa28-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6aa28-111">See Also</span></span>  
 [<span data-ttu-id="6aa28-112">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="6aa28-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="6aa28-113">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="6aa28-113">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)

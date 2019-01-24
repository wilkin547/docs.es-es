---
title: Cómo Cambie el valor de una configuración entre sesiones de aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 475e57e8bfdd5f3296c6af0fb20a472c729ea75c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540720"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="f7361-102">Cómo Cambie el valor de una configuración entre sesiones de aplicación</span><span class="sxs-lookup"><span data-stu-id="f7361-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="f7361-103">En ocasiones, es posible que desea cambiar el valor de una configuración entre sesiones de aplicación después de compilar e implementada la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7361-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="f7361-104">Por ejemplo, es posible que desee cambiar una cadena de conexión para que apunte a la ubicación de la base de datos correcta.</span><span class="sxs-lookup"><span data-stu-id="f7361-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="f7361-105">Dado que las herramientas de tiempo de diseño no están disponibles después de compilar e implementada la aplicación, debe cambiar el valor de configuración manualmente en el archivo.</span><span class="sxs-lookup"><span data-stu-id="f7361-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="f7361-106">Para cambiar el valor de una configuración entre sesiones de aplicación</span><span class="sxs-lookup"><span data-stu-id="f7361-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="f7361-107">Con Microsoft Notepad o algún otro editor XML o texto, abra el archivo .config asociado con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7361-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="f7361-108">Busque la entrada para la configuración que desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="f7361-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="f7361-109">Debe ser similar al ejemplo presentado a continuación.</span><span class="sxs-lookup"><span data-stu-id="f7361-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="f7361-110">Escriba un nuevo valor para la configuración y guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="f7361-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7361-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7361-111">See also</span></span>
- [<span data-ttu-id="f7361-112">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="f7361-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)
- [<span data-ttu-id="f7361-113">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f7361-113">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)

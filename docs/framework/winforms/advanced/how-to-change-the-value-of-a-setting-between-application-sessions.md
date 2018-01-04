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
ms.workload: dotnet
ms.openlocfilehash: c00e61001d9c8877b1fcaa0e938c92249c7915e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>Cómo: Cambiar el valor de una opción de configuración entre sesiones de aplicación
En ocasiones, puede cambiar el valor de una configuración entre sesiones de aplicación después de que se ha compilado e implementada la aplicación. Por ejemplo, puede cambiar una cadena de conexión para que señale a la ubicación de la base de datos correcta. Puesto que las herramientas de tiempo de diseño no están disponibles después de que se ha compilado e implementada la aplicación, debe cambiar el valor de configuración manualmente en el archivo.  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>Para cambiar el valor de una configuración entre sesiones de aplicación  
  
1.  Con Microsoft Notepad o algún otro texto o editor XML, abra el archivo .config asociado a la aplicación.  
  
2.  Busque la entrada para la configuración que desea cambiar. Debe ser similar al ejemplo presentado a continuación.  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  Escriba un nuevo valor para la configuración y guarde el archivo.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar valores de configuración de aplicación y de usuario](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Introducción a la configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-overview.md)

---
title: 'Cómo: Cambiar el valor de una opción de configuración entre sesiones de aplicación'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 383f72f223fb92170d16a9538c94e67825009abb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
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

---
title: Cómo Cambie el valor de una configuración entre sesiones de aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: c1626cea581e5c180665d0ce805dea3e67f27a05
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714364"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>Cómo Cambie el valor de una configuración entre sesiones de aplicación
En ocasiones, es posible que desea cambiar el valor de una configuración entre sesiones de aplicación después de compilar e implementada la aplicación. Por ejemplo, es posible que desee cambiar una cadena de conexión para que apunte a la ubicación de la base de datos correcta. Dado que las herramientas de tiempo de diseño no están disponibles después de compilar e implementada la aplicación, debe cambiar el valor de configuración manualmente en el archivo.  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>Para cambiar el valor de una configuración entre sesiones de aplicación  
  
1.  Con Microsoft Notepad o algún otro editor XML o texto, abra el archivo .config asociado con la aplicación.  
  
2.  Busque la entrada para la configuración que desee cambiar. Debe ser similar al ejemplo presentado a continuación.  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  Escriba un nuevo valor para la configuración y guarde el archivo.  
  
## <a name="see-also"></a>Vea también
- [Utilizar valores de configuración de aplicación y de usuario](using-application-settings-and-user-settings.md)
- [Introducción a la configuración de la aplicación](application-settings-overview.md)

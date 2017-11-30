---
title: My.Settings (Objeto)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords: My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f744460f8ea6c6c7f5c8c5e1658bd357e910def
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="mysettings-object"></a>My.Settings (Objeto)
Proporciona propiedades y métodos para tener acceso a la configuración de la aplicación.  
  
## <a name="remarks"></a>Comentarios  
 La `My.Settings` objeto proporciona acceso a la configuración de la aplicación y permite almacenar y recuperar valores de propiedad y otra información para la aplicación de forma dinámica. Para obtener más información, consulte [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Propiedades  
 Las propiedades del objeto `My.Settings` proporcionan acceso a la configuración de la aplicación. Para agregar o quitar la configuración, utilice la **Diseñador de configuración**.  
  
 Cada valor tiene un **nombre**, **tipo**, **ámbito**, y **valor**, y estos valores determinan cómo la propiedad para tener acceso a cada configuración aparece en la `My.Settings` objeto:  
  
-   **Nombre** determina el nombre de la propiedad.  
  
-   **Tipo** determina el tipo de la propiedad.  
  
-   **Ámbito** indica si la propiedad es de solo lectura. Si el valor es **aplicación**, la propiedad es de solo lectura; si el valor es **usuario**, la propiedad es de lectura y escritura.  
  
-   **Valor** es el valor predeterminado de la propiedad.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|---|---|  
|`Reload`|Vuelve a cargar la configuración de usuario de los últimos valores guardados.|  
|`Save`|Guarda la configuración del usuario actual.|  
  
 El `My.Settings` objeto también proporciona propiedades avanzadas y métodos, heredados de la <xref:System.Configuration.ApplicationSettingsBase> clase.  
  
## <a name="tasks"></a>Tareas  
 En la tabla siguiente se muestra ejemplos de tareas que implican la `My.Settings` objeto.  
  
|Para|Vea|  
|---|---|  
|Leer la configuración de la aplicación|[Cómo: Leer la configuración de la aplicación en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Cambiar una configuración de usuario|[Cómo: Cambiar la configuración del usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Conservar la configuración de usuario|[Cómo: Conservar la configuración del usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Crear una cuadrícula de propiedades para la configuración de usuario|[Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra el valor de la configuración `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]  
  
 Para que este ejemplo funcione, la aplicación debe tener una configuración `Nickname` de tipo `String`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Configuration.ApplicationSettingsBase>  
 [Cómo: Leer la configuración de la aplicación en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [Cómo: Cambiar la configuración del usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [Cómo: Conservar la configuración del usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet)

---
title: "My.Settings (Objeto) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "My.MySettingsProperty.Settings"
  - "My.Settings"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Settings (objeto)"
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# My.Settings (Objeto)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Proporciona propiedades y métodos para acceder a la configuración de la aplicación.  
  
## <a name="remarks"></a>Comentarios  
 La `My.Settings` objeto proporciona acceso a la configuración de la aplicación y permite almacenar y recuperar valores de propiedad y otra información de la aplicación de forma dinámica. Para obtener más información, consulte [administración de configuración (. NET)](/visual-studio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Propiedades  
 Las propiedades de la `My.Settings` objeto proporcionan acceso a la configuración de la aplicación. Para agregar o quitar la configuración, utilice la **Diseñador de configuración**.  
  
 Cada valor tiene un **nombre**, **tipo**, **ámbito**, y **valor**, y estos valores determinan cómo aparece en la propiedad para tener acceso a cada configuración de la `My.Settings` objeto:  
  
-   **Nombre** determina el nombre de la propiedad.  
  
-   **Tipo** determina el tipo de la propiedad.  
  
-   **Ámbito** indica si la propiedad es de sólo lectura. Si el valor es **aplicación**, la propiedad es de solo lectura; si el valor es **usuario**, la propiedad es de lectura y escritura.  
  
-   **Valor** es el valor predeterminado de la propiedad.  
  
## <a name="methods"></a>Métodos  
  
|||  
|-|-|  
|Método|Descripción|  
|`Reload`|Vuelve a cargar la configuración de usuario de los últimos valores guardados.|  
|`Save`|Guarda la configuración actual del usuario.|  
  
 La `My.Settings` objeto también proporciona propiedades avanzadas y métodos, heredados de la <xref:System.Configuration.ApplicationSettingsBase> clase.  
  
## <a name="tasks"></a>Tareas  
 En la tabla siguiente muestra ejemplos de tareas que implican la `My.Settings` objeto.  
  
|||  
|-|-|  
|Para|Vea|  
|Leer la configuración de la aplicación|[Cómo: leer la configuración de la aplicación en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Cambiar una configuración de usuario|[Cómo: cambiar la configuración de usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Conservar la configuración de usuario|[Cómo: conservar la configuración de usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Crear una cuadrícula de propiedades para la configuración de usuario|[Cómo: crear cuadrículas de propiedades para la configuración de usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo muestra el valor de la `Nickname` configuración.  
  
 [!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/visualbasic/VbVbalrMyResources2/Form1.vb#14)]  
  
 Para que funcione este ejemplo, la aplicación debe tener un `Nickname` Configuración del tipo de `String`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Configuration.ApplicationSettingsBase>   
 [Cómo: leer la configuración de la aplicación en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Cómo: cambiar la configuración de usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [Cómo: conservar la configuración de usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Cómo: crear cuadrículas de propiedades para la configuración de usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Administrar la configuración de la aplicación (. NET)](/visual-studio/ide/managing-application-settings-dotnet)
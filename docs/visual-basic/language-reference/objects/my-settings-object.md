---
title: My.Settings (objeto) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
dev_langs:
- VB
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d48d3556f55ef286e2f501e2df5bf5035d3aff90
ms.lasthandoff: 03/13/2017

---
# <a name="mysettings-object"></a>My.Settings (Objeto)
Proporciona propiedades y métodos para acceder a la configuración de la aplicación.  
  
## <a name="remarks"></a>Comentarios  
 La `My.Settings` objeto proporciona acceso a la configuración de la aplicación y permite almacenar y recuperar valores de propiedad y otra información de la aplicación de forma dinámica. Para obtener más información, consulte [administración de configuración (. NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Propiedades  
 Las propiedades de la `My.Settings` objeto proporcionan acceso a la configuración de la aplicación. Para agregar o quitar la configuración, utilice la **Diseñador de configuración**.  
  
 Cada valor tiene un **nombre**, **tipo**, **ámbito**, y **valor**, y estos valores determinan cómo aparece en la propiedad para tener acceso a cada configuración de la `My.Settings` objeto:  
  
-   **Nombre** determina el nombre de la propiedad.  
  
-   **Tipo** determina el tipo de la propiedad.  
  
-   **Ámbito** indica si la propiedad es de sólo lectura. Si el valor es **aplicación**, la propiedad es de solo lectura; si el valor es **usuario**, la propiedad es de lectura y escritura.  
  
-   **Valor** es el valor predeterminado de la propiedad.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|---|---|  
|`Reload`|Vuelve a cargar la configuración de usuario de los últimos valores guardados.|  
|`Save`|Guarda la configuración actual del usuario.|  
  
 El `My.Settings` objeto también proporciona propiedades avanzadas y métodos, heredados de la <xref:System.Configuration.ApplicationSettingsBase>clase.</xref:System.Configuration.ApplicationSettingsBase>  
  
## <a name="tasks"></a>Tareas  
 En la tabla siguiente muestra ejemplos de tareas que implican la `My.Settings` objeto.  
  
|Para|Vea|  
|---|---|  
|Leer la configuración de la aplicación|[Cómo: leer la configuración de la aplicación en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Cambiar una configuración de usuario|[Cómo: cambiar la configuración de usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Conservar la configuración de usuario|[Cómo: conservar la configuración de usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Crear una cuadrícula de propiedades para la configuración de usuario|[Cómo: crear cuadrículas de propiedades para la configuración de usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo muestra el valor de la `Nickname` configuración.  
  
 [!code-vb[VbVbalrMyResources&#14;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]  
  
 Para que funcione este ejemplo, la aplicación debe tener un `Nickname` configuración del tipo de `String`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Configuration.ApplicationSettingsBase></xref:System.Configuration.ApplicationSettingsBase>   
 [Cómo: leer la configuración de la aplicación en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Cómo: cambiar la configuración de usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [Cómo: conservar la configuración de usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Cómo: crear cuadrículas de propiedades para la configuración de usuario en Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Administrar la configuración de la aplicación (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)

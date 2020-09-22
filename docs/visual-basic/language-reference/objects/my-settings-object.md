---
title: My.Settings (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: f3348e9eea5bdd7f4fd911150877c9aefdd66bcc
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867300"
---
# <a name="mysettings-object"></a>My.Settings (Objeto)

Proporciona propiedades y métodos para tener acceso a la configuración de la aplicación.  
  
## <a name="remarks"></a>Comentarios  

 El `My.Settings` objeto proporciona acceso a la configuración de la aplicación y permite almacenar y recuperar dinámicamente la configuración de propiedades y otra información de la aplicación. Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Propiedades  

 Las propiedades del objeto `My.Settings` proporcionan acceso a la configuración de la aplicación. Para agregar o quitar la configuración, use el **Diseñador de configuración**.  
  
 Cada configuración tiene un **nombre**, **tipo**, **ámbito**y **valor**, y esta configuración determina cómo aparece la propiedad para tener acceso a cada configuración en el `My.Settings` objeto:  
  
- **Nombre** determina el nombre de la propiedad.  
  
- **Tipo** determina el tipo de la propiedad.  
  
- El **ámbito** indica si la propiedad es de solo lectura. Si el valor es **Application**, la propiedad es de solo lectura; Si el valor es **User**, la propiedad es de lectura y escritura.  
  
- **Value** es el valor predeterminado de la propiedad.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|---|---|  
|`Reload`|Vuelve a cargar la configuración de usuario de los últimos valores guardados.|  
|`Save`|Guarda la configuración del usuario actual.|  
  
 El `My.Settings` objeto también proporciona propiedades y métodos avanzados, heredados de la <xref:System.Configuration.ApplicationSettingsBase> clase.  
  
## <a name="tasks"></a>Tareas  

 En la tabla siguiente se muestran ejemplos de tareas que implican el `My.Settings` objeto.  
  
|En|Vea|  
|---|---|  
|Leer una configuración de la aplicación|[Cómo: Leer la configuración de la aplicación en Visual Basic](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Cambiar la configuración de un usuario|[Cómo: Cambiar la configuración del usuario en Visual Basic](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Conservar la configuración de usuario|[Cómo: Conservar la configuración del usuario en Visual Basic](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Crear una cuadrícula de propiedades para la configuración del usuario|[Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se muestra el valor de la configuración `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 Para que este ejemplo funcione, la aplicación debe tener una configuración `Nickname` de tipo `String`.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Configuration.ApplicationSettingsBase>
- [Cómo: Leer la configuración de la aplicación en Visual Basic](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [Cómo: Cambiar la configuración del usuario en Visual Basic](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [Cómo: Conservar la configuración del usuario en Visual Basic](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet)

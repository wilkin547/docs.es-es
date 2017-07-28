---
title: "Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Settings object, creating property grids for user settings
- user settings, creating property grids
- property grids, creating for user settings
- property grids
ms.assetid: b0bc737e-50d1-43d1-a6df-268db6e6f91c
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c21b458f9c28f4d25e5b0d8099b9a5255f31ac52
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-property-grids-for-user-settings-in-visual-basic"></a>Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic
Una cuadrícula de propiedades para la configuración del usuario se crea rellenando un control <xref:System.Windows.Forms.PropertyGrid> con las propiedades de configuración de usuario del objeto `My.Settings`.  
  
> [!NOTE]
>  Para que funcione este ejemplo, la aplicación debe tener configurados los ajustes del usuario. Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
 El objeto `My.Settings` expone cada configuración como una propiedad. El nombre de propiedad es el mismo que el nombre de la configuración y el tipo de propiedad es el mismo que el tipo de configuración. El **Ámbito** de la configuración determina si la propiedad es de solo lectura. La propiedad de una configuración con ámbito **Aplicación** es de solo lectura, mientras que la propiedad de una configuración con ámbito **Usuario** es de lectura y escritura. Para obtener más información, vea [My.Settings (Objeto)](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  No se pueden cambiar ni guardar los valores de configuración de ámbito de aplicación en tiempo de ejecución. Las configuraciones con ámbito de aplicación únicamente se pueden cambiar al crear la aplicación (mediante el **Diseñador de proyectos**) o editando el archivo de configuración de la aplicación. Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
 Este ejemplo usa un control <xref:System.Windows.Forms.PropertyGrid> para acceder a las propiedades de configuración de usuario del objeto `My.Settings`. De forma predeterminada, <xref:System.Windows.Forms.PropertyGrid> muestra todas las propiedades del objeto `My.Settings`. Sin embargo, las propiedades de configuración de usuario tienen el atributo <xref:System.Configuration.UserScopedSettingAttribute>. Este ejemplo establece la propiedad <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> de <xref:System.Windows.Forms.PropertyGrid> en <xref:System.Configuration.UserScopedSettingAttribute> para mostrar solo las propiedades de configuración de usuario.  
  
### <a name="to-add-a-user-setting-property-grid"></a>Para agregar una cuadrícula de propiedades de configuración de usuario  
  
1.  Agregue el control **PropertyGrid** desde el **Cuadro de herramientas** a la superficie de diseño de la aplicación, que aquí se da por supuesto que es `Form1`.  
  
     El nombre predeterminado del control de cuadrícula de propiedades es `PropertyGrid1`.  
  
2.  Haga doble clic en la superficie de diseño de `Form1` para abrir el código del controlador de eventos de carga del formulario.  
  
3.  Establezca el objeto `My.Settings` como el objeto seleccionado para la cuadrícula de propiedades.  
  
     [!code-vb[VbVbalrMyResources#11](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_1.vb)]  
  
4.  Configure la cuadrícula de propiedades para que solo muestre la configuración de usuario.  
  
     [!code-vb[VbVbalrMyResources#12](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_2.vb)]  
  
    > [!NOTE]
    >  Para mostrar solo la configuración del ámbito de aplicación, utilice el atributo <xref:System.Configuration.ApplicationScopedSettingAttribute> en lugar de <xref:System.Configuration.UserScopedSettingAttribute>.  
  
## <a name="robust-programming"></a>Programación sólida  
 La aplicación guarda la configuración del usuario cuando se cierra. Para guardar la configuración inmediatamente, llame al método `My.Settings.Save`. Para obtener más información, vea [Cómo: Conservar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).  
  
## <a name="see-also"></a>Vea también  
 [My.Settings (Objeto)](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Cómo: Leer la configuración de la aplicación en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Cómo: Cambiar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [Cómo: Conservar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet)


---
description: 'Más información acerca de: Procedimiento: para crear cuadrículas de propiedades para la configuración del usuario en Visual Basic'
title: Procedimiento para crear cuadrículas de propiedades para la configuración del usuario
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], creating property grids for user settings
- user settings [Visual Basic], creating property grids
- property grids [Visual Basic], creating for user settings
- property grids
ms.assetid: b0bc737e-50d1-43d1-a6df-268db6e6f91c
ms.openlocfilehash: 19523f712207cac225ccf68e02e338a9e76fe358
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797853"
---
# <a name="how-to-create-property-grids-for-user-settings-in-visual-basic"></a>Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic

Una cuadrícula de propiedades para la configuración del usuario se crea rellenando un control <xref:System.Windows.Forms.PropertyGrid> con las propiedades de configuración de usuario del objeto `My.Settings`.  
  
> [!NOTE]
> Para que funcione este ejemplo, la aplicación debe tener configurados los ajustes del usuario. Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
 El objeto `My.Settings` expone cada configuración como una propiedad. El nombre de propiedad es el mismo que el nombre de la configuración y el tipo de propiedad es el mismo que el tipo de configuración. El **Ámbito** de la configuración determina si la propiedad es de solo lectura. La propiedad de una configuración con ámbito **Aplicación** es de solo lectura, mientras que la propiedad de una configuración con ámbito **Usuario** es de lectura y escritura. Para obtener más información, vea [My.Settings (Objeto)](../../../language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
> No se pueden cambiar ni guardar los valores de configuración de ámbito de aplicación en tiempo de ejecución. Las configuraciones con ámbito de aplicación únicamente se pueden cambiar al crear la aplicación (mediante el **Diseñador de proyectos**) o editando el archivo de configuración de la aplicación. Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
 Este ejemplo usa un control <xref:System.Windows.Forms.PropertyGrid> para acceder a las propiedades de configuración de usuario del objeto `My.Settings`. De forma predeterminada, <xref:System.Windows.Forms.PropertyGrid> muestra todas las propiedades del objeto `My.Settings`. Sin embargo, las propiedades de configuración de usuario tienen el atributo <xref:System.Configuration.UserScopedSettingAttribute>. Este ejemplo establece la propiedad <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> de <xref:System.Windows.Forms.PropertyGrid> en <xref:System.Configuration.UserScopedSettingAttribute> para mostrar solo las propiedades de configuración de usuario.  
  
### <a name="to-add-a-user-setting-property-grid"></a>Para agregar una cuadrícula de propiedades de configuración de usuario  
  
1. Agregue el control **PropertyGrid** desde el **Cuadro de herramientas** a la superficie de diseño de la aplicación, que aquí se da por supuesto que es `Form1`.  
  
     El nombre predeterminado del control de cuadrícula de propiedades es `PropertyGrid1`.  
  
2. Haga doble clic en la superficie de diseño de `Form1` para abrir el código del controlador de eventos de carga del formulario.  
  
3. Establezca el objeto `My.Settings` como el objeto seleccionado para la cuadrícula de propiedades.  
  
     [!code-vb[VbVbalrMyResources#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#11)]  
  
4. Configure la cuadrícula de propiedades para que solo muestre la configuración de usuario.  
  
     [!code-vb[VbVbalrMyResources#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#12)]  
  
    > [!NOTE]
    > Para mostrar solo la configuración del ámbito de aplicación, utilice el atributo <xref:System.Configuration.ApplicationScopedSettingAttribute> en lugar de <xref:System.Configuration.UserScopedSettingAttribute>.  
  
## <a name="robust-programming"></a>Programación sólida  

 La aplicación guarda la configuración del usuario cuando se cierra. Para guardar la configuración inmediatamente, llame al método `My.Settings.Save`. Para obtener más información, vea [Cómo: Conservar la configuración del usuario en Visual Basic](how-to-persist-user-settings.md).  
  
## <a name="see-also"></a>Vea también

- [My.Settings (objeto)](../../../language-reference/objects/my-settings-object.md)
- [Cómo: Leer la configuración de la aplicación en Visual Basic](how-to-read-application-settings.md)
- [Cómo: Cambiar la configuración del usuario en Visual Basic](how-to-change-user-settings.md)
- [Cómo: Conservar la configuración del usuario en Visual Basic](how-to-persist-user-settings.md)
- [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet)

---
title: 'Cómo: Crear la configuración de la aplicación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], creating
ms.assetid: 1e7aa347-af75-41e5-89ca-f53cab704f72
ms.openlocfilehash: 7a84fc85b42f2b78ccafcae3c815847633b9916d
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43744421"
---
# <a name="how-to-create-application-settings"></a>Cómo: Crear la configuración de la aplicación
Usando código administrado, puede crear una nueva opción de configuración de la aplicación y enlazarla a las propiedades o a los controles del formulario para que esta opción de configuración se cargue y se guarde automáticamente en tiempo de ejecución.  
  
 En el siguiente procedimiento, creará manualmente una clase contenedora que deriva de <xref:System.Configuration.ApplicationSettingsBase>. A esta clase se agrega una propiedad públicamente accesible para cada opción de configuración de la aplicación que desee exponer.  
  
 También puede realizar este procedimiento con un mínimo de código en el diseñador de Visual Studio.  Consulte también [Cómo: crear configuración de aplicación mediante el diseñador](https://msdn.microsoft.com/library/wabtadw6\(v=vs.110\)).  
  
### <a name="to-create-new-application-settings-programmatically"></a>Para crear una nueva opción de configuración de la aplicación mediante programación  
  
1.  Agregue una nueva clase al proyecto y cámbiele el nombre. Para este procedimiento, llamaremos a esta clase `MyUserSettings`. Cambie la definición de clase para que la clase derive de <xref:System.Configuration.ApplicationSettingsBase>.  
  
2.  Defina una propiedad en esta clase contenedora para cada opción de configuración de la aplicación que necesite y aplique esa propiedad con los atributos <xref:System.Configuration.ApplicationScopedSettingAttribute> o <xref:System.Configuration.UserScopedSettingAttribute>, según el ámbito de la opción de configuración. Para obtener más información acerca del ámbito de configuración, consulte [Application Settings Overview](../../../../docs/framework/winforms/advanced/application-settings-overview.md). En este momento, el código debe ser similar al siguiente:  
  
     [!code-csharp[ApplicationSettings.Create#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
     [!code-vb[ApplicationSettings.Create#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
3.  Cree una instancia de esta clase contenedora en la aplicación. Normalmente será un miembro privado del formulario principal. Ahora que ha definido la clase, necesita enlazarla a una propiedad; en este caso, la propiedad <xref:System.Windows.Forms.Form.BackColor%2A> del formulario. Puede hacerlo en el formulario `Load` controlador de eventos.  
  
     [!code-csharp[ApplicationSettings.Create#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#2)]
     [!code-vb[ApplicationSettings.Create#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#2)]  
  
4.  Si proporciona una manera de cambiar la configuración en tiempo de ejecución, tendrá que guardar la configuración actual del usuario en el disco cuando el formulario se cierre o los cambios se perderán.  
  
     [!code-csharp[ApplicationSettings.Create#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#3)]
     [!code-vb[ApplicationSettings.Create#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#3)]  
  
     Ya ha creado una nueva opción de configuración de la aplicación y la ha enlazado a la propiedad especificada.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 El proveedor de configuración predeterminado, <xref:System.Configuration.LocalFileSettingsProvider>, conserva la información en archivos de configuración como texto sin formato. Esto limita la seguridad a la seguridad de acceso a archivos proporcionada por el sistema operativo para el usuario actual. Por este motivo, debe tener cuidado con la información almacenada en los archivos de configuración. Por ejemplo, un uso común de la configuración de la aplicación es almacenar cadenas de conexión que apuntan al almacén de datos de la aplicación. Sin embargo, por motivos de seguridad, esas cadenas no deberían incluir contraseñas. Para obtener más información sobre las cadenas de conexión, consulte <xref:System.Configuration.SpecialSetting>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Configuration.SpecialSettingAttribute>  
 <xref:System.Configuration.LocalFileSettingsProvider>  
 [Introducción a la configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [Validar la configuración de la aplicación](../../../../docs/framework/winforms/advanced/how-to-validate-application-settings.md)

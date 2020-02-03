---
title: Consideraciones de seguridad adicionales
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, secure calls to Windows API
- security [Windows Forms]
- security [Windows Forms], calling APIs
- Clipboard [Windows Forms], securing access
ms.assetid: 15abda8b-0527-47c7-aedb-77ab595f2bf1
ms.openlocfilehash: c8d51a57194f1dc536bc4b5d0376987dbfd3b2cf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739808"
---
# <a name="additional-security-considerations-in-windows-forms"></a>Consideraciones de seguridad adicionales en Windows Forms
.NET Framework configuración de seguridad puede hacer que la aplicación se ejecute de forma diferente en un entorno de confianza parcial que en el equipo local. En el .NET Framework se restringe el acceso a los recursos locales críticos como el sistema de archivos, la red y las API no administradas, entre otras cosas. La configuración de seguridad afecta a la capacidad de llamar a la API de Microsoft Windows u otras API que el sistema de seguridad no puede comprobar. La seguridad afecta también a otros aspectos de la aplicación, incluido el acceso a archivos y datos y su impresión. Para más información sobre el acceso a archivos y datos en un entorno de confianza parcial, consulte [Acceso más seguro a archivos y datos en Windows Forms](more-secure-file-and-data-access-in-windows-forms.md). Para más información sobre cómo imprimir en un entorno de confianza parcial, consulte [Impresión más segura en Windows Forms](more-secure-printing-in-windows-forms.md).  
  
 En las secciones siguientes se explica cómo trabajar con el portapapeles, realizar la manipulación de ventanas y llamar a la API de Windows desde aplicaciones que se ejecutan en un entorno de confianza parcial.  
  
## <a name="clipboard-access"></a>Acceso al Portapapeles  
 La clase <xref:System.Security.Permissions.UIPermission> controla el acceso al portapapeles y el valor de enumeración <xref:System.Security.Permissions.UIPermissionClipboard> asociado indica el nivel de acceso. En la tabla siguiente se muestran los niveles de permiso posibles.  
  
|Valor UIPermissionClipboard|Descripción|  
|---------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard>|El Portapapeles se puede utilizar sin límites.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard>|El Portapapeles se puede utilizar con ciertas limitaciones. La capacidad de colocar datos en el Portapapeles (operaciones del comando Copiar o Cortar) no está limitada. Los controles intrínsecos que acepten Pegar, como un cuadro de texto, pueden aceptar datos del Portapapeles, pero los controles de usuario no pueden leer el Portapapeles mediante programación.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.NoClipboard>|No se puede usar el Portapapeles.|  
  
 De forma predeterminada, la zona Intranet local recibe el acceso <xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard> y la zona Internet recibe <xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard> acceso. Esto significa que la aplicación puede copiar datos en el Portapapeles, pero no puede leer el Portapapeles ni pegar datos en él mediante programación. Estas limitaciones impiden que los programas que no sean de plena confianza lean el contenido copiado en el Portapapeles por otra aplicación. Si la aplicación requiere acceso total al Portapapeles pero no tiene los permisos necesarios, deberá conceder dichos permisos a la aplicación. Para más información sobre la elevación de permisos, vea [Administración general de directivas de seguridad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100)).  
  
## <a name="window-manipulation"></a>Manipulación de ventanas  
 La clase <xref:System.Security.Permissions.UIPermission> controla también el permiso para realizar la manipulación de ventanas y otras acciones relacionadas con la interfaz de usuario, y el valor de enumeración <xref:System.Security.Permissions.UIPermissionWindow> asociado indica el nivel de acceso. En la tabla siguiente se muestran los niveles de permiso posibles.  
  
 De forma predeterminada, la zona Intranet local recibe el acceso <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> y la zona Internet recibe <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> acceso. Esto significa que, en la zona Internet, la aplicación puede realizar la mayoría de las operaciones de ventanas de la interfaz de usuario, pero se modificará la apariencia de la ventana. La ventana modificada muestra una notificación en un globo la primera vez que se ejecuta, contiene el texto de la barra de título modificada y requiere un botón Cerrar en la barra de título. La notificación del globo y la barra de título informan al usuario de la aplicación que esta se está ejecutando bajo confianza parcial.  
  
|Valor UIPermissionWindow|Descripción|  
|------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionWindow.AllWindows>|Los usuarios pueden utilizar todas las ventanas y eventos de entrada de usuario sin restricciones.|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows>|Los usuarios solo pueden utilizar ventanas de nivel superior y ventanas secundarias más seguras para dibujar, y solo pueden utilizar eventos de entrada de datos del usuario para la interfaz de usuario dentro de dichas ventanas de nivel superior y ventanas secundarias. Estas ventanas más seguras están claramente etiquetadas y tienen restricciones de tamaño máximo y mínimo. Las restricciones impiden ataques de suplantación potencialmente perjudiciales, como la imitación de pantallas de inicio de sesión del sistema o el escritorio del sistema, y restringe el acceso mediante programación a las ventanas principales, las API relacionadas con el foco y el uso del control de <xref:System.Windows.Forms.ToolTip>.|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows>|Los usuarios solo pueden utilizar ventanas secundarias más seguras para dibujar, y solo pueden utilizar eventos de entrada del usuario para la interfaz de usuario dentro de esa ventana secundaria. Un control mostrado en un explorador es un ejemplo de una ventana secundaria más segura.|  
|<xref:System.Security.Permissions.UIPermissionWindow.NoWindows>|Los usuarios no pueden utilizar ninguna ventana ni ningún evento de interfaz de usuario. No se puede utilizar ninguna interfaz de usuario.|  
  
 Cada nivel de permiso identificado por la enumeración <xref:System.Security.Permissions.UIPermissionWindow> permite menos acciones que el nivel superior. En las tablas siguientes se indican las acciones restringidas por los valores <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> y <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows>. Para saber los permisos exactos necesarios para cada miembro, consulte el material de referencia de dicho miembro en la documentación de la biblioteca de clases de .NET Framework.  
  
 <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> permiso restringe las acciones que se muestran en la tabla siguiente.  
  
|Componente|Acciones restringidas|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.Application>|-   Establecer la propiedad <xref:System.Windows.Forms.Application.SafeTopLevelCaptionFormat%2A>.|  
|<xref:System.Windows.Forms.Control>|-Obteniendo la propiedad <xref:System.Windows.Forms.Control.Parent%2A>.<br />-   Establecer la propiedad `Region`.<br />-Llamando al método <xref:System.Windows.Forms.Control.FindForm%2A>, <xref:System.Windows.Forms.Control.Focus%2A>, <xref:System.Windows.Forms.Control.FromChildHandle%2A> y <xref:System.Windows.Forms.Control.FromHandle%2A>, <xref:System.Windows.Forms.Control.PreProcessMessage%2A>, <xref:System.Windows.Forms.Control.ReflectMessage%2A>o <xref:System.Windows.Forms.Control.SetTopLevel%2A>.<br />-Llamar al método <xref:System.Windows.Forms.Control.GetChildAtPoint%2A> si el control devuelto no es un elemento secundario del control que realiza la llamada.<br />-   Modificar el foco en un control contenedor.|  
|<xref:System.Windows.Forms.Cursor>|-   Establecer la propiedad <xref:System.Windows.Forms.Cursor.Clip%2A>.<br />-Llamando al método <xref:System.Windows.Forms.Control.Hide%2A>.|  
|<xref:System.Windows.Forms.DataGrid>|-Llamando al método <xref:System.Windows.Forms.ContainerControl.ProcessTabKey%2A>.|  
|<xref:System.Windows.Forms.Form>|-Obteniendo la propiedad <xref:System.Windows.Forms.Form.ActiveForm%2A> o <xref:System.Windows.Forms.Form.MdiParent%2A>.<br />-Establecer la propiedad <xref:System.Windows.Forms.Form.ControlBox%2A>, <xref:System.Windows.Forms.Form.ShowInTaskbar%2A>o <xref:System.Windows.Forms.Form.TopMost%2A>.<br />-Estableciendo la propiedad <xref:System.Windows.Forms.Form.Opacity%2A> por debajo del 50%.<br />: Establecer la propiedad <xref:System.Windows.Forms.Form.WindowState%2A> en <xref:System.Windows.Forms.FormWindowState.Minimized> mediante programación.<br />-Llamando al método <xref:System.Windows.Forms.Form.Activate%2A>.<br />-Usar los valores de enumeración <xref:System.Windows.Forms.FormBorderStyle.None>, <xref:System.Windows.Forms.FormBorderStyle.FixedToolWindow>y <xref:System.Windows.Forms.FormBorderStyle.SizableToolWindow><xref:System.Windows.Forms.FormBorderStyle>.|  
|<xref:System.Windows.Forms.NotifyIcon>|-El uso del componente <xref:System.Windows.Forms.NotifyIcon> está completamente restringido.|  
  
 El valor <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> restringe las acciones enumeradas en la tabla siguiente, además de las restricciones colocadas por el valor <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows>.  
  
|Componente|Acciones restringidas|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.CommonDialog>|-Mostrar un cuadro de diálogo derivado de la clase <xref:System.Windows.Forms.CommonDialog>.|  
|<xref:System.Windows.Forms.Control>|-Llamando al método <xref:System.Windows.Forms.Control.CreateGraphics%2A>.<br />-   Establecer la propiedad <xref:System.Windows.Forms.Control.Cursor%2A>.|  
|<xref:System.Windows.Forms.Control.Cursor%2A>|-   Establecer la propiedad <xref:System.Windows.Forms.Cursor.Current%2A>.|  
|<xref:System.Windows.Forms.MessageBox>|-Llamando al método <xref:System.Windows.Forms.Form.Show%2A>.|  
  
### <a name="hosting-third-party-controls"></a>Hospedaje de controles de terceros  
 Otro tipo de manipulación de ventanas es posible si los formularios hospedan controles de terceros. Un control de terceros es cualquier <xref:System.Windows.Forms.UserControl> personalizado que no haya desarrollado y compilado usted mismo. Aunque el escenario de hospedaje es difícil de manipular, teóricamente es posible que un control de terceros expanda su superficie de representación para abarcar toda el área del formulario. Después, el control podría imitar un cuadro de diálogo crítico y solicitar información tal como una combinación de nombre de usuario y contraseña o los números de cuenta bancaria de sus usuarios.  
  
 Para limitar este riesgo potencial, utilice controles de terceros pertenecientes únicamente a proveedores de confianza. Si utiliza controles de terceros que ha descargado de un origen que no puede comprobar, se recomienda que revise el código fuente en busca de posibles puntos vulnerables. Después de comprobar que el origen no es malintencionado, debería compilar el ensamblado para garantizar que el origen coincide con el ensamblado.  
  
## <a name="windows-api-calls"></a>Llamadas a la API de Windows  
 Si el diseño de la aplicación requiere una llamada a una función de la API de Windows, tiene acceso al código no administrado. En este caso, las acciones del código en la ventana o el sistema operativo no se pueden determinar cuando se trabaja con valores o llamadas a la API de Windows. La clase <xref:System.Security.Permissions.SecurityPermission> y el valor <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> de la enumeración <xref:System.Security.Permissions.SecurityPermissionFlag> controlan el acceso a código no administrado. Una aplicación solo puede tener acceso al código no administrado cuando se le concede el permiso <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>. De manera predeterminada, solo las aplicaciones que se ejecutan localmente pueden llamar a código no administrado.  
  
 Algunos miembros de Windows Forms proporcionan acceso no administrado que requiere el permiso <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>. En la tabla siguiente se enumeran los miembros del espacio de nombres <xref:System.Windows.Forms> que requieren el permiso. Para más información sobre los permisos necesarios para un miembro, consulte la documentación de la biblioteca de clases de .NET Framework.  
  
|Componente|Member|  
|---------------|------------|  
|<xref:System.Windows.Forms.Application>|Método -   <xref:System.Windows.Forms.Application.AddMessageFilter%2A><br />-   propiedad <xref:System.Windows.Forms.Application.CurrentInputLanguage%2A><br />Método -   `Exit`<br />Método -   <xref:System.Windows.Forms.Application.ExitThread%2A><br />-   <xref:System.Windows.Forms.Application.ThreadException> evento|  
|<xref:System.Windows.Forms.CommonDialog>|Método -   <xref:System.Windows.Forms.CommonDialog.HookProc%2A><br />-   <xref:System.Windows.Forms.CommonDialog.OwnerWndProc%2A>método)<br />Método -   <xref:System.Windows.Forms.CommonDialog.Reset%2A><br />Método -   <xref:System.Windows.Forms.CommonDialog.RunDialog%2A>|  
|<xref:System.Windows.Forms.Control>|Método -   <xref:System.Windows.Forms.Control.CreateParams%2A><br />Método -   <xref:System.Windows.Forms.Control.DefWndProc%2A><br />Método -   <xref:System.Windows.Forms.Control.DestroyHandle%2A><br />Método -   <xref:System.Windows.Forms.Control.WndProc%2A>|  
|<xref:System.Windows.Forms.Help>|métodos de <xref:System.Windows.Forms.Help.ShowHelp%2A> de -   <br />Método -   <xref:System.Windows.Forms.Help.ShowHelpIndex%2A>|  
|<xref:System.Windows.Forms.NativeWindow>|-   <xref:System.Windows.Forms.NativeWindow> (clase)|  
|<xref:System.Windows.Forms.Screen>|Método -   <xref:System.Windows.Forms.Screen.FromHandle%2A>|  
|<xref:System.Windows.Forms.SendKeys>|Método -   <xref:System.Windows.Forms.SendKeys.Send%2A><br />Método -   <xref:System.Windows.Forms.SendKeys.SendWait%2A>|  
  
 Si la aplicación no tiene permiso para llamar a código no administrado, la aplicación debe solicitar <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> permiso o debe tener en cuenta las formas alternativas de implementar características; en muchos casos, Windows Forms proporciona una alternativa administrada a las funciones de la API de Windows. Si no existen ningún medio alternativo y la aplicación debe tener acceso a código no administrado, deberá elevar los permisos a la aplicación.  
  
 El permiso para llamar a código no administrado permite a una aplicación realizar casi todo. Por ello, este permiso para llamar a código no administrado únicamente se debe conceder a aplicaciones que procedan de un origen de confianza. De forma alternativa, dependiendo de la aplicación, la función que realiza la llamada al código no administrado podría ser opcional, o solo habilitarse en el entorno de plena confianza. Para más información sobre los permisos arriesgados, vea [Dangerous Permissions and Policy Administration](../misc/dangerous-permissions-and-policy-administration.md) (Permisos peligrosos y administración de directivas). Para más información sobre la elevación de permisos, vea [Administración general de directivas de seguridad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100)).  
  
## <a name="see-also"></a>Consulte también

- [Acceso más seguro a archivos y datos en Windows Forms](more-secure-file-and-data-access-in-windows-forms.md)
- [Impresión más segura en Windows Forms](more-secure-printing-in-windows-forms.md)
- [Información general sobre la seguridad en Windows Forms](security-in-windows-forms-overview.md)
- [Windows Forms Security](windows-forms-security.md)
- [Proteger las aplicaciones ClickOnce](/visualstudio/deployment/securing-clickonce-applications)

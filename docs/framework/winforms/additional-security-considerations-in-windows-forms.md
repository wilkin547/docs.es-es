---
title: Consideraciones de seguridad adicionales en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, secure calls to Windows API
- security [Windows Forms]
- security [Windows Forms], calling APIs
- Clipboard [Windows Forms], securing access
ms.assetid: 15abda8b-0527-47c7-aedb-77ab595f2bf1
ms.openlocfilehash: 276def9db2ff610a22b42a88ad658727793b53de
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718914"
---
# <a name="additional-security-considerations-in-windows-forms"></a>Consideraciones de seguridad adicionales en formularios Windows Forms
La configuración de seguridad de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] puede hacer que la aplicación se ejecute de manera diferente en un entorno de confianza parcial que en el equipo local. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] restringe el acceso a recursos locales críticos como el sistema de archivos, la red y API no administradas, entre otras cosas. La configuración de seguridad afecta a la capacidad de llamar a la API Microsoft Win32 u otras API que no pueda comprobar el sistema de seguridad. La seguridad afecta también a otros aspectos de la aplicación, incluido el acceso a archivos y datos y su impresión. Para más información sobre el acceso a archivos y datos en un entorno de confianza parcial, consulte [Acceso más seguro a archivos y datos en Windows Forms](more-secure-file-and-data-access-in-windows-forms.md). Para más información sobre cómo imprimir en un entorno de confianza parcial, consulte [Impresión más segura en Windows Forms](more-secure-printing-in-windows-forms.md).  
  
 En las siguientes secciones se explica cómo trabajar con el Portapapeles, manipular ventanas y llamar a la API Win32 desde aplicaciones que se ejecutan en un entorno de confianza parcial.  
  
## <a name="clipboard-access"></a>Acceso al Portapapeles  
 El <xref:System.Security.Permissions.UIPermission> clase controla el acceso al Portapapeles y asociado <xref:System.Security.Permissions.UIPermissionClipboard> valor de enumeración indica el nivel de acceso. En la tabla siguiente se muestran los niveles de permiso posibles.  
  
|Valor UIPermissionClipboard|Descripción|  
|---------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard>|El Portapapeles se puede utilizar sin límites.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard>|El Portapapeles se puede utilizar con ciertas limitaciones. La capacidad de colocar datos en el Portapapeles (operaciones del comando Copiar o Cortar) no está limitada. Los controles intrínsecos que acepten Pegar, como un cuadro de texto, pueden aceptar datos del Portapapeles, pero los controles de usuario no pueden leer el Portapapeles mediante programación.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.NoClipboard>|No se puede usar el Portapapeles.|  
  
 De forma predeterminada, la zona Intranet Local recibe <xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard> acceso y la zona Internet recibe <xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard> acceso. Esto significa que la aplicación puede copiar datos en el Portapapeles, pero no puede leer el Portapapeles ni pegar datos en él mediante programación. Estas limitaciones impiden que los programas que no sean de plena confianza lean el contenido copiado en el Portapapeles por otra aplicación. Si la aplicación requiere acceso total al Portapapeles pero no tiene los permisos necesarios, deberá conceder dichos permisos a la aplicación. Para más información sobre la elevación de permisos, vea [Administración general de directivas de seguridad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100)).  
  
## <a name="window-manipulation"></a>Manipulación de ventanas  
 El <xref:System.Security.Permissions.UIPermission> clase controla también el permiso para manipular ventanas y otras acciones relacionadas con la interfaz de usuario y el asociado <xref:System.Security.Permissions.UIPermissionWindow> valor de enumeración indica el nivel de acceso. En la tabla siguiente se muestran los niveles de permiso posibles.  
  
 De forma predeterminada, la zona Intranet Local recibe <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> acceso y la zona Internet recibe <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> acceso. Esto significa que, en la zona Internet, la aplicación puede realizar la mayoría de las operaciones de ventanas de la interfaz de usuario, pero se modificará la apariencia de la ventana. La ventana modificada muestra una notificación en un globo la primera vez que se ejecuta, contiene el texto de la barra de título modificada y requiere un botón Cerrar en la barra de título. La notificación del globo y la barra de título informan al usuario de la aplicación que esta se está ejecutando bajo confianza parcial.  
  
|Valor UIPermissionWindow|Descripción|  
|------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionWindow.AllWindows>|Los usuarios pueden utilizar todas las ventanas y eventos de entrada de usuario sin restricciones.|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows>|Los usuarios solo pueden utilizar ventanas de nivel superior y ventanas secundarias más seguras para dibujar, y solo pueden utilizar eventos de entrada de datos del usuario para la interfaz de usuario dentro de dichas ventanas de nivel superior y ventanas secundarias. Estas ventanas más seguras están claramente etiquetadas y tienen restricciones de tamaño máximo y mínimo. Las restricciones de evitar los ataques de suplantación de identidad potencialmente perjudiciales, como la imitación de pantallas de inicio de sesión del sistema o el escritorio del sistema y restringe el acceso mediante programación principal de windows, la API relacionadas con el foco y el uso de la <xref:System.Windows.Forms.ToolTip> (control),|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows>|Los usuarios solo pueden utilizar ventanas secundarias más seguras para dibujar, y solo pueden utilizar eventos de entrada del usuario para la interfaz de usuario dentro de esa ventana secundaria. Un control mostrado en un explorador es un ejemplo de una ventana secundaria más segura.|  
|<xref:System.Security.Permissions.UIPermissionWindow.NoWindows>|Los usuarios no pueden utilizar ninguna ventana ni ningún evento de interfaz de usuario. No se puede utilizar ninguna interfaz de usuario.|  
  
 Cada nivel de permiso identificado por la <xref:System.Security.Permissions.UIPermissionWindow> enumeración permite menos acciones que el nivel por encima de él. Las tablas siguientes indican las acciones que están restringidas por la <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> y <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> valores. Para saber los permisos exactos necesarios para cada miembro, consulte el material de referencia de dicho miembro en la documentación de la biblioteca de clases de .NET Framework.  
  
 <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> permiso restringe las acciones enumeradas en la tabla siguiente.  
  
|Componente|Acciones restringidas|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.Application>|-   Establecer la propiedad <xref:System.Windows.Forms.Application.SafeTopLevelCaptionFormat%2A>.|  
|<xref:System.Windows.Forms.Control>|-Obtener la <xref:System.Windows.Forms.Control.Parent%2A> propiedad.<br />-   Establecer la propiedad `Region`.<br />-Llamar el <xref:System.Windows.Forms.Control.FindForm%2A> , <xref:System.Windows.Forms.Control.Focus%2A>, <xref:System.Windows.Forms.Control.FromChildHandle%2A> y <xref:System.Windows.Forms.Control.FromHandle%2A>, <xref:System.Windows.Forms.Control.PreProcessMessage%2A>, <xref:System.Windows.Forms.Control.ReflectMessage%2A>, o <xref:System.Windows.Forms.Control.SetTopLevel%2A> método.<br />-Llamar el <xref:System.Windows.Forms.Control.GetChildAtPoint%2A> método si el control devuelto no es un elemento secundario del control que realiza la llamada.<br />-   Modificar el foco en un control contenedor.|  
|<xref:System.Windows.Forms.Cursor>|-   Establecer la propiedad <xref:System.Windows.Forms.Cursor.Clip%2A>.<br />-Llamar el <xref:System.Windows.Forms.Control.Hide%2A> método.|  
|<xref:System.Windows.Forms.DataGrid>|-Llamar el <xref:System.Windows.Forms.ContainerControl.ProcessTabKey%2A> método.|  
|<xref:System.Windows.Forms.Form>|-Obtener la <xref:System.Windows.Forms.Form.ActiveForm%2A> o <xref:System.Windows.Forms.Form.MdiParent%2A> propiedad.<br />-Establecer la <xref:System.Windows.Forms.Form.ControlBox%2A>, <xref:System.Windows.Forms.Form.ShowInTaskbar%2A>, o <xref:System.Windows.Forms.Form.TopMost%2A> propiedad.<br />-Establecer la <xref:System.Windows.Forms.Form.Opacity%2A> propiedad por debajo del 50%.<br />-Establecer la <xref:System.Windows.Forms.Form.WindowState%2A> propiedad <xref:System.Windows.Forms.FormWindowState.Minimized> mediante programación.<br />-Llamar el <xref:System.Windows.Forms.Form.Activate%2A> método.<br />-El uso de la <xref:System.Windows.Forms.FormBorderStyle.None>, <xref:System.Windows.Forms.FormBorderStyle.FixedToolWindow>, y <xref:System.Windows.Forms.FormBorderStyle.SizableToolWindow> <xref:System.Windows.Forms.FormBorderStyle> valores de enumeración.|  
|<xref:System.Windows.Forms.NotifyIcon>|-Usar el <xref:System.Windows.Forms.NotifyIcon> componente está completamente restringido.|  
  
 El <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> valor restringe las acciones enumeradas en la siguiente tabla, además a las limitaciones que impone el <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> valor.  
  
|Componente|Acciones restringidas|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.CommonDialog>|-Mostrando un cuadro de diálogo derivado de la <xref:System.Windows.Forms.CommonDialog> clase.|  
|<xref:System.Windows.Forms.Control>|-Llamar el <xref:System.Windows.Forms.Control.CreateGraphics%2A> método.<br />-   Establecer la propiedad <xref:System.Windows.Forms.Control.Cursor%2A>.|  
|<xref:System.Windows.Forms.Control.Cursor%2A>|-   Establecer la propiedad <xref:System.Windows.Forms.Cursor.Current%2A>.|  
|<xref:System.Windows.Forms.MessageBox>|-Llamar el <xref:System.Windows.Forms.Form.Show%2A> método.|  
  
### <a name="hosting-third-party-controls"></a>Hospedaje de controles de terceros  
 Otro tipo de manipulación de ventanas es posible si los formularios hospedan controles de terceros. Un control de terceros es cualquier personalizado <xref:System.Windows.Forms.UserControl> que no se ha desarrollado y compilado usted mismo. Aunque el escenario de hospedaje es difícil de manipular, teóricamente es posible que un control de terceros expanda su superficie de representación para abarcar toda el área del formulario. Después, el control podría imitar un cuadro de diálogo crítico y solicitar información tal como una combinación de nombre de usuario y contraseña o los números de cuenta bancaria de sus usuarios.  
  
 Para limitar este riesgo potencial, utilice controles de terceros pertenecientes únicamente a proveedores de confianza. Si utiliza controles de terceros que ha descargado de un origen que no puede comprobar, se recomienda que revise el código fuente en busca de posibles puntos vulnerables. Después de comprobar que el origen no es malintencionado, debería compilar el ensamblado para garantizar que el origen coincide con el ensamblado.  
  
## <a name="win32-api-calls"></a>Llamadas API Win32  
 Si el diseño de la aplicación requiere llamar a una función de la API Win32, estará teniendo acceso a código no administrado. En este caso las acciones del código en la ventana o el sistema operativo no se pueden determinar cuando se trabaja con valores o llamadas API Win32. El <xref:System.Security.Permissions.SecurityPermission> clase y el <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> valor de la <xref:System.Security.Permissions.SecurityPermissionFlag> enumeración controlar el acceso a código no administrado. Una aplicación puede tener acceso a código no administrado, solo cuando se concede el <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> permiso. De manera predeterminada, solo las aplicaciones que se ejecutan localmente pueden llamar a código no administrado.  
  
 Algunos miembros de Windows Forms proporcionan acceso no administrado que requiere el <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> permiso. En la tabla siguiente se enumera los miembros en el <xref:System.Windows.Forms> espacio de nombres que requieren el permiso. Para más información sobre los permisos necesarios para un miembro, consulte la documentación de la biblioteca de clases de .NET Framework.  
  
|Componente|Miembro|  
|---------------|------------|  
|<xref:System.Windows.Forms.Application>|Método -   <xref:System.Windows.Forms.Application.AddMessageFilter%2A><br />-   <xref:System.Windows.Forms.Application.CurrentInputLanguage%2A> Propiedad<br />Método -   `Exit`<br />Método -   <xref:System.Windows.Forms.Application.ExitThread%2A><br />-   <xref:System.Windows.Forms.Application.ThreadException> Evento|  
|<xref:System.Windows.Forms.CommonDialog>|Método -   <xref:System.Windows.Forms.CommonDialog.HookProc%2A><br />-   <xref:System.Windows.Forms.CommonDialog.OwnerWndProc%2A>\ (método)<br />Método -   <xref:System.Windows.Forms.CommonDialog.Reset%2A><br />Método -   <xref:System.Windows.Forms.CommonDialog.RunDialog%2A>|  
|<xref:System.Windows.Forms.Control>|Método -   <xref:System.Windows.Forms.Control.CreateParams%2A><br />Método -   <xref:System.Windows.Forms.Control.DefWndProc%2A><br />Método -   <xref:System.Windows.Forms.Control.DestroyHandle%2A><br />Método -   <xref:System.Windows.Forms.Control.WndProc%2A>|  
|<xref:System.Windows.Forms.Help>|-   <xref:System.Windows.Forms.Help.ShowHelp%2A> Métodos<br />Método -   <xref:System.Windows.Forms.Help.ShowHelpIndex%2A>|  
|<xref:System.Windows.Forms.NativeWindow>|-   <xref:System.Windows.Forms.NativeWindow> Clase|  
|<xref:System.Windows.Forms.Screen>|Método -   <xref:System.Windows.Forms.Screen.FromHandle%2A>|  
|<xref:System.Windows.Forms.SendKeys>|Método -   <xref:System.Windows.Forms.SendKeys.Send%2A><br />Método -   <xref:System.Windows.Forms.SendKeys.SendWait%2A>|  
  
 Si la aplicación no tiene permiso para llamar a código no administrado, la aplicación debe solicitar <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> permiso, o bien debe tener en cuenta las formas alternativas de implementación de características; en muchos casos, Windows Forms proporciona una alternativa administrada a la API Win32 funciones. Si no existen ningún medio alternativo y la aplicación debe tener acceso a código no administrado, deberá elevar los permisos a la aplicación.  
  
 El permiso para llamar a código no administrado permite a una aplicación realizar casi todo. Por ello, este permiso para llamar a código no administrado únicamente se debe conceder a aplicaciones que procedan de un origen de confianza. De forma alternativa, dependiendo de la aplicación, la función que realiza la llamada al código no administrado podría ser opcional, o solo habilitarse en el entorno de plena confianza. Para más información sobre los permisos arriesgados, vea [Dangerous Permissions and Policy Administration](../misc/dangerous-permissions-and-policy-administration.md) (Permisos peligrosos y administración de directivas). Para más información sobre la elevación de permisos, vea [Administración general de directivas de seguridad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100)).  
  
## <a name="see-also"></a>Vea también
- [Acceso más seguro a archivos y datos en Windows Forms](more-secure-file-and-data-access-in-windows-forms.md)
- [Impresión más segura en Windows Forms](more-secure-printing-in-windows-forms.md)
- [Información general sobre la seguridad en Windows Forms](security-in-windows-forms-overview.md)
- [Windows Forms Security](windows-forms-security.md)
- [Proteger las aplicaciones ClickOnce](/visualstudio/deployment/securing-clickonce-applications)
